# 🚀 AdApp – CI/CD + Docker + Kubernetes DevOps Project

## 📌 Overview

AdApp is a containerized Node.js web application demonstrating a complete DevOps workflow using:

* Docker containerization
* Kubernetes orchestration (Kind)
* GitHub Actions CI/CD
* Trivy security scanning
* Docker Hub image publishing
* Kubernetes manifests for deployment

This project showcases practical DevOps and platform engineering concepts including container orchestration, CI/CD automation, vulnerability scanning, and Kubernetes deployments.

---

# 🛠️ Tech Stack

| Technology     | Purpose                     |
| -------------- | --------------------------- |
| Node.js        | Web Application             |
| Docker         | Containerization            |
| Kubernetes     | Container Orchestration     |
| Kind           | Local Kubernetes Cluster    |
| GitHub Actions | CI/CD Pipeline              |
| Trivy          | Container Security Scanning |
| Docker Hub     | Container Registry          |
| YAML           | Kubernetes Manifests        |

---

# 📁 Project Structure

```text
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
├── Dockerfile
├── package.json
├── package-lock.json
├── app.js
├── .gitignore
└── README.md
```

---

# 🐳 Docker Setup

## Build Docker Image

```bash
docker build -t adapp:v1 .
```

## Verify Docker Image

```bash
docker images
```

---

# ☸️ Kubernetes Deployment

## Create Kind Cluster

```bash
kind create cluster --name adapp-cluster
```

## Verify Cluster

```bash
kubectl get nodes
```

## Load Docker Image into Kind

```bash
kind load docker-image adapp:v1 --name adapp-cluster
```

## Deploy Kubernetes Manifests

```bash
kubectl apply -f k8s/
```

## Verify Pods

```bash
kubectl get pods
```

## Verify Services

```bash
kubectl get svc
```

---

# 🌐 Access Application

## Port Forward Service

```bash
kubectl port-forward service/adapp-service 8080:80
```

Open browser:

```text
http://localhost:8080
```

---

# 📦 Kubernetes Deployment Manifest

## deployment.yaml

* Creates Kubernetes Deployment
* Runs multiple pod replicas
* Uses Docker image `adapp:v1`
* Exposes container port 3000

## service.yaml

* Creates Kubernetes Service
* Routes traffic to pods
* Exposes application internally within cluster

---

# ⚙️ CI/CD Pipeline

GitHub Actions pipeline automatically:

* Checks out source code
* Installs Node.js dependencies
* Builds Docker image
* Runs Trivy vulnerability scan
* Pushes Docker image to Docker Hub

Pipeline triggers automatically on push to:

```text
main
```

---

# 🔐 Security Scanning

Trivy is integrated into the CI/CD pipeline to scan Docker images for:

* Vulnerabilities
* Misconfigurations
* Security issues

---

# 📤 Docker Hub Integration

Docker images are automatically pushed to Docker Hub using GitHub Actions secrets.

Required GitHub Secrets:

| Secret Name     | Description             |
| --------------- | ----------------------- |
| DOCKER_USERNAME | Docker Hub Username     |
| DOCKER_PASSWORD | Docker Hub Access Token |

---

# 📈 Kubernetes Scaling

Scale deployment manually:

```bash
kubectl scale deployment adapp --replicas=4
```

Verify scaling:

```bash
kubectl get pods
```

---

# ✅ Features Demonstrated

* CI/CD Pipeline Automation
* Docker Containerization
* Kubernetes Deployment
* Kubernetes Scaling
* Infrastructure as Code Concepts
* DevSecOps Security Scanning
* Container Registry Integration
* Local Kubernetes Cluster Management

---

# 📷 Recommended Screenshots for Repository

Add screenshots for:

* GitHub Actions successful pipeline
* Docker image build
* Kubernetes pods running
* Kubernetes services
* Application running in browser

---

# 🚀 Future Improvements

* Helm Charts
* Ingress Controller
* Monitoring with Prometheus & Grafana
* Terraform-based Kubernetes Infrastructure
* ArgoCD / GitOps Deployment
* SonarQube Integration

---

# 👨‍💻 Author

Amit Kumar

GitHub: [https://github.com/aamit1512-dotcom](https://github.com/aamit1512-dotcom)
LinkedIn: Add your LinkedIn profile here
