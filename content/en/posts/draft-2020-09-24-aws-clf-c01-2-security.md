---
title: "AWS Cloud Practitioner: Security"
author: Caio Pavanelli
date: 2020-09-26
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

For AWS, security is both its responsibility as it is for customers. Whilst AWS is takes charge for the security **of** the cloud, customers are expected to be responsible for the security **in** the cloud. What does it mean? AWS will secure hardware, the operation of managed services and the global infrastructure. Customers will secure its data and all configurations.

> AWS is takes charge for the security **of** the cloud, customers are expected to be responsible for the security **in** the cloud.

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

Amazon Inspector is a service that runs a security benchmark against specific EC2 instances, in which you can run a variety of security benchmarks. It helps to prove if a given EC2 instance is hardened or not for example.

> Hardening is the act of eliminating as many security risks as possible.

It can also perform both network and host assessments. The process will install an AWS agent in your EC2 instance to run the assessment for your assessment target. With the result data you can review your findings and remediate any security issues.

A popular benchmark for Amazon Inspector is the CIS (Center of Internet Security).

### AWS WAF

The AWS Web Application Firewall protects your web applications from common web exploits. You can either write your own rules to **allow** or **deny** traffic based on the contents of HTTP requests, or use a **ruleset** from a trusted AWS Security partner in the AWS WAF Rules marketplace.

WAFs can be attached to **CloudFront** or to an **Application Load Balancer**. The protection covers web applications from attacks in the OWASP (Open Web Application Security Project) top 10 most dangerous attacks.

1. Injection;
2. Broken Authentication;
3. Sensitive data exposure;
4. XML External Entities (XXE);
5. Broken Access Control;
6. Security misconfigurations;
7. Cross Site Scripting (XSS);
8. Insecure Deserealization;
9. Using components with well known vulnerabilities;
10. Insufficient logging and monitoring.

![WAF](images/aws/waf.png)

### AWS Shield




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