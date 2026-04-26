---
title: Amazon EBS
tags:
  - aws
  - storage
  - block-storage
aliases:
  - EBS
---

# Amazon EBS

## What It Is

Amazon EBS is AWS's persistent block storage service for EC2 instances. It provides virtual disks that you attach to instances.

## Why It Exists

Applications often need disk-like storage with low latency and filesystem support. Object storage like [[Amazon S3]] is not suitable for boot volumes or database disks.

## Core Concepts

- Volumes
- Availability Zone scope
- Snapshots
- Volume types
- Boot volumes

## How It Works

EBS volumes are presented to EC2 like disks. The instance formats and mounts them with a filesystem.

```mermaid
flowchart LR
    EC2[EC2 Instance] --> EBS1[EBS Root Volume]
    EC2 --> EBS2[EBS Data Volume]
    EBS1 --> SNAP[Snapshot]
    EBS2 --> SNAP
```

## When To Use

Use EBS for boot disks, database storage, low-latency block storage, and persistent application volumes for EC2.

## When Not To Use

Do not use EBS when you need shared filesystem access by many instances, object storage access patterns, or multi-region native storage.

## Common Use Cases

- EC2 root volumes
- Self-managed databases on EC2
- Transactional workloads
- Backup snapshots for disaster recovery

## Cost And Operations

Main cost drivers are provisioned storage size, performance level, and snapshots. Monitor IOPS, throughput, and queue length, and snapshot regularly.

## Common Mistakes

- Assuming EBS is multi-AZ
- Forgetting snapshots are separate from the live volume
- Under-sizing IOPS for databases
- Expecting multiple instances to share one normal volume like a filesystem

## Practical Example

A self-managed PostgreSQL database runs on EC2 with one EBS volume for the OS, one high-performance EBS volume for database data, daily snapshots, and monitoring on volume latency.

## Related Notes

- [[Amazon EFS]]
- [[Amazon FSx]]
- [[Amazon RDS]]
