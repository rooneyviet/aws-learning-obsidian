# Amazon SNS

## What It Is

Amazon Simple Notification Service (SNS) is a managed publish-subscribe messaging service.

## Why It Exists

One publisher often needs to notify many subscribers with minimal coupling. SNS handles fan-out efficiently.

## Core Concepts

- Topics
- Publishers and subscribers
- Fan-out to SQS, Lambda, HTTP/S, email, SMS, and mobile push
- Standard and FIFO topics

## How It Works

A publisher sends a message to an SNS topic. SNS delivers copies to all subscribed endpoints according to subscription type and policies.

## When To Use

Use SNS for fan-out notifications, event distribution to multiple consumers, and alerting or machine-to-machine notifications.

## When Not To Use

If you need durable per-consumer pull processing with independent retry control, use SQS subscriptions or SQS directly. If you need advanced event filtering and SaaS/event bus patterns, use [[Amazon EventBridge]].

## Common Use Cases

- Alerting pipelines
- Publish once to trigger multiple downstream processors
- Fan-out from one event source to multiple SQS queues

## Security And Operations Considerations

Use topic policies carefully for cross-account publishing. Encrypt sensitive topics. Subscription confirmation and delivery policies matter.

## Common Mistakes

- Using SNS alone where durable queue semantics are needed
- Not using SQS subscriptions for durable fan-out
- Overusing email or SMS for machine workflows

## Practical Example

An order service publishes `OrderCreated` to SNS. One SQS queue handles invoicing, another updates analytics, and a Lambda sends a confirmation email.

## Related Notes

- [[Amazon SQS]]
- [[Amazon EventBridge]]
