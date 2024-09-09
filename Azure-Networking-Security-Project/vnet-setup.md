Resource Group, Virtual Network (VNet) and Subnets Setup

  - Created a resource group as the first step to manage all the resources, services and instances with one identity.
  - Created a Virtual Network (VNet)
      > Enabled Bastion host while creating a public IP.
      > Enabled Firewall with allowing to create a new Firewall policy for my requirements.
      > Allowed the CIDR of the VNet to be default with multiple subnets. Subnets were automatically created and left them in place. The subnets include:
          - Azure Bastion Subnet: To access the Bastion host and enable secure access to the VM.
          - Azure Firewall Subnet: For the Firewall functions.
          - Default Subnet [Webapp Subnet]: Used for hosting the Virtual Machine (VM).
          - Firewall Manager Subnet: Auto-created to manage the firewall.
