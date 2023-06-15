pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
        stage('docker compose stop') {
          
            steps {
               sh 'docker-compose down'
            }
        }
           stage('docker compose start') {
          
            steps {
               sh 'docker-compose up -d'
            }
        }
        
         stage('push image') {
          
            steps {
               sh 'sudo docker login -u hari16008 -p hAri@1101'
                sh 'sudo docker push hari16008/new_image:latest'
               // sh 'sudo docker push hari16008/new_image:latest'
            }
        }
    }
    post { 
        aborted { 
            echo 'ABORTED'
        }
         success { 
            echo 'SUCCESS'
        }
         failure { 
            echo 'FAILURE'
        }
        changed { 
            echo 'FAILURE'
        }
    }
    
}
