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
              sh 'docker build -t alpine_jenkins .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'docker tag alpine_jenkins:latest hari16008/alpine:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               sh 'docker login -u hari16008 -p hAri@1101'
                sh 'docker push alpine_jenkins:latest'
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
