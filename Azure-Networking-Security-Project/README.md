# Azure Networking and Security Project

## Project Overview

This project demonstrates the design and implementation of a secure network architecture in Azure. The setup includes Virtual Networks (VNet), Azure Firewall, Bastion, Virtual Machine (VM), and an Nginx web application. 
The project highlights secure access to the VM through a Bastion host and external traffic routing using Azure Firewall.

## Steps Performed

### 1. Virtual Network (VNet) and Subnets Setup
- Created a Virtual Network (VNet) with multiple subnets within a Security Group (SG).
- Subnets include:
  - **Azure Bastion Subnet**: Auto-created to enable secure access to the VM.
  - **Azure Firewall Subnet**: Created for routing and security.
  - **Default Subnet**: Used for hosting the Virtual Machine (VM).

### 2. Provisioning Virtual Machine (VM) in Default Subnet
- Deployed a VM inside the **Default Subnet**.
- Accessed the VM using **Azure Bastion**, providing a secure, encrypted connection via its private IP.
  
### 3. Installing Nginx on VM
- Installed **Nginx** on the provisioned VM.
- Configured Nginx to host a simple HTML web page.

### 4. Configuring Azure Firewall with DNAT Rules
- Configured **Destination Network Address Translation (DNAT)** rules to route external traffic securely.
  - External traffic from a public IP on port **4000** was routed to the VM's **private IP** on port **80** (default Nginx port).
  
### 5. Verifying the Setup
- Verified the setup by successfully accessing the hosted Nginx web page through a browser using the public IP and port **4000**.
- The secure configuration ensured that only permitted traffic could reach the VM, demonstrating strong Azure networking and security practices.

## Technologies Used

- **Azure Virtual Network (VNet)**
- **Azure Firewall**
- **Azure Bastion**
- **Virtual Machine (VM)**
- **Nginx Web Server**
- **Security Groups (SG)**
- **DNAT (Destination Network Address Translation)**

## Summary

This project demonstrates the creation and management of a secure Azure network. 
By integrating Azure Firewall and Bastion with private subnets, external access to the virtual machine hosting an Nginx web application was restricted and securely managed. 
This setup verified a solid understanding of Azure networking, firewall configuration, and infrastructure security.
