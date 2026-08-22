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
                bat 'docker build -t jenkins-docker-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop jenkins-docker-app || exit /b 0'
                bat 'docker rm jenkins-docker-app || exit /b 0'
                bat 'docker run -d -p 8081:80 --name jenkins-docker-app jenkins-docker-app'
            }
        }
    }
}
