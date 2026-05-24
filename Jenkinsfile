pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Priyanshukumar23/HobbyHub'
            }
        }

        stage('Build Docker Containers') {
            steps {
                sh 'docker compose up --build -d'
            }
        }

        stage('Check Running Containers') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
