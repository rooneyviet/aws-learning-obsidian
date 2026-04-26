# AWS Outposts

## What It Is

AWS Outposts brings AWS-managed infrastructure and services into on-premises or edge facilities.

## Why It Exists

Some workloads must stay on-premises for latency, data residency, local processing, or regulatory reasons while still using AWS APIs and operational models.

## Core Concepts

- AWS-delivered rack or server form factors
- Extension of an AWS Region
- Subset of AWS services locally
- AWS-managed hardware lifecycle

## How It Works

Outposts hardware is installed in your site, connected back to an AWS Region, and exposed through familiar AWS control planes. You deploy workloads using AWS constructs, but compute runs physically on-site.

## When To Use

Use Outposts for low-latency local processing, on-premises data residency requirements, or industrial and edge locations that need AWS-consistent operations.

## When Not To Use

Do not use Outposts if a standard Region or Local Zone is enough, or if the services you need are unsupported locally.

## Common Use Cases

- Local analytics
- On-prem VM or container modernization
- Edge inference and control systems

## Security And Operations Considerations

Outposts is a significant architectural and commercial commitment. Parent Region connectivity remains important, and service availability differs from core Regions.

## Common Mistakes

- Assuming full cloud service parity
- Underestimating on-site facility requirements
- Designing without parent Region dependency awareness

## Practical Example

A manufacturing site runs latency-sensitive control applications on Outposts while synchronizing operational data to the parent Region for analysis.

## Related Notes

- [[AWS Local Zones]]
- [[Amazon VPC]]
