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
    }

    stages
    {
        stage('Unit Testing')
        {
            steps
            {
                bat 'mvn test'
            }
        }
    }
}