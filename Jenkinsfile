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
        stage('ContinuesTesting')
        {
            steps
            {
                 git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                 
                 sh'java -jar /var/lib/jenkins/workspace/DeclarativePipeline2/testing.jar'
                 
            }
        }
        stage('ContinuesDelivery')
        {
            steps
            {
                sh'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war abhi@10.128.15.212:/var/lib/tomcat9/webapps/prodapp.war'
            }
        }
    }

    
}
