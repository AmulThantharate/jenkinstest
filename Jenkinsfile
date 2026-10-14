pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello, World!'
            }
        }
        stage("System Memory"){
            steps {
                scripts{
                    def meminfo = sh(script: 'free -m', retruststdout: true).trim()
                    echo "Memory Info:\n${meminfo}"
                }
            }
        }
    }
}
