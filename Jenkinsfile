pipeline
{
    agent any
    stages
    {
        stage('ContinuosDownload')
        {
            steps
            {
                git 'https://github.com/sushma-suma/mymaven.git'
            }
        }
        stage('ContinuosBuild')
        {
            steps
            {
                sh 'mvn package'
                
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '56669dda-ddff-4884-ae06-526da02164e4', path: '', url: 'http://172.31.91.100:8080')], contextPath: 'testapp', war: '**/*.war'
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
               git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
               sh 'java -jar  /root/.jenkins/workspace/ScriptedPipeline/testing.jar'
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
               deploy adapters: [tomcat9(credentialsId: '56669dda-ddff-4884-ae06-526da02164e4', path: '', url: 'http://172.31.84.73:8080')], contextPath: 'prodapp', war: '**/*.war'

            }
        }
        
        
    }
}
