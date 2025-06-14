# Secure Web App in Private Subnet

This project deploys a secure web application on an EC2 instance inside a private subnet. The instance is not accessible directly from the internet. Instead, it is accessed securely through an admin EC2 (bastion host) launched in a public subnet. The setup ensures that only the admin instance can communicate with the private instance using SSH and HTTP protocols.

The infrastructure is provisioned using AWS CloudFormation. It includes a VPC with a public and a private subnet, an internet gateway, route tables, and two EC2 instances: one in the public subnet (admin) and one in the private subnet (web server). The private EC2 has Apache web server installed automatically using user data during launch. 

Security is enforced using two security groups. The admin instance's security group allows SSH access from anywhere, while the private instance's security group allows SSH and HTTP only from the admin security group, effectively restricting all external access.

To view the web app, a secure SSH port forwarding method is used. This allows a user to tunnel into the private instance through the public admin instance and access the Apache server running on the private EC2 from a local browser via localhost.

The folder includes the CloudFormation template, an architecture image, a PDF report, and this README file.
