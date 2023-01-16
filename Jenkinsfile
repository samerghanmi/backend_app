pipeline
{
    agent any
    stages
    {
        stage('image docker')
        {
            steps
            {
                bat 'docker build -t backend .'
                echo 'done 1'
            }
        }
        stage('Build')
        {
            steps
            {
                bat 'npm install'
                echo 'done build'
            }
        }
        stage('push app') {
            steps {
                bat "docker tag backend:latest samerghanmi/backend"

                bat "docker push samerghanmi/backend"
                echo 'push succeed'
                    }
                }
        stage('deploy') {
            steps {
                bat 'docker-compose up'
                }
                }
        
        
    
    

    }
    
}
