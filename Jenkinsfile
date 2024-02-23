pipeline
{
    agent any
    stages
    {
        stage('Continuesdownload')
        {
            steps
            {
                git'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('ContinuesBuild')
        {
            steps
            {
                sh'mvn package'
            }
        }
        stage('ContinuesDeploy')
        {
            steps
            {
                sh'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war abhi@10.128.15.210:/var/lib/tomcat9/webapps/testapp.war'
            }
        }

    
}
