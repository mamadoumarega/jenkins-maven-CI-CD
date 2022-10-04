pipeline {
    agent any
    tools {
        maven "maven"
    }
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mamadoumarega/jenkins-maven-CI-CD'
            }
        }
        stage('Execute Maven') {
            steps { sh 'mvn package' }
        }
        stage('Docker Build and Tag') {
            steps { sh 'docker build -t samplewebapp:latest .' }
        }
        stage('Run Docker container on Jenkins Agent') {
            steps {
                sh "docker run -d -p 8003:8080 samplewebapp"
            }
        }
    }
}
