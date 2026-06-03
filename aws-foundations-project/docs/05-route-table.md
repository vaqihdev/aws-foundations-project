# Route Tables

## Overview

Route Tables determine how network traffic is directed within the VPC. This project uses separate route tables for public and private subnets.

## CloudFormation Resources

```yaml
PublicRouteTable:
  Type: AWS::EC2::RouteTable

PrivateRouteTable:
  Type: AWS::EC2::RouteTable
```

## Configuration

### Public Route

```yaml
DestinationCidrBlock: 0.0.0.0/0
GatewayId: !Ref IGW
```

### Private Route

```yaml
DestinationCidrBlock: 0.0.0.0/0
NatGatewayId: !Ref NATGateway
```

## Architecture Role

```text
Public Subnet
      │
      ▼
Public Route Table
      │
      ▼
Internet Gateway
```

```text
Private Subnet
      │
      ▼
Private Route Table
      │
      ▼
NAT Gateway
      │
      ▼
Internet Gateway
```

## Why This Configuration?

Using separate route tables allows public resources to communicate directly with the internet while private resources access the internet only through a NAT Gateway.

## Skills Demonstrated

* AWS Routing
* VPC Networking
* Route Table Configuration
* Public and Private Network Design
* CloudFormation

## Key Takeaways

Route tables are a critical networking component that control traffic flow and enforce network segmentation within AWS environments.
