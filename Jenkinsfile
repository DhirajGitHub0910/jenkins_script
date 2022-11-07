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
        stage('continious deployment') 
        {
            steps 
            {
              deploy adapters: [tomcat9(credentialsId: 'baefdbc7-9a7a-450b-b42b-d9af879cb8ea', path: '', url: 'http://172.31.85.137:8080')], contextPath: 'testapp1', war: '**/*.war'  
            }
        }
        stage('continious testing') 
        {
            steps 
            {
               git 'https://github.com/DhirajGitHub0910/testing.git'
               sh 'java -jar /var/lib/jenkins/workspace/pipeline/testing.jar'
               
            }
        }
        stage('continious delivery') 
        {
            steps 
            {
               deploy adapters: [tomcat9(credentialsId: 'baefdbc7-9a7a-450b-b42b-d9af879cb8ea', path: '', url: 'http://172.31.85.137:8080')], contextPath: 'prodapp', war: '**/*.war'
            }
        }
    }
}

