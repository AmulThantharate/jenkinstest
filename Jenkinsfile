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
                if (isUnix()) {
                    sh "hostname"
                } else {
                    bat "hostname"
                }
            }
        }
    }
}
