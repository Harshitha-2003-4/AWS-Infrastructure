# AWS CloudFormation Project: VPC with Public Subnets, EC2 Instances, and Application Load Balancer

This project provisions a secure and scalable AWS infrastructure using CloudFormation. It sets up a Virtual Private Cloud (VPC) with public subnets across two Availability Zones, launches two EC2 instances with Apache web servers, and distributes traffic using an Application Load Balancer (ALB).

---

## 🧱 Architecture Overview

- **VPC** with two **Public Subnets** in separate Availability Zones.
- **Internet Gateway** and **Route Table** for outbound internet access.
- Two **EC2 Instances** (Ubuntu-based) in different subnets with Apache installed via **UserData**.
- **Security Groups** for EC2 and ALB allowing HTTP traffic on port 80.
- An **Application Load Balancer (ALB)** that forwards traffic to both EC2 instances.
- **Target Group** and **Listener** configured to route traffic evenly between the instances.

---

## 📁 Files Included

- `vpc-alb-ec2.yaml` — CloudFormation template for deploying the full stack.
- `README.md` — This documentation file.

---

## 🔧 How to Deploy

### Option 1: Using AWS Management Console

1. Go to the **CloudFormation** service in your AWS Console.
2. Click on **Create Stack** → *With new resources (standard)*.
3. Upload the `vpc-alb-ec2.yaml` file.
4. Specify required parameters (leave defaults or customize as needed).
5. Click **Next**, set stack options if required, then click **Create stack**.
6. Wait for the stack to be created. Look for the **Outputs** tab to get the **Load Balancer DNS Name**.

### Option 2: Using AWS CLI

```bash
aws cloudformation create-stack \
  --stack-name VPC-ALB-EC2-Stack \
  --template-body file://vpc-alb-ec2.yaml \
  --capabilities CAPABILITY_NAMED_IAM
