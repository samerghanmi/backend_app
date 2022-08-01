pipeline
{
    agent any
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
