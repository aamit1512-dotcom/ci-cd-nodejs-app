🚀 CI/CD Node.js Application with Docker & Kubernetes
📌 Overview

This project demonstrates a complete DevOps workflow for a Node.js application using:

Docker containerization
Kubernetes deployment using Kind
GitHub Actions CI/CD pipeline
Trivy security scanning
Docker Hub image publishing

The project showcases practical DevOps and DevSecOps concepts including CI automation, container orchestration, vulnerability scanning, and Kubernetes deployments.

🛠️ Tech Stack
Technology	Purpose
Node.js	Web Application
Docker	Containerization
Kubernetes	Container Orchestration
Kind	Local Kubernetes Cluster
GitHub Actions	CI/CD Pipeline
Trivy	Security Scanning
Docker Hub	Container Registry
📁 Repository Structure
ci-cd-nodejs-app/
│
├── .github/
│   └── workflows/
│       └── main.yml
│
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
│
├── screenshots/
│   ├── app-running.png
│   ├── kubernetes-pods.png
│   └── pipeline.png
│
├── .gitignore
├── app.js
├── Dockerfile
├── package.json
├── package-lock.json
└── README.md
⚙️ CI/CD Pipeline

GitHub Actions pipeline automatically performs:

Source code checkout
Node.js setup
Dependency installation
Docker image build
Trivy vulnerability scan
Docker image push to Docker Hub

Pipeline triggers automatically on push to:

main
🐳 Docker Setup
Build Docker Image
docker build -t node-app:v1 .
Verify Docker Image
docker images
☸️ Kubernetes Setup Using Kind
Create Local Kubernetes Cluster
kind create cluster --name node-app-cluster
Verify Cluster
kubectl get nodes
Load Docker Image into Kind
kind load docker-image node-app:v1 --name node-app-cluster
🚀 Deploy Application to Kubernetes
Apply Kubernetes Manifests
kubectl apply -f k8s/
Verify Pods
kubectl get pods
Verify Services
kubectl get svc
🌐 Access the Application
Port Forward Kubernetes Service
kubectl port-forward service/adapp-service 8080:80

Open browser:

http://localhost:8080
📦 Kubernetes Manifests
deployment.yaml

Responsible for:

Creating Kubernetes Deployment
Running multiple pod replicas
Managing application containers
Exposing container port 3000
service.yaml

Responsible for:

Creating Kubernetes Service
Routing traffic to application pods
Exposing application inside cluster
🔐 Security Scanning

Trivy is integrated into the CI/CD pipeline for container vulnerability scanning.

Scans include:

OS package vulnerabilities
Dependency vulnerabilities
Security misconfigurations
📤 Docker Hub Integration

Docker images are automatically pushed to Docker Hub using GitHub Actions secrets.

Required repository secrets:

Secret Name	Description
DOCKER_USERNAME	Docker Hub Username
DOCKER_PASSWORD	Docker Hub Access Token
📈 Kubernetes Scaling

Scale application replicas:

kubectl scale deployment adapp --replicas=4

Verify scaling:

kubectl get pods
📷 Project Screenshots
GitHub Actions Pipeline

Kubernetes Pods Running

Application Running in Browser

✅ Features Demonstrated
Docker Containerization
Kubernetes Deployment
Kubernetes Scaling
GitHub Actions CI/CD
DevSecOps Security Scanning
Docker Hub Integration
Infrastructure as Code Concepts
Local Kubernetes Cluster Management
🚀 Future Improvements
Helm Charts
Kubernetes Ingress
Monitoring with Prometheus & Grafana
Terraform Infrastructure Provisioning
SonarQube Integration
👨‍💻 Author

Amit Kumar

GitHub: https://github.com/aamit1512-dotcom