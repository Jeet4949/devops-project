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
