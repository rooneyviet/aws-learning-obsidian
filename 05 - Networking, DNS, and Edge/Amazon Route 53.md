# Amazon Route 53

## What It Is

Amazon Route 53 is AWS’s DNS and domain-related service, supporting public DNS, private DNS, health checks, and traffic routing policies.

## Why It Exists

Applications need reliable name resolution, domain registration, and traffic steering at internet scale.

## Core Concepts

- Hosted zones
- Record types
- Routing policies
- Health checks
- Private hosted zones

## How It Works

Clients ask DNS resolvers for a domain. Route 53 answers based on the hosted zone record and routing policy. Alias records can point to AWS resources like ALBs or CloudFront without CNAME limitations at the zone apex.

## When To Use

Use Route 53 for domain DNS management, internal service discovery via private hosted zones, and simple global traffic steering.

## When Not To Use

When you need network-level traffic acceleration instead of DNS-level routing, consider [[AWS Global Accelerator]].

## Common Use Cases

- `example.com` to CloudFront
- Private hosted zones for internal service names
- Active-passive failover between Regions

## Security And Operations Considerations

Protect registrar and DNS changes with strong IAM and MFA. DNS TTL choices affect failover speed and caching behavior.

## Common Mistakes

- Confusing DNS failover with instant traffic switching
- Bad TTL strategy
- Forgetting split-horizon DNS design for internal and external names

## Practical Example

A company uses Route 53 public hosted zones for public websites and private hosted zones for service names reachable only inside VPCs.

## Related Notes

- [[Amazon CloudFront]]
- [[AWS Global Accelerator]]
- [[Amazon VPC]]
