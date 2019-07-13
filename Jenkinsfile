pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 9000:3306'
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
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }
    }
}
