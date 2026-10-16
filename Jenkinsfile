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
            def hostname = sh(script: 'hostname', returnStdout: true).trim()
            echo "Hostname: ${hostname}"
        }
    }
}
