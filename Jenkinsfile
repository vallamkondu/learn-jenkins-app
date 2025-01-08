pipeline {
    agent any
    
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
               sh '''
               ls -ltra
               node --version
               npm --version
               npm ci
               npm run build
               ls -ltra
               '''
            }
        }
        stage('with docker') {
            steps {
                sh '''echo "Hello world with docker"
                touch container-yes.txt
                ls -ltra
                '''
                
            }
        }
    }
}