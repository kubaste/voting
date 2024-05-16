pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https:repo.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'docker-compose up -d --build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'docker-compose exec server npm test'
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    sh 'docker-compose down'
                }
            }
        }
    }
}
