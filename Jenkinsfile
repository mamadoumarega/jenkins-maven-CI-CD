pipeline {
agent any
tools
{
maven "Maven"
}
stages {
stage('checkout') {
steps {
git branch: 'main', url: 'https://github.com/mamadoumarega/jenkins-maven-CI-CD'
}
}
stage('Execute Maven') {
steps {
sh 'mvn package'
}
}
stage('Docker Build and Tag') {
steps {
}
stage('Run Docker container on Jenkins Agent') {
steps {
sh "docker run -d -p 8003:8080 samplewebapp"
}
}
}
}

