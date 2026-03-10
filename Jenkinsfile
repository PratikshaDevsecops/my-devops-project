pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t hospital-website .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop hospital-container || true'
                sh 'docker rm hospital-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name hospital-container hospital-website'
            }
        }

    }
}