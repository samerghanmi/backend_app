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
    }
    stage('Code Quality Check via SonarQube') {
        steps 
        {
            script 
            {
                def scannerHome = tool 'sonarqube';
                withSonarQubeEnv("sqserv") 
                {
                    sh "${tool("sonarqube")}/bin/sonar-scanner \
                    -Dsonar.projectKey=test-node-js \
                    -Dsonar.sources=. \
                    -Dsonar.css.node=. \
                    -Dsonar.host.url=http://localhost:9000 \
                    "
               }
           }
       }
   }
    
}