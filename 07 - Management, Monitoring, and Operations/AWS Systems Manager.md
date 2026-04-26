# AWS Systems Manager

## What It Is

AWS Systems Manager is a collection of operational tools for managing AWS resources and operating systems at scale.

## Why It Exists

Operators need inventory, patching, automation, remote access, parameter storage, and fleet management without relying on direct SSH or RDP access.

## Core Concepts

- Session Manager
- Run Command
- Patch Manager
- State Manager
- Automation
- Parameter Store
- Inventory and Fleet Manager

## How It Works

Managed instances run the SSM Agent and communicate with the Systems Manager control plane. With proper IAM and connectivity, operators can execute commands, open shell sessions, patch systems, and store or retrieve configuration.

## When To Use

Use Systems Manager for fleet operations without bastions, centralized patching and automation, and secure parameter storage.

## When Not To Use

Do not treat Systems Manager as a full secrets-manager replacement for every use case, and do not expect it to work if instances cannot run the SSM Agent or reach SSM endpoints.

## Common Use Cases

- Session Manager shell access
- Patch baselines
- Runbook automation
- Parameter Store for app configs

## Security And Operations Considerations

Prefer SSM access over open SSH ports. Use VPC endpoints for private access. IAM scoping is critical.

## Common Mistakes

- Missing instance IAM role or SSM Agent
- No network path to SSM endpoints
- Overusing plain-text parameters for sensitive secrets

## Practical Example

Private EC2 instances in isolated subnets are managed through Session Manager using interface endpoints, with no inbound SSH allowed.

## Related Notes

- [[AWS PrivateLink]]
- [[Security Groups]]
- [[Amazon CloudWatch]]
