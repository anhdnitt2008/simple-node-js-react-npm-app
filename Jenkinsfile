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
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    
}
