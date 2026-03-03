pipeline
{
    agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
    stages
    {
        stage('BUILD')
        {
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

        stage('test')
        {
            steps{
                sh '''
                test -f build/index.html
                npm test 
                echo "Test Stage Completed"
                '''
            }
        }
    }
}