# 🚀 End-to-End DevOps Lifecycle Project

A complete CI/CD pipeline implementation using **Docker**, **Jenkins**, and **Kubernetes**. This project automates the entire software delivery process—from code commit to production deployment.

## 🏗️ Architecture


1.  **Code:** Developer pushes code to GitHub.
2.  **Build (CI):** Jenkins detects the change, pulls code, and builds a Docker image.
3.  **Ship:** Jenkins pushes the image to Docker Hub.
4.  **Deploy (CD):** Kubernetes (Minikube) pulls the image and runs it as a scalable service.

## 🛠️ Tools Used
* **Version Control:** Git & GitHub
* **Containerization:** Docker
* **CI Server:** Jenkins (Running in Docker)
* **Orchestration:** Kubernetes (Minikube)
* **Scripting:** Groovy (Jenkins Pipeline), YAML (K8s Manifests)

## 📂 Project Structure
```text
├── Dockerfile          # Blueprint for the Python/Flask App
├── Jenkinsfile         # The CI Pipeline script (Groovy)
├── app.py              # Simple Python Flask Application
├── deployment.yaml     # K8s Deployment Manifest (High Availability)
└── service.yaml        # K8s Service Manifest (Load Balancer/Network)

⚙️ How to Run This Project
1. Prerequisites
Docker Desktop installed

Minikube & Kubectl installed

Jenkins Container running

2. The Application
The app is a simple Python Flask server listening on Port 5000.

Docker Build: docker build -t my-devops-app .

Docker Run: docker run -p 5000:5000 my-devops-app

3. The Kubernetes Deployment
Deploy the app to the local cluster:

Bash

# Apply configuration
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

# Check status
kubectl get pods
kubectl get svc

# Access the App
minikube service my-devops-service
🌟 Key Features
Automated Pipeline: Zero-touch build and push process.

Security: Credentials managed via Jenkins Secrets (not hardcoded).

High Availability: Deployed with 2 replicas in Kubernetes.

Self-Healing: Kubernetes automatically restarts crashed pods.
