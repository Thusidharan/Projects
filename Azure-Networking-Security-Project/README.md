# Azure Networking and Security Project

## Project Overview

This project demonstrates the design and implementation of a secure network architecture in Azure. The setup includes Virtual Networks (VNet), Azure Firewall, Bastion, a Virtual Machine (VM), and an Nginx web application. The goal is to securely access the VM via the Bastion host and route external traffic through the Azure Firewall.

## Architecture Design

The architecture involves setting up a VNet containing multiple subnets. A VM is hosted in the default subnet and secured with Azure Firewall and Bastion host. The firewall manages incoming traffic, while the Bastion host provides secure access to the VM without exposing it to public networks. A DNAT rule is configured on the firewall to route external traffic to the Nginx web server running on the VM.

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
- Under networking selected Default Subnet with the created VNet. Disabled the Public IP to access the VM and setup with a private IP to ensure the security.
- Completed the VM creation. Bastion host also got created with the VM due to the settings applied while creating the VNet.
- Accessed the VM using **Azure Bastion**, providing a secure, encrypted connection via its private IP.
  
### 3. Installing Nginx on VM
- Installed **Nginx** on the provisioned VM.
- Configured Nginx to host a simple HTML web page.

### 4. Configuring Azure Firewall with DNAT Rules
- Updated the Firewall policies > Configured **Destination Network Address Translation (DNAT)** default rule collection (firewall-nginx-rule).
-  Used 'Add Rule' and added the rule to rule to the above rule collection to route external traffic securely.
    > Source - My IP address, assuming only I need access for now.
    > Destination - Public IP of the Firewall.
    > Destination port - 4000 (Can setup any port other than the default ones.
    > Translated IP address - Private IP of the VM
    > Translated port - 80 (Nginx running port)
    
  - External traffic from a public IP on port **4000** was routed to the VM's **private IP** on port **80** (default Nginx port).
  
### 5. Verifying the Setup
- Verified the setup by successfully accessing the hosted Nginx web page through a browser using the public IP of the Firewall and port **4000** (public IP:4000).
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
