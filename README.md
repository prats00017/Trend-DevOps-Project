# Trend DevOps Project

## 🚀 Overview

This project demonstrates an end-to-end CI/CD pipeline for deploying the **Trend Store Application** using **Terraform, Jenkins, Docker, Amazon EKS, Prometheus, and Grafana**.

The application source code is stored in GitHub. Jenkins automates the build and deployment process, Docker containerizes the application, Amazon EKS orchestrates the containers, and Prometheus with Grafana provide monitoring and visualization.

---

## 📌 Architecture

```
GitHub
   ↓
Jenkins Pipeline
   ↓
Docker Build
   ↓
DockerHub
   ↓
Amazon EKS
   ↓
Kubernetes Deployment + Service
   ↓
Trend Store Application
   ↓
Prometheus
   ↓
Grafana Dashboard
```

---

## 🛠 Technologies Used

* AWS
* Terraform
* Jenkins
* Docker
* DockerHub
* Kubernetes
* Amazon EKS
* Prometheus
* Grafana
* GitHub

---

## 📂 Project Structure

```
Trend/
│
├── Dockerfile
├── Jenkinsfile
├── README.md
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│
├── k8s/
│   ├── deployment.yaml
│   ├── service.yaml
│
└── src/
```

---

## ⚙️ CI/CD Workflow

### 1. Source Code Management

* Code stored in GitHub repository.
* Jenkins integrated with GitHub.

### 2. Build Stage

* Jenkins builds Docker image.

```bash
docker build -t prateek0017/trend-app:latest .
```

### 3. Push Stage

* Docker image pushed to DockerHub.

```bash
docker push prateek0017/trend-app:latest
```

### 4. Deploy Stage

* Kubernetes manifests applied to Amazon EKS.

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

---

## 🐳 Docker

Build Image

```bash
docker build -t prateek0017/trend-app:latest .
```

Run Container

```bash
docker run -d -p 8081:80 prateek0017/trend-app:latest
```

---

## ☸️ Kubernetes Deployment

Deployment

```bash
kubectl apply -f k8s/deployment.yaml
```

Service

```bash
kubectl apply -f k8s/service.yaml
```

Verify

```bash
kubectl get pods
kubectl get svc
kubectl get nodes
```

---

## 📊 Monitoring Setup

### Prometheus

Prometheus collects metrics from the Kubernetes cluster.

### Grafana

Grafana visualizes:

* CPU Usage
* Memory Usage
* Disk Usage
* Network Usage
* Node Metrics
* Running Pods
* Cluster Resource Utilization

Imported Dashboards:

* Node Exporter Full
* Kubernetes Views Global

---

## 📈 Jenkins Pipeline

```groovy
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
```

---

## ✅ Results

* Infrastructure provisioned using Terraform.
* Jenkins CI/CD pipeline automated successfully.
* Docker image pushed to DockerHub.
* Application deployed on Amazon EKS.
* Service exposed using AWS LoadBalancer.
* Prometheus monitoring configured.
* Grafana dashboards visualized cluster metrics.

---

## 📸 Screenshots

* Terraform Apply
* Jenkins Dashboard
* Pipeline Success
* EKS Cluster
* Kubernetes Pods
* Kubernetes Services
* Trend Store Application
* Prometheus Metrics
* Node Exporter Dashboard
* Kubernetes Views Global Dashboard

---

## 🎯 Conclusion

Successfully implemented a complete DevOps workflow using Terraform, Jenkins, Docker, Amazon EKS, Prometheus, and Grafana. The project demonstrates Infrastructure as Code, CI/CD automation, Kubernetes orchestration, and real-time monitoring of cluster resources.

