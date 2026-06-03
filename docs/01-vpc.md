# Amazon VPC

## Overview

The Virtual Private Cloud (VPC) serves as the foundational networking layer for this project. It provides an isolated environment where AWS resources can securely communicate with each other while maintaining controlled access to the internet.

## CloudFormation Resource

```yaml
LabVPC:
  Type: AWS::EC2::VPC
```

## Configuration

```yaml
Properties:
  CidrBlock: !Ref LabVpcCidr
  EnableDnsSupport: true
  EnableDnsHostnames: true
```

| Property      | Value       | Description                                   |
| ------------- | ----------- | --------------------------------------------- |
| CIDR Block    | 10.0.0.0/20 | Defines the IP address range for the VPC      |
| DNS Support   | Enabled     | Allows DNS resolution within the VPC          |
| DNS Hostnames | Enabled     | Allows EC2 instances to receive DNS hostnames |

## Architecture Role

The VPC acts as the parent network for all infrastructure components:

```text
VPC
├── Public Subnet
├── Private Subnet
├── Internet Gateway
├── NAT Gateway
├── Route Tables
├── Security Groups
└── EC2 Instance
```

## Why This Configuration?

The selected CIDR range provides sufficient IP address space while maintaining a simple and scalable network structure. DNS support and hostnames are enabled to improve service discovery and instance management.

## Skills Demonstrated

* AWS Networking
* VPC Design
* CIDR Planning
* Infrastructure as Code (CloudFormation)
* Network Isolation
* AWS Architecture Fundamentals

## Key Takeaways

Through this implementation, I gained hands-on experience designing and deploying AWS networking infrastructure using CloudFormation while following basic cloud architecture best practices.
