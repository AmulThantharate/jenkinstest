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
                script{
                 def freeMem = sh(script: 'free -m | awk \'/MemFree:/ {print $2}\'', returnStdout: true).trim()
                    echo "Free Memory: ${freeMem} MB"                    
		}
            }
        }
    }
}
