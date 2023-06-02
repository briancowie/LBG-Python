pipeline {
    
    agent any
    
    stages {    
        stage('build and run containers') {
            steps {
                sh '''
                docker build -t gcr.io/lbg-mea-11/bcowie-sprint3:v1 .
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
