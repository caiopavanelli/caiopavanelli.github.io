---
title: "AWS Cloud Practitioner: Security"
author: Caio Pavanelli
date: 2020-09-27
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tags: 
- hard skills
- aws
- aws cloud practitioner
- security
---

The AWS Certified Cloud Practitioner examination is intended to evaluate an overall understanding of the AWS Cloud. This post will focus on the security topic of the examination, and it's based on study notes taken for the test. These notes are heavily based on [Andrew Brown's video at FreeCodeCamp YouTube channel](https://www.youtube.com/watch?v=3hLmDS179YE), and the freely available [AWS Cloud Practitioner Essentials course](https://www.aws.training/Details/Curriculum?id=27076). This is part 2 of 4.

## Security

AWS cloud security is addressed in the exam to cover the following topics:

- Define the AWS Shared Responsibility model;
- Define AWS Cloud security and compliance concepts;
- Identify AWS access management capabilities;
- Identify resources for security support.

### Shared responsibility model

For AWS, security is both its responsibility as it is for customers. Whilst AWS takes charge for the security **of** the cloud, customers are expected to be responsible for the security **in** the cloud. What does it mean? AWS will secure the hardware, the operation of managed services and the global infrastructure. Customers will secure its data and all configurations.

> AWS takes charge for the security **of** the cloud, customers are expected to be responsible for the security **in** the cloud.

It's the customer responsibility to take care of:

- Data;
- Platforms;
- Applications;
- IAM (Identity and Access Management);
- Operating system;
- Network configuration;
- Firewall configuration;
- Client-side data encryption and data integrity authentication;
- Server-side encryption (File system and/or data);
- Network traffic protection (Encryption, Integrity, Identity);

AWS remains responsible for:

- AWS Software for:
  - Compute;
  - Storage;
  - Database;
  - Networking;
- AWS Hardware for:
  - Region;
  - Availability zones;
  - Edge locations.

### AWS Compliance Programs

The AWS Compliance programs are a set of internal policies and procedures of a company to comply with laws, rules, and regulations or to uphold business reputation.

### AWS Artifact

AWS Artifact comes at no cost. It's a self-service portal for on-demand access to AWS' security and compliance reports, and select online agreements. The intent of those documents is to prove how AWS meets such compliances.

### Amazon Inspector

Amazon Inspector is a service that runs a security benchmark against specific EC2 instances, in which you can run a variety of security benchmarks. It helps to prove if a given EC2 instance is hardened or not, for example.

> Hardening is the act of eliminating as many security risks as possible.

It can also perform both network and host assessments. The process will install an AWS agent in your EC2 instance to run the assessment for your target. With the result data you can review your findings and remediate any security issues.

A popular benchmark for Amazon Inspector is the CIS (Center of Internet Security).

### AWS WAF

The AWS Web Application Firewall protects your web applications from common web exploits. You can either write your own rules to **allow** or **deny** traffic based on the contents of HTTP requests, or use a **ruleset** from a trusted AWS Security partner in the AWS WAF Rules marketplace.

WAFs can be attached to **CloudFront** or to an **Application Load Balancer**. The protection can cover web applications from attacks in the OWASP (Open Web Application Security Project) top 10 most dangerous attacks.

1. Injection;
2. Broken Authentication;
3. Sensitive data exposure;
4. XML External Entities (XXE);
5. Broken Access Control;
6. Security misconfigurations;
7. Cross Site Scripting (XSS);
8. Insecure Deserialization;
9. Using components with well known vulnerabilities;
10. Insufficient logging and monitoring.

![WAF](/images/aws/waf.png)

### AWS Shield

AWS Shield is a managed **DDoS** (Distributed Denial of Service) protection service that safeguards applications running in AWS.

A DDoS attack is a malicious attempt to disrupt normal traffic by flooding a website with a large amount of fake traffic.

All AWS customers benefit from the automatic protections of **AWS Shield Standard**, at no additional charge. When you route your traffic through **Route 53** or **CloudFront** you are using AWS Shield Standard.

AWS Shield protects against layers 3, 4 and 7 attacks.

- layer 3 = network;
- layer 4 = transport;
- layer 7 = application.

![AWS Shield](/images/aws/shield.png)

#### AWS Shield Standard

AWS Shield Standard is targeted for protection against most common DDoS attacks, and access to tools and best practices to build DDoS resilient architectures.

It's automatically available on all AWS services.

#### AWS Shield Advanced

AWS Shield Advanced is targeted for additional protection against larger and more sophisticated attacks, to have visibility of the attacks, and to have 24/7 access to DDoS experts for complex cases.

---

AWS Shield is available on:

- Amazon Route 53;
- Amazon CloudFront;
- Elastic Load Balancing;
- AWS Global Accelerator;
- Elastic IP (Amazon Elastic Compute Cloud and Network Load Balancer).

### Penetration Testing

> Pentesting is an authorized simulated cyberattack on a computer system, performed to evaluate the security of the system.

AWS permits pentesting on a set of services:

- EC2 instances;
- NAT Gateways;
- ELB (Elastic Load Balancer);
- RDS (Relational Database Services);
- CloudFront;
- Aurora;
- API Gateways;
- AWS Lambda and Lambda@Edge functions;
- Lightsail resources;
- Elastic Beanstalk environments.

On the other hand, not all kinds of pentesting are allowed and therefore the following activities are strictly prohibited:

- Denial of Service (DoS);
- Distributed Denial of Service (DDoS);
- Simulated DoS;
- Simulated DDoS;
- Port flooding;
- Protocol flooding;
- Request flooding (login request flooding, API request flooding).

For other simulated events you will need to submit a request to AWS. A reply usually takes up to 7 days.

### Guard Duty

**Guard Duty** is a threat detection service which uses an **IDS/IPS** that continuously monitors for malicious/suspicious activity and unauthorized behavior. It uses machine learning to analyze the following AWS logs:

- CloudTrail logs;
- VPC Flow logs;
- DNS logs.

> Intrusion Detection System (IDS) and Intrusion Protection System (IPS) are a device or software that monitors a network or system for malicious activity or policy violations.

Guard Duty will alert you of findings, which you can automate an incident response via CloudWatch events or with third-party services.

### Key Management Service (KMS)

**KMS** is a managed service that makes it easy for you to create and control the encryption keys used to encrypt your data. It's a multi-tenant HSM (Hardware Security Module).

Many AWS services are integrated to use KMS to encrypt your data with a single checkbox.

KSM uses envelope encryption. When you encrypt your data, your data is protected, but you also have to protect your protection key. So you envelope your data key by encrypting it with a master key as an additional layer of security.

### Amazon Macie

Amazon Macie is a fully managed service that continuously monitors **Amazon S3** data access activity for anomalies, and generates detailed alerts when it detects a risk of unauthorized access or inadvertent data leaks.

It works by using machine learning to analyze your CloudTrail logs. Macie will also identify your most at risk users which could lead to a compromise.

Macie has a variety of alerts:

- Anonymized access;
- Configuration compliance;
- Credential loss;
- Data compliance;
- File hosting;
- Identity enumeration;
- Information loss;
- Location anomaly;
- Open permissions;
- Privilege escalation;
- Ramsomware;
- Service disruption;
- Suspicious access.

### Security Groups vs NACLs

A **Security Group** acts as a firewall at the **instance** level. It implicitly denies all traffic and you have to create **allow rules**.

**Network Access Control Lists** (NACLs) act as firewalls at the **subnet** level. In this case you have to create **allow** and **deny** rules.

### AWS VPN

AWS VPN let's you establish a secure and private tunnel from your network or device to the AWS global network. There are two kinds of VPN access:

- **AWS site-to-site VPN**: securely connect on-premises network on branch office site to VPC.
- **AWS client VPN**: securely connect users to AWS on on-premises networks.

## AWS Organizations and Accounts

**Organizations** allows you to centrally manage billing, control access, compliance, security, and share resources across your AWS accounts. Every organization has one **root account user** which is a single sign-in identity that has complete access to all AWS services and resources in an account. Each account has a parent root account user. A group of AWS accounts within an organization can be isolated in an **organization unit**. Organization units can also contain other units creating a hierarchy.

**Service Control Policies** give central control over the allowed permissions for all accounts in your organization, helping to ensure your accounts stay within your organization's guidelines.

<!-- ☁️ Security
⌨️ (3:13:49) Shared Responsibility Model
⌨️ (3:15:34) AWS Compliance programs
⌨️ (3:17:59) AWS Artifact
⌨️ (3:19:05) AWS Artifact Follow Along
⌨️ (3:21:35) Amazon Inspector
⌨️ (3:23:04) AWS WAF
⌨️ (3:24:17) AWS Shield
⌨️ (3:27:42) Penetration Testing
⌨️ (3:29:29) Guard Duty
⌨️ (3:31:13) Key Management Service
⌨️ (3:32:50) Amazon Macie
⌨️ (3:35:06) Security Groups vs NACLs
⌨️ (3:37:02) AWS VPN -->