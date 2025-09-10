pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Chellurigayathridevi/janabank.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t janabank:latest .'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up -d --build'
            }
        }
    }
}

