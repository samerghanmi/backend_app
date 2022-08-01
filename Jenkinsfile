pipeline
{
    agent
    {
        docker
        {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    stages
    {
        stage('Build')
        {
            steps
            {
                sh 'npm install'
                echo 'done 2'
            }
        }
    
    stage('Code Quality Check via SonarQube') {
        steps {
      	withSonarQubeEnv('sonarqubeserver'){
		sh 'npm sonar:sonar'
		}
           }
       }
    }
    
}
