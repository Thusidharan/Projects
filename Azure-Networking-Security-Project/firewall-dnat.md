Configuring Azure Firewall with DNAT Rules

  - Updated the Firewall policies > Configured Destination Network Address Translation (DNAT) default rule collection (firewall-nginx-rule).
  - Used 'Add Rule' and added the rule to rule to the above rule collection to route external traffic securely.
    > Source - My IP address, assuming only I need access for now. 
    > Destination - Public IP of the Firewall. 
    > Destination port - 4000 (Can setup any port other than the default ones. 
    > Translated IP address - Private IP of the VM 
    > Translated port - 80 (Nginx running port)
  
  - External traffic from a public IP on port 4000 was routed to the VM's private IP on port 80 (default Nginx port).

Verifying the Setup
  - Verified the setup by successfully accessing the hosted Nginx web page through a browser using the public IP of the Firewall and port 4000 (public IP:4000).
  - The secure configuration ensured that only permitted traffic could reach the VM, demonstrating strong Azure networking and security practices.
