pipeline
{
    stages
    {
        stage('BUILD')
        {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps
            {
                sh '''
                ls -la
                node --version 
                npm  --version
                echo "Build Stage completed"
                npm ci 
                npm run build
                ls -la
                '''
            }
        }

        stage('TEST')
        {
            steps{
                agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
                sh '''
                test -f build/index.html
                npm test 
                echo "Test Stage Completed"
                '''
            }
        }
    }
}