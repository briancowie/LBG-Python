pipeline {
    
    agent any
    
    stages {
        stage('pre-build cleanup') {
            steps {
                sh 'docker stop $(docker ps -a -q)'
            }
        }    
        
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t lbg-app:v1 .
                docker run -d -p 5000:8080 --name lbg-app lbg-app:v1
                '''
            }
        }
    }
}   
