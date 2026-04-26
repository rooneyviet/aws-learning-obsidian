# AWS Direct Connect

## What It Is

AWS Direct Connect provides dedicated private network connectivity from on-premises locations to AWS.

## Why It Exists

Internet-based connectivity can have variable latency, security posture, and bandwidth characteristics. Enterprises often want more predictable hybrid connectivity.

## Core Concepts

- Dedicated connection via Direct Connect location or partner
- Private VIF
- Public VIF
- Transit VIF
- BGP routing

## How It Works

Your router connects to AWS at a Direct Connect location or through a partner. BGP exchanges routes. Traffic then reaches VPCs through VGW or TGW attachment patterns.

## When To Use

Use Direct Connect for stable high-bandwidth hybrid connectivity, lower or more predictable latency than internet VPN, and large data transfer workloads.

## When Not To Use

Do not use Direct Connect when you need quick setup or only have small temporary needs. Internet VPN may be sufficient.

## Common Use Cases

- Data center to AWS private access
- Backup and DR replication
- Hybrid application traffic
- Central enterprise WAN connectivity

## Security And Operations Considerations

Dedicated connectivity is not automatically encrypted; add MACsec or VPN overlays if required. Provisioning lead time is longer than VPN, and port and data transfer costs apply.

## Common Mistakes

- Assuming Direct Connect replaces all need for VPN
- Underestimating provisioning lead time
- Poor route filtering or hybrid segmentation

## Practical Example

An enterprise uses Direct Connect plus Transit Gateway to connect multiple AWS VPCs to its corporate network, with Site-to-Site VPN as backup.

## Related Notes

- [[AWS Transit Gateway]]
- [[AWS Site-to-Site VPN and Client VPN]]
