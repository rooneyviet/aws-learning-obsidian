# Amazon CloudWatch

## What It Is

Amazon CloudWatch is AWS’s monitoring and observability service for metrics, logs, alarms, dashboards, and event-driven operational workflows.

## Why It Exists

Operating systems need telemetry to detect failures, capacity issues, performance regressions, and anomalous behavior.

## Core Concepts

- Metrics and custom metrics
- Logs and log groups
- Alarms
- Dashboards
- Logs Insights
- Integration with EventBridge and Auto Scaling

## How It Works

AWS services publish metrics automatically. Applications and agents can publish logs and custom metrics. Alarms evaluate thresholds or anomaly detection and trigger actions.

## When To Use

Use CloudWatch for production observability, centralized log collection, infrastructure metrics, and operational alarms.

## When Not To Use

Do not treat CloudWatch as your only deep distributed tracing tool; pair it with [[AWS X-Ray]] or OpenTelemetry-based tracing when needed.

## Common Use Cases

- CPU and memory alarms
- Log retention and search
- Application error dashboards
- Event-driven remediation

## Security And Operations Considerations

Log ingestion and retention can become expensive. High-cardinality custom metrics cost more and can become noisy. Set retention intentionally.

## Common Mistakes

- Keeping all logs forever by default
- Alarm fatigue from poor thresholds
- Not correlating metrics, logs, and traces

## Practical Example

An API stack sends ALB metrics, app logs, custom latency metrics, and alarms into CloudWatch. On alarm, EventBridge triggers an automated diagnostic workflow.

## Related Notes

- [[AWS X-Ray]]
- [[AWS Systems Manager]]
- [[AWS Health]]
