# Exam AZ-300 & AZ-301 Quick Prep

## Azure Active Directory

| Hybrid Identity Model | Password Hash Sync (PHS) | Pass-Through Auth (PTA) | Federation/ADFS |
| --- | --- | --- | --- |
| PW Store & Auth Flow | Azure AD | On-Prem AD | External/Other Provider |
| Add Resilience With | PTA or Federation | PHS | PHS |
| Seamless SSO | Yes | Yes | No |

## Virtual Machines

| SLA % | Qualifier |
| --- | --- |
| 99.99 | 2+ in 2+ Availability ZONES |
| 99.95 | 2+ in 1 Availability SET |
| 99.9 | 1 w/Premium Disks |

| VM/ASR Disks | Max Size |
| --- | --- |
| OS Disk | 2 TB |
| Data Disk(s) | 4 TB each |

| Availability SET | Default # |
| --- | --- |
| Fault Domains | 2 |
| Update Domains | 5 |

## Storage

| Storage Tier* | Hot | Cool | Archive |
| --- | --- | --- | --- |
| Access Model | Frequent | Infrequent | Rare |
| Starting Option | Yes | Yes | No |
| Minimum Days | 0 | 30 | 180 |
| Lead Time | 0 | 0 | 15 hours |

*\*Note: Understand lifecycle - <https://docs.microsoft.com/azure/storage/blobs/storage-lifecycle-management-concepts#policy>*

| Access Security Level | Account | Container | BLOB |
| --- | --- | --- | --- |
| Shared Access Signature | Yes | No | Yes |
| Access Policy | No | Yes | Yes |

## Data Types & Storage Choices

| Storage Type | Storage BLOB | Storage TABLE | SQL MI/DB/EP | Cosmos DB |
| --- | --- | --- | --- | --- |
| Data Type | Unstructured (Files) | Semi-Structured | Structured (Relational) | Semi-Structured |
| Query Support | REST | REST | SQL | Multiple, including GRAPH |

## SQL Database & Elastic Pool

| DTU SKU | Basic | S0-S2 | S3-S12 | P1-P6 | P11, P15 |
| --- | --- | --- | --- | --- | --- |
| DTU | 5 | 10-50 | 100-3000 | 125-1000 | 1750, 4000 |
| Max Data | 2 GB | 250 GB | 1 TB | 1 TB | 4 TB |

| vCore Gen | 4 | 5 |
| --- | --- | --- |
| vCores | 24 | 80 |
| RAM GB | 168 | 408 |
| Data TB | 1 | 4 |

| vCore SKU | General | Hyperscale* | Critical |
| --- | --- | --- | --- |
| Data IOPS | 7000 | 200k | 200k |
| Data ms | 5-10 | 1-2 | 1-2 |
| Log IOPS | 7000 | 7000 | 200k |
| Log ms | 5-10 | 5-10 | 1-2 |
| Max Data Slider | GenX | 1-4 Replicas | GenX |

*\*Note: Cannot be resized once set*

| Data Security | Tramsparent Data Encryption (TDE) | Dynamic Data Masking (DDM) | Row-Level Security |
| --- | --- | --- | --- |
| When | Always | Mask field DATA in COLUMNS | Filter out ROWS from VIEWS |
| How | Portal - Enabled by default | Portal - Edit masking rule | "SCHEMABINDING=ON" query syntax |

## Network

| LB SKUs | Front Door | Traffic Manager | App Gateway | Load Balancer |
| --- | ---| --- | --- | --- |
| Implemetation | L7-Path | DNS | L7-Path | L4-5tuple |
| Routing Scope | Global | Global | In-Region | In-Region |
| Endpoint  | Public | Public | Public or Internal | Public or Internal |
| Protocols | Web (HTTP/S) | Any | Web (HTTP/S) | Any |
| Sticky Sessions | Cookie | No | Cookie | 2/3tuple |
| Integrated Security | WAF | No | WAF | No |
| Integrated Cache | Yes | No | No | No |
| Outbound Rules | No | No | No | Yes |

## Disaster Recovery

| Time Measure | Represents |
| --- | --- |
| Recovery Point Objective (RPO) | Max acceptable data loss |
| Recovery Time Objective (RTO) | Max acceptable downtime |

## Containers

| Registry SKUs | Basic | Standard | Premium |
| --- | --- | --- | --- |
| Storage GB | 10 | 100 | 500 |
| Webhooks | 2 | 10 | 100 |
| Geo-Replication | No | No | Yes |

| AKS Scaling | Cluster Node | Container Pod |
| --- | --- | --- |
| Horizontal | Cluster Autoscaler | Horizontal Pod Autoscaler (HPA)
| Vertical | Cluster Autoscaler | n/a |

## Events & Messages

| Event or Message | Event | Message |
| --- | --- | --- |
| Data Size | <64k | 64k+ |
| Process before delivery | No | Yes |

| Event Choice | Grid | Hub* |
| --- | --- | --- |
| Handling Use-Case | One-at-a-Time Events | High-Volume Streams |
| Analytics Use-Case | n/a | Big Data Processing |
| Reliability Control | Retry up to 24 hours | Granular via SDK |
| Pricing Model | Per-Event | Capacity & Event |

*\*Note: IoT Hub can also send outbound events to devices

| Messaging Choice | Storage Queue | Service Bus* |
| --- | --- | --- |
| Protocol | REST | Many |
| Max Queue Size | Storage capacity | 80 GB |
| Guarantee | No (must code) | FIFO & Most-at-Once |
| Requires Polling | Yes | No |
| Group into Transactions | No | Yes |
| Batching Support | No | Yes |

*\*Note: Service Bus Topics can support multiple Subscribers

## Code-First (Imperative) Integration

| Choices | WebJobs | Functions |
| --- | --- | --- | --- |
| Trigger Types| Triggered | Multiple |
| Long-Running Type| Continuous (Looping) | No - 5-min timeout |
| Remote Debugging | Only for Continuous | Yes |
| Pricing | App Service Plan | ASP or Consumption |
| ASP-App Integrated | Yes | No |
| JobHost Control | Yes | No |
| Auto-Scale | No | Yes |
| Stateful Type | No | Durable |

## Design-First (Declarative) Integration
| Choices | Logic Apps | Flow|
| --- | --- | --- |
| Users | Devs | Business |
| Granularity | Code | Configuration |

