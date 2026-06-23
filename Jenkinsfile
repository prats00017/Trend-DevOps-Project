pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t prateek0017/trend-app:latest .'
            }
        }

        stage('Push to DockerHub') {
            steps {
                sh 'docker push prateek0017/trend-app:latest'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker rm -f trend-container || true
                docker run -d -p 8081:80 --name trend-container prateek0017/trend-app:latest
                '''
            }
        }
    }
}