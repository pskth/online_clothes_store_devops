pipeline {
    agent any

    stage('Clone Repository') {
    steps {
        git branch: 'development',
            url: 'https://github.com/prajwalinna/online_clothes_store_devops.git'
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