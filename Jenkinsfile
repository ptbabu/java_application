pipeline {
   agent any
   parameters {
        string(name: 'ENV', defaultValue: 'DEV', description: 'How should I greet the world?')
        choice(choices: ['US-EAST-1', 'US-WEST-2'], description: 'What AWS region?', name: 'region')
		string(name: 'ENV', defaultValue: 'PROD', description: 'How should I greet the world?')
        choice(choices: ['US-EAST-1', 'US-WEST-2'], description: 'What AWS region?', name: 'region')
    }
    stages {
       
        stage('Build') {
           
           agent { 
               label 'docker'
            }
            steps {
                echo 'Building..'
                 sh 'mvn package'
            }
        
           
           agent { 
               label 'slave1'
            }
            steps {
                echo 'Building..'
                 sh 'mvn package'
            }
		}
       
   
        stage('Deploy') {
           agent { 
               label 'docker'
            }
            
            steps {
                
                sh 'sudo apt update -y'
                sh 'sudo apt install tomcat8 -y'
                sh 'sudo apt install tomcat8-admin -y'
                sh 'sudo apt install tomcat8-user -y'
                sh 'sudo cp /home/ubuntu/workspace/paramerized_pipeline1/target/grants.war /var/lib/tomcat8/webapps/'
                sh 'sudo cp /home/ubuntu/workspace/paramerized_pipeline1/tomcat-users.xml /etc/tomcat8/'
                sh 'sudo service tomcat8 restart'
            }
        
           agent { 
               label 'slave1'
            }
            
            steps {
                
                sh 'sudo apt update -y'
                sh 'sudo apt install tomcat8 -y'
                sh 'sudo apt install tomcat8-admin -y'
                sh 'sudo apt install tomcat8-user -y'
                sh 'sudo cp /home/ubuntu/workspace/paramerized_pipeline1/target/grants.war /var/lib/tomcat8/webapps/'
                sh 'sudo cp /home/ubuntu/workspace/paramerized_pipeline1/tomcat-users.xml /etc/tomcat8/'
                sh 'sudo service tomcat8 restart'
            }
        }
    }
}

