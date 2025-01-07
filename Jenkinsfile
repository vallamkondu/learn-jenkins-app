pipeline {
    agent any
    
    stages {
        stage('without docker') {
            steps {
               sh '''
               echo "Without docker"
               touch container-no.txt
               ls -ltra
               '''
            }
        }
        stage('with docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''echo "Hello world with docker"
                touch container-yes.txt
                ls -ltra
                '''
                
            }
        }
    }
}