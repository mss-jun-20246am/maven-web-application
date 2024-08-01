node 
{
echo "The Job name is: ${env.JOB_NAME}"
echo "The node name is: ${env.NODE_NAME}"
echo "The Jenkins Home Dir name: ${env.JENKINS_HOME}"

def mavenHome = tool name: 'maven3.9.8'

stage('CheckOutCode')
{
    git branch: 'development', credentialsId: '2546aafd-99e6-4f08-8bde-e4e030cfb94f', url: 'https://github.com/mss-jun-20246am/maven-web-application.git'
}
stage('Build')
{
    sh "${mavenHome}/bin/mvn clean package"
}

  /*
stage('ExecuteSonarQubeReport')
{
    sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
stage('UploadArtifactIntoNexus')
{
    sh "${mavenHome}/bin/mvn clean deploy"
}
stage('DiployAppIntoTomcat')
{
sshagent(['d8cea364-8299-4801-a729-039b51976a6d']) {
    
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.13.55:/opt/apache-tomcat-9.0.91/webapps/"
}
}
*/
}
