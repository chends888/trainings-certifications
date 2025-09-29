# AWS Study Notes

## Cloud & Payment Models
- **Most common cloud model**: Client-server model
- **AWS payment model**: Pay-as-you-go

## AWS Cloud Concepts
- On-demand resources: scale up and down rapidly to optimize costs and revenue
- Contain IT resources: repetitive tasks everyone needs
- Easier to go global depending on business needs

---

## Amazon EC2
Elastic Compute Cloud provides flexible compute resources.

- On-premise–like, customizable compute power
- Choose operating system, web apps, databases, networking
- Controlled networking

### EC2 Instance Types
- **General Purpose**: balances compute, memory, networking
- **Compute Optimized**: gaming, high-performance computing, modeling
- **Memory Optimized**: memory-intensive tasks, large datasets
- **Accelerated Computing**: GPUs, floating-point operations, hardware acceleration
- **Storage Optimized**: high-performance storage workloads

### EC2 Pricing
- **On-Demand**: pay per hour/second, no commitment
- **Savings Plan**: commit for 1–3 years, discounted rates
- **Reserved Instances**: discount applied to predictable usage, 1–3 year terms
- **Spot Instances**: spare capacity, very cheap, can be interrupted
- **Dedicated Host**: physical server, private tenancy, most expensive

---

## Scalability & Load Balancing
- **Scalability**: increase/decrease instances when workload changes  
  - AWS Auto Scaling
  - Backup resources for failover
- **Load Balancing**: distribute workload across instances  
  - AWS Elastic Load Balancing (ELB)  
  - Can distribute frontend and backend workloads → decoupled architecture  

---

## Architectures
- **Tightly coupled**: components depend on each other → fragile
- **Loosely coupled**: independent components → resilient

**Amazon SQS**: send, receive, store messages between components at scale

---

## Containers & Serverless
- **AWS Lambda**: run code without managing servers
- **Amazon ECS/EKS**: run container workloads (Docker/Kubernetes)
- **AWS Fargate**: serverless compute for containers

---

## Regions & Availability
- **Regions**:
  - **Compliance**: keep data within country
  - **Proximity**: reduce latency by being closer to clients
  - **Pricing**: costs differ by region
  - **Feature availability**: not all features are in all regions
- **Availability Zones (AZs)**: multiple isolated data centers per region → disaster resistance
- **Edge locations**: cache content close to customers for lower latency

---

## AWS Management Tools
- **AWS Management Console**
- **AWS CLI**
- **SDKs**
- **AWS Elastic Beanstalk**: auto-deploy applications
- **AWS CloudFormation**: infrastructure as code

---

## Networking
- **VPC**: Virtual Private Cloud → isolate and control networking
- **Virtual Private Gateway**: secure internet routing
- **AWS Direct Connect**: private connection between on-prem and AWS
- **Route 53**: scalable, resilient DNS service
- **NACLs vs Security Groups**:
  - NACLs: stateless, operate at subnet level
  - Security Groups: stateful, operate at resource level (EC2)

---

## Storage & Databases
- **EBS**: block storage (snapshots, complex reads/writes, must be in same AZ)
- **S3**: object storage, multiple tiers (frequent, infrequent, archival), cheapest tier
  - S3 Transfer Acceleration: faster transfers over distance
- **EFS & FSx**: shared file storage, serverless, multi-instance
- **Amazon RDS**: managed relational database (PostgreSQL, MySQL, Oracle, MariaDB, SQL Server)
- **Amazon Aurora**: high-performance, MySQL/PostgreSQL-compatible, continuous backups
- **DynamoDB**: serverless NoSQL key-value DB, millisecond latency
- **Amazon Redshift**: data warehouse for analytics
- **AWS DMS**: database migration
- **Other DB Services**: DocumentDB (MongoDB), ElastiCache (Redis, Memcached), KeySpaces (Cassandra), Neptune (graph DB)
- **AWS Snowball**: physical data transfer device
- **Amazon Athena**: query data directly from S3
- **Amazon SageMaker**: ML platform

> ⚠️ No one-size-fits-all database — pick based on workload.

---

## Security
- **Shared Responsibility Model**: AWS secures infrastructure, you secure applications/data
- **Security Groups**: firewall at instance level
- **NACLs**: firewall at subnet level
- **IAM Roles**: grant temporary, scoped permissions (preferred over IAM users)
- **AWS KMS**: encryption key management
- **Amazon Inspector**: vulnerability scanning
- **Amazon GuardDuty**: threat detection
- **AWS Shield**: DDoS protection
- **AWS Secrets Manager**: manage secrets, credentials, keys
- **Amazon Macie**: detect sensitive data in S3
- **Amazon Detective**: ML-driven resource investigation

---

## Monitoring & Compliance
- **Amazon CloudWatch**: monitoring, dashboards, alerts
- **AWS CloudTrail**: records API calls, audits
- **AWS Trusted Advisor**: checks against cost, security, reliability, performance, limits
- **AWS Config**: compliance monitoring, tracks resource changes
- **AWS Artifact**: compliance reports

---

## Billing & Cost Management
- **Consolidated Billing**: across accounts
- **AWS Budgets**: set and monitor spend limits
- **AWS Cost Explorer**: visualize and analyze costs
- **Savings Plans**: commit for discounts
- **AWS Marketplace**: third-party apps and services

---

## Well-Architected Framework
1. **Operational Excellence**: automate processes, deliver changes reliably. Exam tip: the possibility to automate changes to reduce risk and improve delivery
2. **Security**: manage permissions, protect confidentiality, alerts
3. **Reliability**: build resilient, distributed systems, plan for failure. Exam tip: system will fail, how will you design the system with that in mind?
4. **Performance Efficiency**: optimize performance, use new services
5. **Cost Optimization**: scale efficiently, control spending. Exam tip: use AWS services to not overspend

6. **Sustainability**: efficient resource use, minimize carbon footprint

---

## Disaster Recovery
- **HA (High Availability)**: replicate components, keep workloads running
- **DR (Disaster Recovery)**: replicate entire workloads, plan for disasters
- Use multiple regions for resilience

---

## Support Plans
- **Business Plan**: includes Trusted Advisor best practices
- **Enterprise On-Ramp**: adds Technical Account Manager
- **Enterprise**: full dedicated support

---

## Governance & Adoption
- **Principle of Least Privilege**: minimal permissions required
- **AWS Cloud Adoption Framework (CAF)**: organization-wide cloud adoption strategy

---

## AI/ML & Analytics
- **Analytics Services**: data collection, visualization, streaming, transformations
- **AWS Systems Manager**: incident management, runbooks, ops management
