pipeline {
    agent {
        docker {
            image 'node:9-alpine' 
            args '-p 3000:3000 -p 5000:5000'
	    args '-u 0:0'	 
        }
    }
    environment {
        CI = 'true'
    }	
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
