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
    }

}

        
