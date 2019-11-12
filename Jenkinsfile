pipeline {
    agent {
         docker { image 'maven:3-alpine' }
          }
    stages {
        stage('run') {
            steps {
                sh 'ocker run --name test -it debian .'
            }
        }
        stage('Back-end') {
            steps {
                sh 'mvn --version'
            }
        }
        
    }
}

