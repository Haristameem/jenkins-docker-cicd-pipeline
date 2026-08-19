pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Haristameem/jenkins-docker-cicd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-cicd-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop devops-cicd-container || exit 0'
                bat 'docker rm devops-cicd-container || exit 0'
                bat 'docker run -d -p 8080:80 --name devops-cicd-container devops-cicd-app'
            }
        }
    }
}
