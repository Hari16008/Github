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
               bat 'docker-compose down'
            }
        }
           stage('docker compose start') {
              steps {
               bat 'docker-compose up -d'
            }
        }
        stage('push image') {
              steps {
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/new_image'
                // bat 'docker push hari16008/new_image'
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
