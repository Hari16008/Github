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
              bat 'docker build -t nodejs_task .'
            }
        }
         stage('Tag Image') {
              steps {
               bat 'docker tag nodejs_task:latest hari16008/nodejs_task:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               bat 'docker login -u hari16008 -p hAri@1101'
                bat 'docker push hari16008/nodejs_task:latest'
            }
         }
         stage('Run Image') {
              steps {
                bat 'docker run --name jenkinsC2 -p 7780:80 -d nodejs_task:latest'
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
