# Internet Gateway (IGW)

## What It Is

An Internet Gateway is a VPC component that allows communication between a VPC and the public internet.

## Why It Exists

VPC resources need a controlled path for internet-bound traffic and inbound public traffic.

## Core Concepts

- Attached to one VPC
- Highly available and horizontally scaled by AWS
- Supports IPv4 and IPv6 internet connectivity
- Works with route tables and public IP addressing

## How It Works

A subnet becomes effectively public when its route table has `0.0.0.0/0` to the IGW and the instance has a public IPv4 address or Elastic IP.

## When To Use

Use an IGW for public-facing load balancers, bastion hosts, instances that must accept inbound internet traffic, or public egress for intentionally public resources.

## When Not To Use

Do not use it for private application or database tiers. For outbound-only internet access from private subnets, use [[NAT Gateway and NAT Instances]].

## Common Use Cases

- ALB in public subnets
- Web servers with public IPs
- Public API ingress

## Security And Operations Considerations

The IGW itself has no hourly charge. Security still depends on route tables, security groups, and NACLs. Public exposure should be minimized.

## Common Mistakes

- Thinking an IGW alone makes instances public
- Forgetting public IP assignment
- Putting sensitive workloads behind an IGW route

## Practical Example

An ALB in a public subnet receives internet traffic through an IGW and forwards it to EC2 instances in private subnets.

## Related Notes

- [[Amazon VPC]]
- [[VPC Route Tables]]
- [[NAT Gateway and NAT Instances]]
- [[Security Groups]]
