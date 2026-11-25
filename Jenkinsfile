pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                echo 'Code deja recupere par Jenkins'
                checkout scm
            }
        }
        stage('Build Images') {
            steps {
                sh 'docker build -t mern-server ./Server'
                sh 'docker build -t mern-client ./Client'
            }
        }
        stage('Deploy with Compose') {
            steps {
                sh 'docker compose down || true'
                sh 'docker compose up --build -d'
            }
        }
        stage('Test') {
            steps {
                sh 'sleep 5'
                sh 'curl -f http://localhost:9000/api/health'
                sh 'docker compose ps'
            }
        }
    }
}