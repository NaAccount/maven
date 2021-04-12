node('master') 
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/intelliqittrainings/maven.git'             
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@100.25.198.15:/var/lib/tomcat9/webapps/testapp.war'
    }

    stage('ContinuousTesting')
    {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
    }
    stage('ContinuousDelivery')
    {
    
    sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@54.235.26.86:/var/lib/tomcat9/webapps/prodapp.war'}
}
