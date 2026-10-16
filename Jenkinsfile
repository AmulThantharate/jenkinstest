pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
	    stage("Print Hostname"){
	        steps{
                script {
                if (isUnix()) {
                    sh "hostname"
                } else {
                    bat "hostname"
                }
            }
            }
        }
        stage("System Information"){
            steps {
                script {
                    def hostname = sh(script: 'hostname', returnStdout: true).trim()
                    echo "Hostname: ${hostname}"
                }
            }
        }
        stage("Custom Variable"){
            steps{
                script {
                    env.JENKINS_CUSTOM = "Hello Jenkins"
                }
                sh "echo ${env.JENKINS_CUSTOM}"
            }
        }
    }
}
