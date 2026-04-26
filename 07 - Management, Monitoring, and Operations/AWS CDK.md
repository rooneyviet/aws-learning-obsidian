# AWS CDK

## What It Is

AWS Cloud Development Kit (CDK) lets you define cloud infrastructure in general-purpose programming languages and synthesize it into CloudFormation.

## Why It Exists

CloudFormation is powerful but can become verbose. CDK adds abstraction, reuse, and code-level composition.

## Core Concepts

- App, Stack, Construct
- L1, L2, and L3 constructs
- `cdk synth`, `cdk diff`, and `cdk deploy`

## How It Works

You write infrastructure code in TypeScript, Python, Java, C#, or Go. CDK synthesizes CloudFormation templates, which are then deployed through CloudFormation.

## When To Use

Use CDK when your team is comfortable with code-based IaC and wants reusable infrastructure patterns.

## When Not To Use

Do not use CDK if the team wants plain declarative templates only or if simple static templates are enough and abstraction adds little value.

## Common Use Cases

- Platform engineering constructs
- Multi-environment app stacks
- Reusable VPC or serverless patterns

## Security And Operations Considerations

CDK still deploys through CloudFormation, so CloudFormation behavior still matters. Abstraction can hide resources if the team does not inspect synthesized templates.

## Common Mistakes

- Treating CDK as magic and not understanding generated resources
- Overengineering shared constructs too early
- Skipping `cdk diff` review

## Practical Example

A team builds a reusable construct for a private ECS service with ALB, logs, alarms, and autoscaling, then reuses it across services.

## Related Notes

- [[AWS CloudFormation]]
- [[Amazon CloudWatch]]
