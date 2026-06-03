# Internet Gateway

## Overview

An Internet Gateway (IGW) enables communication between resources inside the VPC and the public internet. It is a highly available AWS-managed component that serves as the entry and exit point for internet traffic.

## CloudFormation Resource

```yaml
IGW:
  Type: AWS::EC2::InternetGateway
```

## Configuration

```yaml
VPCtoIGWConnection:
  Type: AWS::EC2::VPCGatewayAttachment
```

## Architecture Role

```text
Internet
    │
    ▼
Internet Gateway
    │
    ▼
Public Route Table
    │
    ▼
Public Subnet
```

## Why This Configuration?

The Internet Gateway allows resources in the public subnet to receive and send internet traffic. Without an IGW, the EC2 instance would not be accessible from outside the VPC.

## Skills Demonstrated

* AWS Networking
* Internet Connectivity
* VPC Architecture
* CloudFormation
* Network Routing

## Key Takeaways

This implementation demonstrates how AWS VPC resources connect to the internet through an Internet Gateway while maintaining controlled network access.
