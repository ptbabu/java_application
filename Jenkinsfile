pipeline {
    agent {
         docker { image 'maven:3-alpine' }
          }
    stages {
        stage('run') {
            steps {
                sh 'docker run --name test -it debian .'
            }
        }
        stage('Back-end') {
            steps {
                sh 'mvn --version'
            }
        }
        
    }
}

