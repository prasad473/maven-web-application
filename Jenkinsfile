node
{
def mavenHome = tool name: "maven3.6.2"
  properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
stage('CheckoutCode')
{
git branch: 'development', credentialsId: 'bec76dc9-de6d-44ec-be82-066d4c41e5da', url: 'https://github.com/prasad473/maven-web-application.git'
}

stage('build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('Executesonarqubereport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('uploadartifactintonexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployappintoTomcat')
{
sshagent(['8df7ce2f-efef-4b12-9a4b-87ac771e7ae5']) 
{
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@65.0.104.51:/opt/apache-tomcat-9.0.39/webapps"
  
}
}
stage('sendemail')
{
mail bcc: '', body: 'Build', cc: 'ndprasad696@gmail.com', from: '', replyTo: '', subject: 'Build Over', to: 'prasad.dvp73@gmail.com'
}
*/
}




