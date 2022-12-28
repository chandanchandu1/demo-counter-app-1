pipeline
{
    agent any

    stages
    {
        stage('git')
        {
            steps
            {
                git 'https://github.com/chandanchandu1/demo-counter-app-1.git'
            }
        }
    
        stage('Unit Testing')
        {
            steps
            {
                bat 'mvn test'
            }
        }

        stage('Integrating testing')
        {
            steps
            {
                bat 'mvn verify -DskipUnitTests'
            }
        }

        stage('maven build')
        {
            steps
            {
                bat 'mvn clean install'
            }
        }

        stage('sonar qube')
        {
            steps
            {
                script
                {
                    withSonarQubeEnv(credentialsId: 'sonar-api-key')
                    {
                        bat 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
}