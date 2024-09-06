# AWS VPC Project: Secure Multi-AZ Deployment with Private Subnets, NAT Gateway, and Load Balancing

## Objective
Designed and implemented a secure and scalable AWS environment using Virtual Private Cloud (VPC) to host web servers in a multi-availability zone setup, ensuring high availability, fault tolerance, and security.

## Key Components and Configuration

### VPC and Subnet Architecture
- Created a custom VPC with both public and private subnets across two Availability Zones (AZs) for high availability.
- Configured public subnets for the NAT Gateway and Bastion Host, and private subnets for the application servers to enhance security.

### Internet Gateway and NAT Gateway
- Attached an Internet Gateway to the VPC for internet connectivity of resources in public subnets.
- Set up a NAT Gateway in the public subnet to enable secure internet access for resources in the private subnets without exposing them to direct inbound internet traffic.

### EC2 Instances and Auto Scaling Group
- Deployed EC2 instances in the private subnets across two Availability Zones using an Auto Scaling Group to automatically manage the scaling of instances based on traffic demands, ensuring resilience and fault tolerance.

### Application Load Balancer (ALB)
- Configured an Application Load Balancer (ALB) to distribute incoming application traffic across EC2 instances in multiple Availability Zones, improving application availability and fault tolerance.
- Set up routing rules to manage traffic flow and ensure seamless user experience.

### Bastion Host for Secure Access
- Deployed a Bastion Host (EC2 instance) in a public subnet to provide secure SSH access to EC2 instances located in private subnets, adding an additional layer of security.

## Security and Management
- Ensured secure management and access by utilizing private subnets for application servers and a Bastion Host for administrative access.
- Configured route tables and security groups to control traffic flow and secure the environment.

## Outcome and Benefits
- Achieved a robust, secure, and scalable AWS infrastructure that ensures high availability and security by leveraging VPC, NAT Gateway, Auto Scaling, and an Application Load Balancer.
- The environment is highly available and can efficiently handle fluctuating traffic loads while keeping the servers secure and private.
