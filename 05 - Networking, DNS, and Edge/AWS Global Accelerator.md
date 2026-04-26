# AWS Global Accelerator

## What It Is

AWS Global Accelerator provides static anycast IPs and routes users onto the AWS global network to the optimal healthy regional endpoints.

## Why It Exists

DNS-based routing can be slow to adapt, and internet paths to endpoints can vary. Global Accelerator improves performance and failover at the network layer.

## Core Concepts

- Two static anycast IP addresses
- Endpoint groups in Regions
- Health checks and traffic dials
- ALB, NLB, EC2, and EIP-backed endpoints

## How It Works

Clients connect to a static IP announced globally. AWS routes traffic to the nearest edge and then across the AWS backbone to the best healthy endpoint group.

## When To Use

Use Global Accelerator for low-latency global applications, fast regional failover, static IP requirements, and TCP or UDP workloads.

## When Not To Use

Do not use it when simple DNS-based global routing is enough or when CDN caching is the primary need; use [[Amazon CloudFront]].

## Common Use Cases

- Multi-region API endpoints
- Global gaming backends
- Region failover with stable client IP targets

## Security And Operations Considerations

Global Accelerator adds service cost versus pure DNS routing but is useful when clients need allowlisted static IPs. It works well with Shield and regional security controls.

## Common Mistakes

- Confusing it with CloudFront
- Expecting content caching
- Not testing failover behavior

## Practical Example

A global API uses Global Accelerator in front of two regional ALBs so traffic can fail over quickly if one Region becomes unhealthy.

## Related Notes

- [[Amazon Route 53]]
- [[Amazon CloudFront]]
