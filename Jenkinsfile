pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
                sh ''' 
                '''
            }
        }
        stage('Stage 2'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "Docker Image Deployed"
                '''
            }
        }
    }
}
