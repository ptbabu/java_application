pipeline {
    agent {
         docker { image 'maven:3-alpine' }
          }
    stages {
        stage('run') {
            steps {
                sh 'docker run -d maven:3-alpine'
            }
        }
        stage('Back-end') {
            steps {
                sh 'mvn --version'
            }
        }
        
    }
}

