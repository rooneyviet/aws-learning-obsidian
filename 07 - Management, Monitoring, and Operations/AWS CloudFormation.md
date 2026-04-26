# AWS CloudFormation

## What It Is

AWS CloudFormation is infrastructure as code for defining and provisioning AWS resources using declarative templates.

## Why It Exists

Manual console changes are slow, inconsistent, and hard to reproduce. Infrastructure should be versioned, reviewable, and repeatable.

## Core Concepts

- Templates in YAML or JSON
- Stacks
- Parameters, Outputs, Conditions, and Mappings
- Change sets
- Drift detection
- Stack policies and nested stacks

## How It Works

You submit a template. CloudFormation compares desired resources to actual state, creates a dependency graph, and provisions or updates resources in order.

## When To Use

Use CloudFormation for repeatable infrastructure deployments, environment consistency, change review, and automation.

## When Not To Use

Do not force CloudFormation onto one-off experiments the team will not maintain, or dynamic imperative provisioning logic that fits better in higher-level tools.

## Common Use Cases

- VPC stacks
- Application infrastructure deployment
- Baseline account resources

## Security And Operations Considerations

CloudFormation itself has no extra charge, but created resources do. Stack rollback behavior matters. Protect critical resources with deletion policies.

## Common Mistakes

- Hardcoding values instead of parameterizing or composing
- Large monolithic templates with poor modularity
- Ignoring drift between console changes and templates

## Practical Example

A team defines ALB, Auto Scaling, RDS, and IAM roles in one stack so dev, staging, and prod environments stay consistent.

## Related Notes

- [[AWS CDK]]
- [[AWS Systems Manager]]
