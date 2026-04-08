# js-webapp-cd

This repository contains the Kubernetes deployment configuration for a JavaScript web application, integrated with **ArgoCD** for continuous deployment on a Kubernetes cluster.

## 🚀 Features
- Kubernetes Deployment manifest with 2 replicas
- Kubernetes Service exposing the app via NodePort
- Integrated with ArgoCD for automated deployment
- Deploys Docker image: `abdelrahman678/web-js-app:v17`

## 📁 Project Structure
/js-webapp-cd
│
├── deployment.yml # Kubernetes Deployment manifest
├── svc-WA.yml # Kubernetes Service manifest
└── README.md # Project description


## ⚙️ Kubernetes Deployment Details

### Deployment (`deployment.yml`)
- **replicas:** 2
- **container image:** `abdelrahman678/web-js-app:v17`
- **container name:** `wwebapp`
- **labels:** `app: webapp-deploy`
- **selector:** `app: webapp-deploy`

### Service (`svc-WA.yml`)
- **type:** NodePort
- **port:** 8080
- **targetPort:** 3000
- **selector:** `app: webapp-deploy`

This allows the app to be exposed to the cluster network via port 8080.

## 🔄 CI/CD Pipeline
- The repository is connected to **ArgoCD**.
- Any update pushed to the repo triggers **automatic deployment** to the Kubernetes cluster.
- ArgoCD syncs the manifests, ensuring the live cluster matches the repo configuration.

## 🐳 Prerequisites
- Kubernetes cluster
- ArgoCD installed and configured
- Docker image `abdelrahman678/web-js-app:v17` available in Docker registry

## 📌 Author
AbdelRahman Ahmed