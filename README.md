# Application Deployment with CI/CD using AWS, Terraform, Jenkins and Docker

## Overview
This project demonstrates an end-to-end CI/CD pipeline for deploying the Trendify web application using AWS EC2, Terraform, Jenkins and Docker.

## Tech Stack
- AWS EC2
- Terraform
- Jenkins
- Docker
- GitHub
- Nginx
- Linux

## Architecture

GitHub Repository
↓
Jenkins Pipeline
↓
Docker Build
↓
Docker Container
↓
AWS EC2 Instance
↓
Trendify Application

## Steps Performed

### 1. Infrastructure Provisioning
- Created AWS infrastructure using Terraform.
- Configured VPC and Security Group.

### 2. Jenkins Setup
- Installed Jenkins on EC2.
- Enabled port 8080.

### 3. Docker Setup
- Installed Docker.
- Added Jenkins user to Docker group.

### 4. GitHub Integration
- Connected GitHub repository to Jenkins.
- Configured Pipeline from SCM.

### 5. CI/CD Pipeline
- Jenkinsfile fetched from GitHub.
- Docker image built automatically.
- Container deployed on port 8081.

### 6. Security Group Configuration

Allowed ports:

- 22 (SSH)
- 8080 (Jenkins)
- 8081 (Application)

## Commands

### Check Docker Images

```bash
docker images
```

### Check Running Containers

```bash
docker ps
```

### Restart Jenkins

```bash
sudo systemctl restart jenkins
```

### Restart Docker

```bash
sudo systemctl restart docker
```

## Application URL

```
http://13.201.62.188:8081
```

## Results

- Jenkins Pipeline executed successfully.
- Docker image built automatically.
- Container deployed successfully.
- Application accessible externally.

## Author

Prateek Gupta
