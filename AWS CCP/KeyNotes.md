# AWS Key Notes for Main Services (Key Words for each services)
## Table of Contents(TOC)

  
- [AWS Key Notes for Main Services (Key Words for each services)](#aws-key-notes-for-main-services-key-words-for-each-services)
  - [Table of Contents(TOC)](#table-of-contentstoc)
    - [Core Services](#core-services)
  - [EC2 Pricing Models:](#ec2-pricing-models)
    - [ON-DEMAND:](#on-demand)
    - [ON-DEMAND:](#on-demand-1)
    - [RESERVED-INSTANCE:](#reserved-instance)
    - [SPOT INSTANCES:](#spot-instances)
    - [DEDICATED INSTANCES:](#dedicated-instances)
    - [SAVINGS PLANS:](#savings-plans)
  - [S3 Classes:](#s3-classes)
  - [SNOW FAMILY:](#snow-family)
  - [STORAGE SERVICES:](#storage-services)
  - [DATABSE SERVICES:](#databse-services)
  - [AWS WELL-ARCHITECTED DESIGN PRINCIPLES:](#aws-well-architected-design-principles)
    - [1) Operational Excellence:](#1-operational-excellence)
    - [2) Security:](#2-security)
    - [3) Reliability:](#3-reliability)
    - [4) Performance Efficiency:](#4-performance-efficiency)
    - [5) Cost Optimization:](#5-cost-optimization)
  - [COMPLIANCE PROGRAMS:](#compliance-programs)

### Core Services
**Trusted Advisor:** Recommends you regarding cost optimisation, performance, fault tolerence, security.

**Personal Health Dashboard:** Detects/Shows if any issues or outages available or affecting use of aws services. Provides Alerts & Guidance for AWS Events that might affect your environment.

**AWS Config:** Auditing and Recording compliance of aws resouces.

**CloudWatch:** Metrics and ALARMS are presented. You can set the metrics and alarm accordingly and can view the logs of the services.

**AWS Budgets:** For ALERTS, and setting budgets for services/costs.

**CloudTrail:** API calls, Audit & Events

**Inspector:**
Runs on EC2 and scans if any vulnerabilities in OS or Application.

**AWS Outpost:** Rack of servers running AWS Infrastructure on Physical Location.

**Artifacts:** Provides Documentation.

**AWS Macie:** Monitors S3 Data Access activity for anomalies and Generates Detailed ALERTS when DETECTS RISK of UNAUTHORIZED access. (Security Detection ML Service), Analyzes CLoudTrail Logs.

**Amazon Polly:** Text to Life like Speech

**Elastic Beanstalk:** For deploying services.

**EC2 Instance - Dedicated Hosts:** Physical Server, Software licsense, address compliance requirements & reduce costs.

**AWS Services for Chef & Puppet:**
-> OpsWorks

**EC2 Spot Instances**: Infrequent access

**Security Groups:** Acts as a firewall at **Instance Level**

**ACLs:** Acts as a firewall at **Subnet level** 

**Amazon GuardDuty:** Threat Detection service that continuously monitors your AWS accounts and
workloads for malicious activity

**Amazon Inspector:** automated vulnerability management service that continually SCANS AWS workloads for
*SOFTWARE VULNERABILTIES*.

**Amazon Macie:** Fully managed Data Security and Data Privacy Service that uses machine learning and
pattern matching to discover and protect your sensitive data in AWS

**AWS Shield:** Managed Distributed Denial of Service **(DDoS) protection service** that safeguards applications running on AWS

## EC2 Pricing Models:

### ON-DEMAND:  
-> PAYG	Model (Pay-As-You-Go)
-> No upfront payment
-> No long-term commitment
-> Where the workload is - spikey, short-term & Unpredictable.
-> By-default this is been selected.
-> Estimated by Hourly Rate.

### ON-DEMAND: 
- PAYG	Model (Pay-As-You-Go)
- No upfront payment
- No long-term commitment
- Where the workload is - spikey, short-term & Unpredictable.
- By-default this is been selected.
- Estimated by Hourly Rate.

### RESERVED-INSTANCE:
- Predictable, Steady-State, Reserved Capacity.
- The longer the term, the greater the savings. (1 or 3 years of contract)
- STANDARD    - upto 75% of reducing costs compared to On-Demand.
- CONVERTIBLE - upto 54% of reducing costs compared to On-Demand.
**Payment Methods**
- All upfront (Pre paid): Full payment at the start of the term
- Partial Upfront       : Some amount has to be payed then remaining is been discounted at hourly rate while billing
- No Upfront            : all is discounted at hourly rate regardless of Reserved Instance.
- RIs can be shared between multiple accounts
- Unused RIs can be sold in Reserved Instance Marketplace.

### SPOT INSTANCES:
- Unused compute capacity (Idle Servers).
- Discount of 90% compared to On-Demand.
- Flexible STRAT & END Time of applications.
- Feasible at very LOW COMPUTE COST.
- Load Balancing, Flexible & Big Data Workloads.

  **AWS BATCH:** very convinient to use with SPOT. (Commonly we use Spot with AWS BATCH).
  - If Terminated by AWS   : won't be charged for partial hour of usage.
  - If Terminated by USER  : will be charged for an hour that we use.

### DEDICATED INSTANCES:
- To meet Regulatory requirements.
- Here we have - Multi Tenant & Single Tenant
   - Multi Tenant: Virtual Isolization
   - Single Tenant: Physical Isolization
- Dedicated can be offered:
   - On-demand
   - Reserved (upto 60% savings)
   - Spot (upto 90% savings)
- Used When: Security concern, don't want to share same hardware with AWS Customers.

### SAVINGS PLANS:
- Similar t Reserved Instances but Simplidies purchasing process.
- Have 3 typesof saving plans:
   - Compute Saving Plan-> flexoble & reduces cost upto 66%
   - EC2 Instance Saving Plan-> Provides lowest prices offering saving upto 72%
   - SageMaker(ML Service that uses ML EC2 Instances) Saving Plan-> Reduces costs upto 64%.

## S3 Classes:
- **S3 Standard(default) -** Fast, 99.99% Availability, Replicated across 3 AZs.
- **S3 Intelligent Tiering -** Uses ML to analyze object usage.
- **S3 Standard IA(Infrequent Access) -** Still Fast, CHEAPER if we access files LESS THAN ONCE A MONTH. 50% Less than STANDARD.
- **S3 One-Zone-IA -** Objects exists in only 1 AZ. 99.5% Availability, 20% Cheaper than Standard IA. Don't have duplicated data to retrieve it as it's in single AZ.
- **S3 Glacier -** for Long-Term Cold Storage. Very Cheap. Retrieval can take minutes to hours. Used for- Archiving & Long-term Backup.
- **S3 Glacier Deep Archive -** Lowest Cost storage, Data Retrieval is 12 hours.
- **S3 Outposts -** has it's own storage class.

## SNOW FAMILY:
- Storage & compute devices used to PHYSICALLY MOVE DATA IN or OUT the CLOUD. 
  - **Snowcone     :** 8TB(HHD); 14TB(SSD)
  - **Snowball Edge:** Storage Optimized(80TB); Compute Optimized(39.5TB)
  - **Snowmobile   :** 100PB of Storage.
- **Snowball** is for PetaBytes of storage-----(no more used, aka - Snowball Edge).

## STORAGE SERVICES:

**-> Simple Storage Service(S3)   -** Serverless OBJECT Storage Service.

**-> S3 Glacier                   -** Cold Storage Services, for archiving & long-term backup.

**-> Elastic Block Store(EBS)     -** Persistent Block Storage Service (virtual hard drive).

**-> Elastic File Storage(EFS)    -** Cloud Native NFS Files System service (When you need to share files between multiple servers).

**-> Storage Gateway 	        -** Hybrid Cloud Storage (extends on-premise sotrage to cloud).

**-> AWS SnowFamily     	        -** Storage devices used to physically migrate large amount of data.

**-> AWS Backup		        -** Fully managed backup service.

**-> CloudEndure Disaster Recovery-**** Replicates your machine into Low Cost.

**-> Amazon FSx			-** Feature rich & highly-performant file system.	

## DATABSE SERVICES:
- **Database Migration Service(DMS) -**
  - DMS can migrate:
  - On-premise to AWS;
  - from 2 DB in diff/same AWS accounts using different SQL Engines;
  - from SQL to NOSQL DB. 
- **Elastic Cache -** managed DB for IN-MEMORY & CACHING open source DB for Redis/Memcached (When you need to improve the performance of app by adding a caching layer in-front of web-server/DB).
- **RedShift -** PetaSize Data-warehouse for OLAP.									

## AWS WELL-ARCHITECTED DESIGN PRINCIPLES:

### 1) Operational Excellence: 
- Perform operations as Code.
- Make Frequent Small Reversible Changes.
- Refine Operations procedures frequently.
- Anticipate Failures.
- Learn from all Operational Failures.

### 2) Security:
- Implement a strong Identity Foundation (PoLP- Principle of Least Privilege).
- Enable Traceability.
- Apply Security at all Layers.
- Automate Security Best Practices.
- Protect data in Transit & at Rest.
- Keep People away from Data.
- Prepare for Security Events.

### 3) Reliability:
- Automatically recover from Failure.
- Test Recovery Procedures.
- Scale Horizontally to increase aggregate System availability.
- Stop Guessing Capacity.
- Manage change in Automation.

### 4) Performance Efficiency:
- Democratize Advanced Technologies.
- Go Global In Minutes.
- Use Serverless Architectures.
- Expirements more often.
- Consider Mechanical Sympathy.

### 5) Cost Optimization:
- Implement Cloud Financial Management.
- Adopt a consumption model.
- Measure overall efficiency.
- Stop spending money on undifferentiated heavy lifting.
- Analyze and Attribute Expenditure.

**AWS ABUSE (Trust & Safety Team):**
- Spam
- DDOS attacks
- Port Scanning
- Intrusion Attempts
- Hosting Prohibited Content
- Distributing Malware
If your logs shows that one or more AWS-owned IP addresses are used for these attacks (if coming outside of AWS a/c or even from Inside of AWS a/c), you should not contact to AWS Support, You should contact to AWS ABUSE TEAM.


**Hardware Security Module(HSM):** Designed to store ENCRYPTION KEYS

**FIPS (Federal Information Processing Standard):** US & Canadian Gov. standard - specifies security reqs. for Cryptographic Modules that protect Sensitive Data.

**For MULTI-TENANT :** AWS KMS(Key Management Service) - helps in encryption of data.

**For SINGLE-TENANT:** AWS CloudHSM.


## COMPLIANCE PROGRAMS:
- **HIPAA (Health Insurance Portability & Accountability Act):** US based, Secures Medical information.
- **PHIP (Personal Helath Information Protection Act):** An Ontario provinsial Law (Canada) - regulates patient protected Health Info.
- **PCI DSS (The Payment Card Industry Data Security Standard):** Secures Credit card info. when doing online payment.
- **ISO/IEC (International Organizational for Standardization/International Electrotechnical Commission):**
   - ISO/IEC 27018: Protection of Personal Data in the Cloud (eg: PII).
   - ISO/IEC 27017: Enhanced focus on Cloud Security.
- **SOC (System and Organization Control):**
   - SOC 1: 18 Standard and report on the effectiveness of internal control.
   - SOC 2: Evaluates internal controls, policies, and procedures that directly relate to the security of a system at a service organization.
   - SOC 3: A report based on the Trust Services Criteria that can be freely distributed.
- **FIPS (Federal Information Processing Standard):**
   - US & Canadian Gov. standard - specifies security reqs. for Cryptographic Modules that protect Sensitive Data.
- **CSA (Cloud Security Alliance) STAR Certification:** Third-party assessment for Cloud provider's Security posture.
 
