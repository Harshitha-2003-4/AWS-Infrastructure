# EC2 Instance with Security Group for Drift Detection

This CloudFormation template deploys an Amazon EC2 instance along with a security group configured for SSH access. It is designed for use with AWS CloudFormation Drift Detection to monitor infrastructure changes.

## Resources Created

- **Security Group**: Allows SSH (port 22) access from anywhere (use cautiously).
- **EC2 Instance**:
  - Instance Type: `t2.micro`
  - AMI ID: `ami-075686beab831bb7f` *(Update as per your AWS region)*
  - Security Group: Attached
  - Key Pair: Named `real` *(Ensure it exists in your AWS account)*

## Prerequisites

- AWS CLI configured
- Existing VPC ID
- Existing EC2 Key Pair (`real`) in the selected region
- Valid AMI ID for your region

## Deployment

1. Go to AWS CloudFormation Console.
2. Choose **Create Stack** > **With new resources (standard)**.
3. Upload or paste this template.
4. Provide necessary parameters if using a parameterized version.
5. Deploy the stack.

## Drift Detection

After deployment:

1. Go to **CloudFormation Console**.
2. Select your stack.
3. Choose **Stack Actions** > **Detect Drift**.
4. CloudFormation will compare the actual resources with the template.
5. Any differences (drift) will be reported.

