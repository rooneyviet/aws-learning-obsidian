# AWS Local Zones

## What It Is

AWS Local Zones place selected AWS infrastructure closer to major population centers outside the main AWS Region.

## Why It Exists

Some workloads need lower latency to end users than a distant parent Region can provide.

## Core Concepts

- Extension of a parent Region
- Subset of AWS services
- Low-latency access to users in a metro area

## How It Works

You enable a Local Zone for your account, create subnets in it, and launch supported resources there while still managing them within the parent Region context.

## When To Use

Use Local Zones for latency-sensitive apps near users, media rendering, gaming, VDI, or local content processing.

## When Not To Use

Do not use them if regular Region latency is acceptable or if required services are not available in the Local Zone.

## Common Use Cases

- Real-time gaming servers
- Media and entertainment workflows
- VDI close to end users

## Security And Operations Considerations

Not all services and features are supported. Data transfer patterns between Region and Local Zone matter.

## Common Mistakes

- Assuming full Region service parity
- Ignoring dependency latency back to the parent Region

## Practical Example

A gaming backend places latency-sensitive game servers in a Local Zone while keeping core databases in the parent Region.

## Related Notes

- [[AWS Outposts]]
- [[Amazon VPC]]
