# Amazon Kinesis

## What It Is

Amazon Kinesis is a family of services for real-time streaming data ingestion, processing, and delivery. In practice, people often mean Kinesis Data Streams.

## Why It Exists

Some systems produce continuous streams of events that must be processed in near real time and possibly replayed.

## Core Concepts

- Shards and throughput
- Partition keys
- Producers and consumers
- Retention window and replay
- Ordering within a shard
- Enhanced fan-out

## How It Works

Producers write records to a stream. Records are stored durably across shards. Consumers read from shard iterators or via managed integrations like Lambda.

## When To Use

Use Kinesis for clickstream, telemetry, logs, IoT, market data, near real-time analytics, and multiple consumers needing replayable streams.

## When Not To Use

Do not use Kinesis for simple work queues; use [[Amazon SQS]]. For low-volume event routing, use [[Amazon EventBridge]].

## Common Use Cases

- Application telemetry pipelines
- Stream processing with Lambda or Flink
- Real-time dashboards and anomaly detection

## Security And Operations Considerations

Partition-key choice affects hot shards. Monitor iterator age and shard utilization. Costs scale with shards, throughput mode, and retention.

## Common Mistakes

- Choosing hot partition keys
- Treating it like a queue instead of a stream
- Forgetting consumer scaling and replay strategy

## Practical Example

Web applications stream click events into Kinesis. One consumer updates live metrics while another pipeline stores events in a data lake.

## Related Notes

- [[Amazon SQS]]
- [[Amazon EventBridge]]
- [[AWS Glue]]
- [[Amazon Athena]]
