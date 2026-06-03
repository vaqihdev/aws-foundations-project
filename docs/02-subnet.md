# Public and Private Subnets

## Overview

This project implements both public and private subnets to separate internet-facing resources from internal resources. This approach follows common AWS networking and security best practices.

## CloudFormation Resources

```yaml
PublicSubnet:
  Type: AWS::EC2::Subnet

PrivateSubnet:
  Type: AWS::EC2::Subnet
```

## Configuration

| Subnet         | CIDR Block  | Purpose                         |
| -------------- | ----------- | ------------------------------- |
| Public Subnet  | 10.0.0.0/24 | Hosts internet-facing resources |
| Private Subnet | 10.0.1.0/24 | Hosts internal resources        |

## Architecture Role

```text
VPC
├── Public Subnet
│   ├── EC2 Instance
│   └── NAT Gateway
│
└── Private Subnet
    └── Internal Resources
```

## Why This Configuration?

Separating workloads into public and private subnets improves security and network organization. Public resources can receive internet traffic, while private resources remain isolated from direct external access.

## Skills Demonstrated

* AWS Networking
* Subnet Design
* CIDR Allocation
* Network Segmentation
* CloudFormation

## Key Takeaways

This implementation demonstrates how subnet separation can improve security and create a scalable cloud network architecture.
