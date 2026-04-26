---
title: AWS CloudHSM
tags:
  - aws/security
  - aws/crypto
aliases:
  - CloudHSM
---

# AWS CloudHSM

## What It Is

[[AWS CloudHSM]] is AWS's managed hardware security module service. It gives you dedicated HSM appliances in AWS VPCs so you can generate, store, and use cryptographic keys inside hardware you control at the crypto layer.

## Why It Exists

Some workloads need stronger control or compatibility than [[KMS]] provides. Examples include regulatory requirements for dedicated HSM tenancy, support for specific cryptographic APIs, or legacy applications that expect PKCS#11, JCE, or OpenSSL-style HSM integration.

## Core Concepts

- Dedicated HSMs
- Cluster
- Crypto users and admins
- Client integration
- Backups and synchronization

## How It Works

You provision a CloudHSM cluster inside your VPC. AWS manages the infrastructure availability of the appliances, but you manage users, keys, and crypto operations. Your applications connect using supported client libraries.

```mermaid
flowchart LR
    A[Application] --> B[CloudHSM client library]
    B --> C[CloudHSM cluster]
    C --> D[Dedicated HSMs]
```

## When To Use

Use [[AWS CloudHSM]] when you need dedicated HSM tenancy, customer control of HSM users and key hierarchy, legacy crypto integrations, or compliance requirements that explicitly call for customer-controlled HSM-backed keys.

## When Not To Use

Do not use CloudHSM just because encryption sounds important. For most AWS-native storage and service encryption, [[KMS]] is far simpler, cheaper, and better integrated.

## Common Use Cases

- Enterprise PKI and private CA systems
- Code-signing or document-signing platforms with HSM requirements
- Migration of applications built around PKCS#11

## Security And Operations Considerations

CloudHSM shifts more responsibility to you. Plan quorum, credential handling, backup expectations, client high availability, and cluster scaling. Put HSMs in multiple Availability Zones.

## Common Mistakes

- Choosing CloudHSM when KMS would meet the requirement
- Underestimating operational ownership
- Failing to design HA across AZs and client paths
- Assuming AWS manages crypto-side admin lifecycle for you

## Practical Example

A company operates an internal certificate authority used to sign device certificates for industrial hardware. Auditors require dedicated HSM control and the CA software expects PKCS#11. The team deploys a CloudHSM cluster across two Availability Zones and keeps CA signing keys inside the hardware boundary.

## Related Notes

See also [[KMS]], [[ACM]], [[IAM]], [[AWS CloudTrail]], and [[AWS Security Hub]].
