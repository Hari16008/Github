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
              bat 'docker build -t ubuntu_jenkins .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag ubuntu_jenkins:latest hari16008/ubuntu:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/ubuntu_jenkins:latest'
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
