pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
        stage('Build Image') {
            steps {
              bat 'docker-compose up -d 
            }
        }
        
         stage('push image') {
          
            steps {
               sh 'sudo docker login -u hari16008 -p hAri@1101'
                sh 'sudo docker push hari16008/compose_nginx_build:latest'
               // sh 'sudo docker push hari16008/compose_nginx_build:latest'
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
