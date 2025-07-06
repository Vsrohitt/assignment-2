# CLO835 Assignment 2 – Kubernetes Multi-Tier App Deployment using Kind

👨‍💻 Author: **Rohit Sharma**  
📍 Seneca College – Summer 2025  
📦 GitHub Repo: [assignment-2](https://github.com/Vsrohitt/assignment-2)

---

## 🔍 Project Description

This project builds on Assignment 1, where a multi-container Flask app and MySQL database were containerized and pushed to **Amazon ECR**.  
In this assignment, I deployed the same application stack onto a local **Kubernetes cluster using Kind** (Kubernetes-in-Docker), following best practices including namespaces, pull secrets, deployments, and services.

---

## 📁 Folder Structure
k8s-assignment2/
├── kind-config.yaml
├── deployments/
│ ├── mysql-deployment.yaml
│ └── webapp-deployment.yaml
├── services/
│ ├── mysql-service.yaml
│ └── webapp-service.yaml

## 🔧 Technologies Used

- **Amazon EC2 (Amazon Linux 2)**
- **Docker & Kubernetes (Kind)**
- **kubectl, AWS CLI**
- **Amazon ECR for container images**
- **Kubernetes Namespaces, Deployments, Services**

---

## 🚀 Deployment Workflow

1. ✅ **Created Kind cluster** using `kind-config.yaml`
2. ✅ **Created namespaces**: `webapp` and `mysql-ns`
3. ✅ **Created ECR pull secrets** in both namespaces
4. ✅ **Deployed** MySQL and Flask containers using Deployments
5. ✅ **Used headless ClusterIP** service for MySQL
6. ✅ **Exposed Flask webapp** using NodePort (`30000`)
7. ✅ **Tested deployment** using curl and browser via EC2 public IP

---

## 🐳 ECR Docker Images

Images pulled directly from my Amazon ECR repository:

- `529989091415.dkr.ecr.us-east-1.amazonaws.com/clo835-webapp`
- `529989091415.dkr.ecr.us-east-1.amazonaws.com/clo835-mysql`

---

## 🌐 Access

- Web Application URL:  
  `http://<EC2_PUBLIC_IP>:30000`

Use `curl http://checkip.amazonaws.com` to get your EC2’s public IP.

---

## 📝 Key Notes

- Kubernetes Deployments manage ReplicaSets automatically
- MySQL runs internally with a headless ClusterIP service
- Flask app is exposed externally via NodePort
- ECR login and secret setup ensures private image access per namespace

