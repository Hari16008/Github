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
              bat 'docker build -t jenkins_task .'
            }
        }
         stage('Tag Image') {
           
            steps {
               bat 'docker tag jenkins_task:latest hari16008/jenkins_task:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/jenkins_task:latest'
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
