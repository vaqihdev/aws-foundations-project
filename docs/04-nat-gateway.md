# NAT Gateway

## Overview

A NAT Gateway allows resources located in private subnets to access the internet without exposing them to inbound internet traffic.

## CloudFormation Resource

```yaml
NATGateway:
  Type: AWS::EC2::NatGateway
```

## Configuration

```yaml
EIP:
  Type: AWS::EC2::EIP

NATGateway:
  Type: AWS::EC2::NatGateway
```

## Architecture Role

```text
Private Subnet
      │
      ▼
 NAT Gateway
      │
      ▼
Internet Gateway
      │
      ▼
   Internet
```

## Why This Configuration?

Private resources often need internet access for software updates, package downloads, and external API communication. A NAT Gateway provides outbound connectivity while preventing direct inbound access from the internet.

## Skills Demonstrated

* AWS Networking
* NAT Gateway Configuration
* Elastic IP Management
* Private Network Design
* CloudFormation

## Key Takeaways

Using a NAT Gateway improves security by allowing outbound internet access while keeping private resources isolated from direct external connections.
