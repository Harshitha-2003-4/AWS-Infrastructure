# AWS Infrastructure Projects

This repository contains various hands-on AWS infrastructure projects that demonstrate real-world use of core AWS services using Infrastructure as Code (IaC) with YAML/CloudFormation templates.

##  Project Structure
├── ASG-autoscaling-groups
│ ├── ASG.yaml
│ └── Auto-scaling-groups.pdf
├── README.md

##  Projects Included

### 1. **Auto Scaling Group (ASG) Setup**
- **File**: `ASG.yaml`
- **Description**: CloudFormation template to launch a scalable and highly available EC2-based web application using:
  - Launch Templates
  - Auto Scaling Groups
  - Target Groups & Application Load Balancer (ALB)
- **Documentation**: See `Auto-scaling-groups.pdf` for detailed architecture, explanation, and deployment flow.

##  How to Use

1. Sign in to your AWS Console.
2. Go to the **CloudFormation** service.
3. Click on **Create Stack** → **With new resources (standard)**.
4. Upload the `ASG.yaml` template file.
5. Follow the stack creation wizard (specify parameters as required).
6. Monitor the stack creation process and verify resources in the EC2 and Auto Scaling dashboards.

##  Prerequisites

- An active AWS account
- IAM role or user with permissions to use CloudFormation, EC2, VPC, Auto Scaling, and ALB
- (Optional) AWS CLI installed and configured, if deploying via CLI

## 🔧 Deployment via AWS CLI (Optional)

aws cloudformation create-stack \
  --stack-name MyASGStack \
  --template-body file://ASG-autoscaling-groups/ASG.yaml \
  --capabilities CAPABILITY_NAMED_IAM


