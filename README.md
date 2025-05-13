# EKS


# Production-Ready DevSecOps CI/CD Pipeline on AWS EKS

## 🚀 Overview

Deploy a static web application on AWS EKS using a robust DevSecOps CI/CD pipeline that incorporates security, scalability, observability, and automation.

## 🧰 Technologies Used

- **Infrastructure & Orchestration:** AWS EKS, Terraform, Kubernetes, Helm
- **CI/CD & GitOps:** GitHub Actions, ArgoCD
- **Monitoring & Logging:** Prometheus, Grafana, OpenSearch
- **Security & Compliance:** Trivy, External Secrets Operator (ESO)
- **Storage & Networking:** EFS & EBS CSI Drivers, NGINX Ingress Controller
- **Scaling & Networking Enhancements:** Karpenter, KEDA, Cilium
- **Core Kubernetes Components:** CoreDNS, KubeProxy, Metrics Server

## 🗺️ Implementation Roadmap

### 1. Infrastructure Provisioning
- Provision VPC, subnets, and IAM roles using Terraform.
- Deploy EKS cluster and configure node groups.

### 2. CI/CD Pipeline Setup
- **GitHub Actions:** Build, scan (Trivy), and push Docker images to Amazon ECR.
- **ArgoCD:** GitOps deployment to EKS using Helm charts.

### 3. Application Deployment
- Use Helm for templated Kubernetes manifests.
- Setup NGINX Ingress Controller and Route 53 for domain access.

### 4. Monitoring & Logging
- Deploy Prometheus & Grafana for metrics.
- Deploy OpenSearch and integrate Fluent Bit for logs.

### 5. Security Enhancements
- Use ESO for secret management.
- Integrate Trivy in CI for vulnerability scans.

### 6. Storage & Networking
- Use EBS CSI for block storage.
- Use EFS CSI for shared file storage.

### 7. Scaling & Networking
- Use Karpenter and KEDA for workload and node scaling.
- Cilium for advanced CNI features and security.

## 📁 Project Structure

```
devsecops-eks-pipeline/
├── terraform/
│   ├── vpc/
│   ├── eks/
│   └── modules/
├── helm-charts/
│   ├── nginx-ingress/
│   ├── prometheus/
│   ├── grafana/
│   ├── opensearch/
│   └── application/
├── github-actions/
│   └── workflows/
│       ├── build.yml
│       └── deploy.yml
├── argocd/
│   └── applications/
│       └── app.yaml
├── manifests/
│   ├── storage/
│   ├── secrets/
│   └── scaling/
└── docs/
    └── architecture-diagram.png
```

## 🧭 Architecture Flow

1. **Dev Workflow:** GitHub push triggers Actions to build, scan, and push images to ECR.
2. **GitOps CD:** ArgoCD syncs Helm charts to EKS.
3. **Ingress & DNS:** NGINX Ingress + ExternalDNS for routing.
4. **Monitoring & Logging:** Prometheus/Grafana + OpenSearch.
5. **Security:** Trivy for image scanning, ESO for secrets.
6. **Scaling:** Karpenter/KEDA for dynamic scaling.
7. **Networking:** Cilium for enhanced CNI.

## 📚 Resources

- [AWS Observability Accelerator](https://aws.amazon.com/blogs/mt/introducing-amazon-eks-observability-accelerator/)
- [Three-Tier DevSecOps Project](https://github.com/codewithmuh/three-tier-devsecops-project)
- [Advanced DevSecOps Pipeline](https://medium.com/@mohammedbazith/advanced-devsecops-pipeline-with-kubernetes-aws-and-gitops-da6d5537ede1)
