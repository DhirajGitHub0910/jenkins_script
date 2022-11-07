pipeline {
    agent any

    stages
    {
        stage('continious download') 
        {
            steps 
            {
                git 'https://github.com/DhirajGitHub0910/maven.git'

            }
        }
        stage('continious building') 
        {
            steps 
            {
              sh 'mvn package'  
            }
        }
        
        
    }
}

