# Security Groups

## What It Is

Security Groups are stateful virtual firewalls attached to ENIs, instances, and certain managed resources.

## Why It Exists

AWS needs a simple, identity-like network security model that controls allowed inbound and outbound traffic close to the resource.

## Core Concepts

- Stateful behavior
- Allow rules only
- Attached to ENIs and resources, not subnets
- Security group references

## How It Works

When traffic reaches a resource ENI, AWS evaluates the associated security groups. If an inbound rule allows the traffic, the connection is established. Return traffic is automatically allowed.

## When To Use

Use Security Groups for nearly all EC2, RDS, load balancer, and endpoint access control.

## When Not To Use

If you need explicit deny behavior at subnet level, use [[Network ACLs (NACLs)]].

## Common Use Cases

- Allow `443` from the internet to an ALB
- Allow app servers to reach DB on `5432` or `3306`
- Allow SSH only from a management subnet or use Systems Manager instead

## Security And Operations Considerations

Prefer SG-to-SG references over CIDR rules when possible. Review unused or overly permissive security groups regularly.

## Common Mistakes

- Using `0.0.0.0/0` on sensitive ports
- Reusing one SG for unrelated workloads
- Assuming SG order matters

## Practical Example

An ALB security group allows inbound `443` from the internet, an app security group allows inbound `8080` from the ALB SG, and a DB security group allows inbound `5432` from the app SG.

## Related Notes

- [[Amazon VPC]]
- [[VPC Subnets]]
- [[Network ACLs (NACLs)]]
- [[AWS Systems Manager]]
