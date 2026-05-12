pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Cloning GitHub Repository'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-cicd-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop flask-container || true'
                sh 'docker rm flask-container || true'
                sh 'docker run -d -p 5000:5000 --name flask-container flask-cicd-app'
            }
        }

    }
}