pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
         stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
         }

        stage('Build') { 
            steps { 
                
                 sh''' sudo docker build -t flaskapp . '''
                }
            }
        
        stage('Deploy') { 
            steps { 
                
                 sh''' sudo docker run -itd --name flaskapp -p 83:5000 flaskapp:latest '''
                }
            }
       }
   
   }
