pipeline {
    agent any

    environment {
        DOCKER_HOST = "unix:///home/prajwal-inna/.docker/desktop/docker.sock"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'development',
                url: 'https://github.com/prajwalinna/online_clothes_store_devops.git'
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                dir('backend') {
                    sh 'npm install'
                }
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    sh 'npm install'
                }
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker compose build'
            }
        }

        stage('Run Containers') {
            steps {
                sh 'docker compose up -d'
            }
        }

        stage('Verify Containers') {
            steps {
                sh 'docker ps'
            }
        }
    }
}