# 🚀 Project 2: Mivahub Fashion Collection (Production EKS Deployment)

A production-grade, containerized web application deployed on **Amazon EKS (Elastic Kubernetes Service)** using **Terraform** for Infrastructure as Code and **GitHub Actions** for CI/CD automation with vulnerability scanning.

---

## 🏗️ Architecture & Tech Stack
* **Cloud Provider:** Amazon Web Services (AWS - `us-east-1`)
* **Containerization:** Docker (Nginx-Alpine, Non-Root Security Best Practices)
* **Container Registry:** Amazon ECR (`project2-app`)
* **CI/CD Automation:** GitHub Actions (Automated build, Trivy security scan, and ECR push)
* **Infrastructure as Code (IaC):** Terraform (Modular VPC and EKS v1.31 cluster with managed `t3.small` nodes)
* **Orchestration:** Kubernetes (Deployments, Services, and AWS Classic Load Balancer)

---

## 📂 Project Structure
```text
project-2/
├── .github/
│   └── workflows/
│       └── deploy.yml       # GitHub Actions CI/CD pipeline
├── terraform/
│   ├── providers.tf         # AWS provider and backend config
│   ├── variables.tf         # Input variables (region, cluster name)
│   ├── vpc.tf               # Custom VPC configuration (Public/Private subnets)
│   └── eks.tf               # EKS Cluster and Managed Node Group
├── Dockerfile               # Production Nginx Dockerfile (non-root appuser)
├── .dockerignore            # Excluded build files
├── index.html               # Mivahub Fashion Collection frontend
└── k8s-deployment.yaml      # Kubernetes Deployment and LoadBalancer Service