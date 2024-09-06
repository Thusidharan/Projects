# DevOps Continuous Integration (CI) Project

## Project Overview
Set up and configured a DevOps project in Azure DevOps.

### 1. Project Setup:
- Created a new project and integrated a voting application from GitHub consisting of three microservices (Node.js, Python, and .NET).
- Migrated the complete GitHub repository to Azure DevOps Repos, ensuring all codebases were properly imported and versioned.

### 2. Azure Resource Configuration:
- Created a **Resource Group (RG)** and an **Azure Container Registry (ACR)** to manage and store Docker images.
- Provisioned a **Virtual Machine (VM)** in Azure to act as a custom build agent for enhanced control over the build environment.

### 3. Build Pipeline Implementation:
- Set up separate **CI pipelines** in Azure DevOps for each microservice to handle the build process and Docker image creation.
- Configured pipelines to push Docker images to **Azure Container Registry (ACR)** upon successful builds.

### 4. Docker and YAML Customization:
- Customized **Docker** and **pipeline YAML files** to ensure triggers for each microservice, optimizing build processes and reducing unnecessary builds.
- Validated and successfully ran pipelines, demonstrating robust CI practices by triggering builds upon code changes.

### 5. CI Integration and Validation:
- Ensured seamless CI integration by automating validation and verifying changes with Docker image updates.
