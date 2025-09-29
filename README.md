# Jenkins Kubernetes Deployment Practice

## Overview
This repository contains practice files for deploying Jenkins on Kubernetes using Minikube.  
It includes:
- Deployment YAML for Jenkins
- Service YAML to expose Jenkins
- Practice screenshots for reference

---

## Project Structure
├── deployment.yaml 
├── service.yaml 
├── images/ # Practice screenshots
│ ├── 1.png
│ ├── 2.png
│ └── 3.png
  └── 4.png
└── README.md


---

## Jenkins Deployment
- **Namespace:** jen-app  
- **Replicas:** 3  
- **Container Image:** `jenkins/jenkins:latest`  
- **Port:** 8080  

### Apply Deployment
```bash
kubectl create namespace jen-app   # if not already created
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

Notes:

Make sure Minikube is running with at least 2 CPUs and 4GB RAM:

minikube start --driver=docker --cpus=2 --memory=4096


For persistent Jenkins data, consider adding PersistentVolume and PersistentVolumeClaim.

ClusterIP services are internal only. Use NodePort or LoadBalancer for external access.


References:

Minikube Documentation

Kubernetes Official Docs

Jenkins Docker Image
