# Security Group

## Overview

Security Groups act as virtual firewalls that control inbound and outbound traffic for AWS resources. In this project, a Security Group is attached to the EC2 instance to allow web traffic and remote administration.

## CloudFormation Resource

```yaml
AppSecurityGroup:
  Type: AWS::EC2::SecurityGroup
```

## Configuration

```yaml
SecurityGroupIngress:
  - IpProtocol: tcp
    FromPort: 80
    ToPort: 80
    CidrIp: 0.0.0.0/0

  - IpProtocol: tcp
    FromPort: 22
    ToPort: 22
    CidrIp: 0.0.0.0/0
```

## Allowed Traffic

| Port | Protocol | Purpose           |
| ---- | -------- | ----------------- |
| 80   | TCP      | HTTP Web Traffic  |
| 22   | TCP      | SSH Remote Access |

## Architecture Role

```text
Internet
    │
    ▼
Security Group
    │
 ┌──┴──┐
 │     │
 ▼     ▼
HTTP  SSH
80    22
```

## Why This Configuration?

Port 80 allows users to access the web application hosted on the EC2 instance. Port 22 enables administrators to connect securely using SSH for server management and troubleshooting.

## Security Considerations

For production environments, SSH access should be restricted to trusted IP addresses instead of allowing access from 0.0.0.0/0.

Example:

```yaml
CidrIp: 203.x.x.x/32
```

## Skills Demonstrated

* AWS Security
* Security Group Configuration
* Network Access Control
* EC2 Security
* CloudFormation

## Key Takeaways

This implementation demonstrates how Security Groups can be used to protect AWS resources while allowing only the required network traffic.
