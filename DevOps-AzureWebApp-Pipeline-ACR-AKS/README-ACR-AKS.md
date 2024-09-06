## Azure and Kubernetes (K8s) : Azure Container Registry (ACR) and AKS Cluster Integration

### Project Overview
Integrated Azure Container Registry (ACR) with Azure Kubernetes Service (AKS) for container deployment.

### 1. ACR and AKS Provisioning:
- Provisioned an **Azure Container Registry (ACR)** and an **Azure Kubernetes Service (AKS)** cluster, setting up a new resource group for deployment.

### 2. Pipeline for Build and Deployment:
- Configured Azure Pipelines to build Docker images and push them to ACR.
- Developed a pipeline to pull code from GitHub, build Docker images with Azure CLI, and deploy them to the AKS cluster.

### 3. CI/CD Workflow Verification:
- Tested the CI/CD workflow by making a test commit to Azure Repo, which triggered an automatic deployment.
- Verified that the Docker image updates were applied seamlessly in the AKS cluster.
