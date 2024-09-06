# Azure Networking and Security Project

## Project Overview

This project demonstrates the design and implementation of a secure network architecture in Azure. The setup includes Virtual Networks (VNet), Azure Firewall, Bastion, Virtual Machine (VM), and an Nginx web application. 
The project highlights secure access to the VM through a Bastion host and external traffic routing using Azure Firewall.

## The architecture project will A VNet will be implemented and it will contain subnets & one subnet will be having the VM with the app in it. A firewall will be placed to filter traffic for the VNet. Also, a Bastion host will be used in a specific subnet to securely access the VM. When a user tries to reach the app, user will be reaching the firewall and then directed to the VM.

## Steps Performed

### 1. Resource Group, Virtual Network (VNet) and Subnets Setup
- Created a resource group as the first step to manage all the resources, services and instances with one identity.
- Created a Virtual Network (VNet)
  - Enabled Bastion host while creating a public IP.
  - Enabled Firewall with allowing to create a new Firewall policy for my requirements.
  - Allowed the CIDR of the VNet to be default with multiple subnets. Subnets were automatically created and left them in place. The subnets include:
    - **Azure Bastion Subnet**: To access the Bastion host and enable secure access to the VM.
    - **Azure Firewall Subnet**: For the Firewall functions.
    - **Default Subnet** [Webapp Subnet]: Used for hosting the Virtual Machine (VM). 
    - **Firewall Manager Subnet**: Auto-created to manage the firewall.

### 2. Provisioning Virtual Machine (VM) in Default Subnet
- Deployed a VM in the same resouce group, allowed SSH and created a new key pair for access. (Default region and free service eligible Ubuntu image)
- Under networking selected Default Subnet with the created VNet. Disabled the Public IP to access the VM with a private IP to ensure the security.
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
