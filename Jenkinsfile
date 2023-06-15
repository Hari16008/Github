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
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/compose_nginx_build:latest'
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
