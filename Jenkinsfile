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
        stage("Tree Package Install"){
            steps{
                script{
                    sh """
                    if command -v tree >/dev/null 2>&1; then
                        echo "Package tree is already installed"
                    else
                        echo "Installing Package tree"
                        sudo apt-get update -y
                        sudo apt-get install tree -y
                    fi
                    """
                }
            }
        }
        stage("Verify Tree Installation"){
            steps{
                script{
                    def treeVersion = sh(script: 'tree --version', returnStdout: true).trim()
                    echo "Tree Version: ${treeVersion}"
                }
            }
        }
    }
}
