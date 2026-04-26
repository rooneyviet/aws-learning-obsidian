# AWS Site-to-Site VPN and Client VPN

## What It Is

- Site-to-Site VPN connects a network to AWS over IPsec tunnels.
- AWS Client VPN provides secure remote user access into AWS or connected networks.

## Why It Exists

Organizations need secure connectivity without requiring dedicated private circuits for every use case.

## Core Concepts

- Site-to-Site VPN tunnels, customer gateway, and VGW or TGW
- Static or BGP routing
- Client VPN endpoints and authentication

## How It Works

Site-to-Site VPN establishes redundant encrypted tunnels between on-premises equipment and AWS. Client VPN allows individual users to connect securely from laptops or remote devices into AWS-connected networks.

## When To Use

Use Site-to-Site VPN for fast hybrid setup, backup connectivity for Direct Connect, or branch connectivity. Use Client VPN for remote workforce access and admin access to private environments.

## When Not To Use

Do not rely on VPN as the primary solution for very high-throughput long-term enterprise connectivity when Direct Connect is more suitable.

## Common Use Cases

- Connect branch office to VPC
- Backup connectivity for Direct Connect
- Secure engineer access to private subnets
- Access internal apps from remote laptops

## Security And Operations Considerations

Site-to-Site VPN is encrypted over the internet. Monitor tunnel health and route propagation. Client VPN can become a broad access path if authorization rules are too open.

## Common Mistakes

- Missing return routes
- Not testing tunnel failover
- Overly permissive client VPN authorization
- Treating VPN as zero-trust by default

## Practical Example

A company uses Site-to-Site VPN from a branch firewall to a Transit Gateway and Client VPN for administrators accessing private EC2 instances and internal dashboards.

## Related Notes

- [[AWS Direct Connect]]
- [[AWS Transit Gateway]]
- [[Amazon VPC]]
