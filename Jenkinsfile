pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Haristameem/jenkins-docker-cicd-pipeline.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t jenkins-docker-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8081:80 jenkins-docker-app'
            }
        }
    }
}
