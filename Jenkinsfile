pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t trend-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f trend-container || true
                docker run -d -p 8081:80 --name trend-container trend-app
                '''
            }
        }

    }
}