pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t docker-cicd-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f docker-cicd-app || true'
                sh 'docker run -d --name docker-cicd-app -p 8081:80 docker-cicd-app'
            }
        }
    }
}
