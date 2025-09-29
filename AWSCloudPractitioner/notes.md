Most common cloud model: Client-server model

AWS payment model: pay-as-you-go model





Cloud concept: on-demand resources (optimize costs and revenue by rapidly scaling up and down according to demands). Contain IT resources (tasks that are repetitive, and everyone does it). Easier to go global, depending on the business needs.



EC2: on-premise, flexible compute resources. Custom computing power, operating system, web apps, databases, and other software. Controlled networking





EC2 types:

Genral Purpose: balances compute, memory and networking;

Compute Optimized: gaming high performance, modeling, great processor performance;

Memory Optimized: memory intensive tasks, process large datasets in memory;

Accelerated Computing: graphics processing, floating number calculations, utilize hardware acceleration;

Storage Optimized: high performance storage.





EC2 pricing:

On-demand: general purpose, good to have a basic understanding on your average usage

Savings plan: same instances as on-demand but need to be used for 1-3 years

Reserved instances: are a discount applied to your on-demand instances. 1 or 3 year term, steady state usage, predictable usage

Spot instances: spare EC2 computing power, cheap, but processes can be interrupted

Dedicated host: private tenancy, most expensive ones



Scalability

Have backups for when your primary instances fail

Have the possibility of changing the number of active instances when workload increases or decreases.

AWS Auto Scaling





Load Balancing

Distribute workload equally among instances

AWS Elastic Load Balancing

Can distribute workloads among front-end and back-end, creating a decoupled architecture.





Tightly coupled architecture: usually not good, because if one of the components fail, other components could see errors too

Loosely coupled architecture: applications do not depend on each other

Amazon SQS:

Send, receive, store messages between software components at any volume





Containers

AWS Lambda: host code and run it without accessing the underlying server.

Amazon ECS and EKS: run Docker container-based workloads, that run in EC2.

Amazon Fargate: serverless way to run compute.





AWS Regions

Compliance: make sure your data is not being exported to other countries;

Proximity: reduce ping by being closer to clients;

Pricing: regions operate at different costs therefore AWS pricing might differ among regions;

Feature availability: some features might require specific infrastructure operate, some regions might not have all AWS features.





Availability Zones

Run your business in multiple EC2 on multiple AZs, so they are more disaster proof





Edge locations

Locations close to the customers that store data so it can be sent later on to the instance





AWS Management Console

AWS Command Line

SDKs







AWS Elastic Beanstalk: automatically deploy predefined instances

AWS CloudFormation













Networking





VPC: way to organize your instances in a way that only authorized. People can connect and communicate to them

Virtual Private Gateways: more protection to connect clients and server, but still using the same route as regular internet users

AWS Direct Connect: a private connection between clients and servers. Allows your on-premise DB to connect to AWS



Route 53: is AWS’s DNS service, highly available and scalable. Great against DNS attacks



Network ACL: operates at a VPC level. Are stateless, Security Groups are stateful (e.g. if a packet is sent to another subnet and comes back, it does not need to be listed in the security group)

Security Group: operated at a resource level (e.g. EC2)











Storage



EBS: block storage (block of defined size), does not depend on any EC2 instance (can be mounted or not)

Able to create snapshots, in case of disasters

Complex read, write and update

Has to be in the same A.Z. as the EC2 instance

S3: store data as objects. Supports many tiers when access is concerned, be they frequent access or data that need to be stored for many years. The cheapest tier of storage in AWS.

Better for complete object read, write, update

S3 transfer acceleration: accelerates transfering data over long distances

EFS and FSx: serverless filesystem storage

Multiple instances reading and writing at the same time

Any instance within the Region can use it

Amazon RDS: cloud relational database. Compatible to migrate from IBM DB2,  PostgreSQL, MySQL, Oracle, MariaDB, SQLServer. It doesn’t improve performance, just move it to the cloud

Disaster recovery

Redundancy

Many more

Amazon Aurora

Continuous backup to S3

Data recovery

Reduced cost and faster than standard MySQL (5 times) and PostgreSQL (3 times) DBs

Dynamo DB: serverless DB

Non relational

Millisecond response time

Cannot run complex queries

Store key-value

Amazon Redshift: big data analytics

AWS DMS: database migration

Amazon DocumentDB, ElasticCache and KeySpaces: migrate from non-relational DBs: mongoDB, Cassandra, Redis, emcached

Amazon Neptune: graph database

AWS Snowball: physical device that you transfer you data to, then it is transported to an Amazon datacenter, so you don’t need to transfer your data over the network

Amazon Athena: query data in multiple formats (CSV, JSON, Orc, Avro, Parquet).

Amazon SageMaker: data collection, data preparation, inferencing.







There is no one-size-fits-all type DB









Security





AWS shared responsibility model. AWS takes care a part of the security and customer takes care of the other part.

Security groups: act as firewalls for EC2 instances, so you define which ports are allowed of not allowed

Network Access Control Lists (NACLs): act as a firewall but at a subnet level, so all instances under that subnet would be affected.



Roles: identities that allow or deny certain actions. Temporarily give users certain permissions. Prevents you from creating a single IAM user for every person that needs to take actions in your AWS. Usually preferred over creating new IAM Users.



Amazon Key Management Service (KMS): perform encrypted operations

Amazon Inspector: scan for vulnerabilities in instances

Amazon GuardDuty: detects threads in your AWS infrastructure. Analyzes network activity and malicious activity in you account.











Amazon CloudWatch: monitor your instances and other services on AWS and on-premise, can trigger action in case the state is not the desired state. Custom dashboards with metrics



Amazon CloudTrail: records all API calls to/from application and who triggered the actions.

AWS Truster Advisor: service to check resources against:

Cost optimization

Security

Fault tolerance

Performance

Service limits





Amazon Inspector: kind of a scanner for EC2 instances and containers and report vulnerabilities



Amazon Guard Duty: monitor you environment against threats. It monitors CloudTrail Mgmt Events, CloudTrail S3 data events, VPC Flow logs and DNS logs.





AWS Shield:  protection against DDos attacks.



AWS Secrets Manager: manage secrets, api keys, DB credentials. Can do automatic rotations

Amazon Macie: scans S3 for sensitive information and remediate



Amazon Detective: machine learning-driven tool that analyzes all of your AWS resources for you to investigate.





Billing



Consolidated billing for all AWS account of one organization

Budgets: be warned before you hit your set budget

Cost explorer: graphs to see what expenses you had. Expenses can be grouped by many categories

Savings plans: flexible pricing, but you have to commit on using the service for a fixed amount of time (e.g. 1 year)







AWS Marketplace: a place to search and easily use third party apps







Well-architected framework







Operational Excellence

Have insights about processes

Deliver changes to customers quickly and reliably

Exam tip: the possibility to automate changes to reduce risk and improve delivery





Security

Use cloud technologies to improve asset security

Manage permissions

Confidentiality: people who don’t have to access certain data, shouldn’t be able to access it

Security alerts



Reliability

Build architecture that is resilient against changes and failures, good recovery

Distributed design

Exam tip: system will fail, how will you design the system with that in mind?



Performance Efficiency

Design systems with good performance over time

Use new features and technologies as they are released

Use scaling to scale up or down depending on the load



Cost Optimization

Understand spend over time

Scaling according to load

Exam tip: use AWS services to not overspend



Sustainability

Related to Cost Optimization in the sense to use your resources in the most efficient way possible, without overspending

Analyze the carbon footprint of your resources











Disaster Recovery

Related to anticipating a disaster to be able to prevent a mitigate

One possibility is to use multiple AWS regions



HA vs DR

HA is related to replicate specific components, cloud workloads

DR is more related to replicating entire workloads





Support Plans



Basically:

Trusted advisor Best Practices: start having the full support on the Business Plan

Technical Account Manager: start having it from the Enterprise Plan On-Ramp (kind of an intermediate between Business and Enterprise)







Principle of Least Privileged

Giving the least level of permission or a person to execute the needed action





AWS Config: Knows all of your resources, warns you about non-compliant according to rules you define. Also records the changes made



AWS Artifact: Compliance reports.



AWS Cloud Adoption Framework: get your company to adopt cloud as a whole



AI/Machine Learning services



Analytics Services: big data analytics, visualization, streaming data, converting



AWS Systems Manager: incident management, runbooks, operational management