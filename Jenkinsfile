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
        stage('SonarQube analysis') 
        {
            def scannerHome = tool 'SonarScanner 4.0';
            withSonarQubeEnv('sonarscannerserv') 
            { // If you have configured more than one global server connection, you can specify its name
                sh "${scannerHome}/bin/sonar-scanner"
            }
        }
        
    
    

    }
    
}
