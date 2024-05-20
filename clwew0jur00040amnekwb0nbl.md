---
title: "Aquila MERN application end to end  a three-tier architecture on AWS."
seoTitle: "Aquila MERN application end to end  a three-tier architecture on AWS."
seoDescription: "Assignmeent for Aquila MERN application end to end  a three-tier architecture on AWS."
datePublished: Mon May 20 2024 11:33:00 GMT+0000 (Coordinated Universal Time)
cuid: clwew0jur00040amnekwb0nbl
slug: aquila-mern-application-end-to-end-a-three-tier-architecture-on-aws
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1716203611744/38fd417c-6dee-40ae-9703-e32fc7e3b9b8.png

---

# Assignment

My task was to setup a three-tier architecture on AWS and deploy the Aquila MERN application on it, while adhering to the following requirements:

1. The web application server's Public IP should remain hidden from the internet and external users, ensuring it is not exposed.
    
2. Developers and internal Users should have the ability to log in to the application and database servers by using the private IP addresses of the servers only.
    

# Let's Begin

1 - Creating a VPC, naming it something identifiable like "Aquila-VPC" and specify an IPv4 CIDR block (e.g., 10.0.0.0/16). This VPC acts as a virtual network for our resources, allowing us to control the IP addressing, subnets, route tables, and gateways.

2 - Next, we create three subnets within the VPC to segment our network into different functional areas:

* **Public Subnet for Load Balancer**: Naming it "Public-Subnet" and assigning an IPv4 CIDR block (e.g., 10.0.1.0/24). This subnet will host resources that need to be accessible from the internet, like load balancers.
    
* **Private Subnet for Application Servers**: Naming it "Private-App-Subnet" and assigning an IPv4 CIDR block (e.g., 10.0.2.0/24). This subnet is for hosting application servers that shouldn't be directly accessible from the internet.
    
* **Private Subnet for Database Servers**: Naming it "Private-DB-Subnet" and assigning an IPv4 CIDR block (e.g., 10.0.3.0/24). This subnet will host our database servers, further isolating them from public access for security reasons.
    

3 - Creating an Internet Gateway and attach it to our VPC. This gateway allows our VPC to communicate with the internet. Naming it "Aquila-IG" and creating a route table named "Public-Route-Table". And add a route to the Internet Gateway (destination 0.0.0.0/0), allowing traffic to and from the internet. Associate this route table with the Public Subnet to enable internet access.

Next, Creating another route table named "Private-Route-Table". This table will be used by the private subnets, isolating them from direct internet access but allowing internal communication within the VPC.

4 - To allow instances in the private subnets to access the internet (for software updates and installation) without exposing them directly, we create a NAT Gateway in the Public Subnet and associate it with an Elastic IP for a static public IP address also updating the Private Route Table to route internet-bound traffic (0.0.0.0/0) to the NAT Gateway.

5 - We setup multiple Security Group:

* Load Balancer Security Group For inbound HTTP traffic (port 80) from anywhere and outbound traffic to port 3010 to the Application Server Security Group. This will ensures that the load balancer can accept web traffic and forward it to the application servers.
    
* Application Server Security Group For inbound traffic from the Load Balancer Security Group on port 3010 and SSH access (port 22) from the Public Subnet IP range for future bastion host access. Allowing outbound traffic to all destinations to enable internet access for updates and other dependencies.
    
* Database Server Security Group For inbound traffic from the Application Server Security Group on the database port (27017) and SSH access (port 22) from the Public Subnet IP range for bastion host access. Allowing outbound traffic to all destinations.
    
* Bastion Host Security Group For inbound SSH traffic (port 22) from a trusted IP and outbound SSH traffic to the private subnets (10.0.2.0/24 and 10.0.3.0/24). This bastion host acts as a secure gateway for accessing your private instances.
    

6 - We Launch EC2 Instances respectively:

* Application Server Launched an EC2 instance in the Private-App-Subnet using the Application Server Security Group. This setup will isolates our application servers from the internet, making them accessible only through the load balancer or bastion host.
    
* Database Server Launched an instance in the Private-DB-Subnet using the Database Server Security Group. This setup ensures that our database is securely accessible only within the VPC.
    
* Bastion Host Launched an instance in the Public-Subnet using the Bastion Host Security Group. The bastion host provides a secure way to access your private instances for management and troubleshooting.
    

7 - Finally , We create a Network Load Balancer (NLB) to distribute incoming traffic across our application server. Naming it "Aquila-NLB", choosing "Internet-facing", and selecting the public subnet. Configuring listeners for TCP (port 80) and associating the Load Balancer Security Group. Creating a target group for the application server, registering their private IP addresse. Setting up listeners to forward TCP traffic from port 80 to the target group on port 3010.

# After setting up the NLB, we go to the "Load Balancers" section in the EC2 dashboard and find the DNS name of the NLB. This DNS name will be the URL for accessing your Aquila web interface.