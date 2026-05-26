## AWS VPC with Public & Private Subnets

This AWS CloudFormation template provisions a secure and isolated VPC environment, featuring both public and private subnets, along with a NAT Gateway to provide outbound internet connectivity for instances located in the private subnet.
Architecture

## This template implements the following topology:

    VPC (10.0.0.0/20): An isolated network environment.

    Public Subnet: Designed to host resources that require direct public access (e.g., an EC2 instance with a public IP).

    Private Subnet: Designed to host backend resources that do not require direct internet access.

    NAT Gateway: Enables instances in the private subnet to access the internet for updates (outbound only), while blocking unsolicited inbound connections from the internet.

    Internet Gateway: Provides the gateway for traffic to/from the internet for the public subnet.

## Resources Created

    VPC with DNS support and hostnames enabled.

    Internet Gateway attached to the VPC.

    Public Subnet (with MapPublicIpOnLaunch: true).

    Private Subnet.

    Elastic IP (EIP) & NAT Gateway (deployed in the public subnet).

    Route Tables:

        Public Route Table: Routes 0.0.0.0/0 to the Internet Gateway.

        Private Route Table: Routes 0.0.0.0/0 to the NAT Gateway.

    Security Group: Allows HTTP (80) and SSH (22) access from anywhere.

    EC2 Instance (t3.micro): A sample application server deployed in the public subnet.

## How to Deploy

    Ensure you have the AWS CLI installed and configured with appropriate credentials.

    Run the following command to deploy the template:
    
    aws cloudformation create-stack \
  --stack-name MyLabStack \
  --template-body file://template.yaml \
  --capabilities CAPABILITY_IAM

  You can monitor the deployment progress via the AWS Console > CloudFormation > Stacks.