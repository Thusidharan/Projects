# DevOps Continuous Deployment (CD) Project

## Project Overview
Extended the CI project with a Continuous Deployment (CD) setup.

### 1. CD Process Setup:
- Integrated the existing CI pipelines with a CD process using **Azure Kubernetes Service (AKS)** for Kubernetes cluster management.
- Employed **ArgoCD** as the GitOps tool for automating deployments.

### 2. GitOps Workflow Implementation:
- Configured ArgoCD to monitor changes in the **Azure DevOps Repos**, specifically focusing on updated Docker images in the **Azure Container Registry (ACR)** resulting from CI builds.
- Created a new 'update' stage in each microservice pipeline to handle the deployment process.

### 3. Automated Image Updates:
- Utilized a custom shell script to update **Kubernetes manifest files** in the repository with the latest image tags.
- Configured GitOps to automatically detect and apply changes in the Kubernetes specification manifest file to the AKS cluster.

### 4. Kubernetes and GitOps Management:
- Set up and configured a suitable **AKS cluster** to manage container orchestration.
- Configured ArgoCD to access the AKS cluster with the necessary permissions and network settings.
- Managed access control for the private repository and ACR to ensure secure operations.

### 5. Validation of CI/CD Pipeline:
- Successfully deployed microservices to the AKS cluster using **ArgoCD**, demonstrating a fully automated GitOps-based CD pipeline.
- Validated real-time updates and deployment efficiency from code commit to production-like deployment.
