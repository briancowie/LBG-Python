pipeline {
    
    agent any
    
    stages {
        stage('pre-build cleanup') {
            steps {
                sh 'docker stop $(docker ps -a -q) && docker rm -vf $(docker ps -aq) && docker rmi -f $(docker images -aq)'
            }
        }    
        
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t bcowie-sprint3:v1 .
                '''
            }
        }
        
        stage('push to GCR'){
            steps{
                sh 'docker push gcr.io/lbg-mea-11/bcowie-sprint3:v1'
            }
        }
    }
}   
