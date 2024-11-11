node{
echo "The job name is: ${env.JOB_NAME}"
echo "The node name is: ${env.NODE_NAME}"
echo "The build number is: ${env.BUILD_NUMBER}"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

def mavenHome = tool name: 'maven3.9.8'

stage('CheckOutCode'){
git branch: 'development', credentialsId: '635807d9-7de5-4fdf-86af-05766f2091ba', url: 'https://github.com/etishree-git/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
/*
}
stage('ExecuteSonarqubeReport'){
sh "${mavenHome}/bin/mvn clean sonar:sonar"
}
stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn clean deploy"
}
stage('DeployAppIntoTomcatServer'){
sshagent(['716452f8-b47d-4f74-8843-7c26b563c55d']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.6.65:/opt/tomcat9/webapps"
}
}
*/
}
