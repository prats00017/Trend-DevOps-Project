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

        stage('Deploy to EKS') {
            steps {
                sh 'kubectl apply -f k8s/deployment.yaml'
                sh 'kubectl apply -f k8s/service.yaml'
            }
        }
    }
}