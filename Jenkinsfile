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
              sh 'docker build -t jenkins_ubuntu .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'docker tag jenkins_ubuntu:latest hari16008/ubuntu:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/jenkins_ubuntu:latest'
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
