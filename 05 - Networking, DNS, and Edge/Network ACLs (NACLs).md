# Network ACLs (NACLs)

## What It Is

A Network ACL is a stateless firewall applied at the subnet boundary.

## Why It Exists

It provides coarse subnet-level traffic filtering, including explicit deny rules, independent of resource-level security groups.

## Core Concepts

- Stateless behavior
- Ordered rules
- Allow and deny rules
- Associated with subnets

## How It Works

Traffic entering or leaving a subnet is checked against the NACL rules in order. Because NACLs are stateless, both inbound and outbound ephemeral ports often need explicit allowance.

## When To Use

Use NACLs for additional subnet-level guardrails, explicit deny scenarios, or broad segmentation.

## When Not To Use

Do not use NACLs as the primary security control for most workloads when security groups are sufficient and simpler.

## Common Use Cases

- Blocking known malicious CIDR blocks
- Adding a subnet-level control around public-facing tiers
- Enforcing coarse egress restrictions

## Security And Operations Considerations

NACLs are easy to misconfigure because of stateless behavior. Handle ephemeral ports carefully.

## Common Mistakes

- Forgetting return traffic rules
- Writing overly broad deny rules
- Treating NACLs like Security Groups

## Practical Example

A public subnet NACL allows inbound `80/443`, allows ephemeral return traffic, and denies a suspicious external CIDR block.

## Related Notes

- [[Security Groups]]
- [[VPC Subnets]]
- [[VPC Route Tables]]
