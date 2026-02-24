pipeline {
    agent any

    stages {
        stage('w/o Docker') {
            steps {
                sh ''' 
                echo "WithOut Docker"
                touch container-no.txt
                '''
            }
        }
        stage('w Docker'){
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "With Docker"
                touch container-yes.txt
                '''
            }
        }
    }
}
