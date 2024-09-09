Provisioning Virtual Machine (VM) in Default Subnet

    - Deployed a VM in the same resouce group, allowed SSH and created a new key pair for access. (Default region and free service eligible Ubuntu image)
    - Under networking selected Default Subnet with the created VNet. Disabled the Public IP to access the VM and setup with a private IP to ensure the security.
    - Completed the VM creation. Bastion host also got created with the VM due to the settings applied while creating the VNet.
    - Accessed the VM using Azure Bastion, providing a secure, encrypted connection via its private IP.

Installing Nginx on VM

    - Installed Nginx on the provisioned VM.
    - Configured Nginx to host a simple HTML web page.
    - Restarted the Nginx for the changes to get applied.
