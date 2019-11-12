pipeline {
    agent {
         docker { image 'maven:3-alpine' }
          }
    stages {
        stage('run') {
            steps {
                sh 'docker run --name test -it maven:3-alpine '
            }
        }
        stage('Back-end') {
            steps {
                sh 'mvn --version'
            }
        }
        
    }
}

