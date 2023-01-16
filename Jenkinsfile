pipeline
{
    agent any
    stages
    {
        stage('image docker')
        {
            steps
            {
                sh 'docker build -t backend .'
                echo 'done 1'
            }
        }
        stage('Build')
        {
            steps
            {
                sh 'npm install'
                echo 'done 2'
            }
        }
        stage('push app') {
            steps {
                bat "docker tag backend:latest samerghanmi/backend"

                bat "docker push samerghanmi/backend"
                    }
                }
        stage('deploy') {
            steps {
                bat 'docker-compose up'
                }
                }
        
        
    
    

    }
    
}
