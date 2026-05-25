pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Priyanshukumar23/HobbyHub'
            }
        }
        stage('Create Env File') {
            steps {
                sh '''
                echo "PORT=5000" > server/.env
                echo "JWT_SECRET=hobbyhubsecret123" >> server/.env
                echo "MONGO_URI=mongodb://mongo:27017/hobbyhub" >> server/.env
                '''
            }
        }
        stage('Build Docker Containers') {
            steps {
                sh 'docker-compose down'
                sh 'docker-compose up --build -d'
            }
        }

        stage('Check Running Containers') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
