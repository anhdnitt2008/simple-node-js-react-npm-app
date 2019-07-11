pipelinre {
    agent {
        docker {
            image 'node:9-alpine' 
            args '-p 3003:3003' 
        }
    }
    environment {
	HOME = '.'
    }	
    stages {
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
	}
    }
}
