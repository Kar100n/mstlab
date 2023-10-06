pipeline 
{
    agent any
    tools{maven 'M1'}
    stages 
    {
        stage("fetching") 
        {
            steps 
            {
                git branch: 'main', url:https://github.com/Kar100n/mstlab"
            }
        }
        stage('compile')
        {
            steps 
            {
                sh 'mvn compile'
            }
        }
        stage('Test')
        {
            steps 
            {
                sh 'mvn test'
            }
        }
    }
}
