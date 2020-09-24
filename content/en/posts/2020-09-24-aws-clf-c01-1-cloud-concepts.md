---
title: "AWS Cloud Practitioner: Cloud Concepts"
author: Caio Pavanelli
date: 2020-09-24
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tags: 
- hard skills
- aws
- aws cloud practitioner
- cloud concepts
---

The AWS Certified Cloud Practitioner examination is intended to evaluate an overall understanding of the AWS Cloud. This post will focus on the cloud concepts part of the examination, and it's based on study notes taken for the test. These notes are heavily based on Andrew Brown's video at FreeCodeCamp YouTube channel, and the freely available [AWS Cloud Practitioner Essentials course](https://www.aws.training/Details/Curriculum?id=27076). This is part 1 of 4.

{{< youtube 3hLmDS179YE >}}

## Exam Objectives

The AWS Certified Cloud Practitioner is the entry level of AWS Cloud certifications, but it already covers a wide range of topics. The objectives of exam **CLF-C01** are:

- Define what the AWS cloud is, and its global infrastructure;
- Describe basic AWS cloud architecture principles;
- Understand the AWS cloud value proposition;
- Talk about common AWS services and their common use cases;
- Define basic security and compliance aspects of AWS platform and their shared security model;
- Define the billing, account management and pricing models;
- Identify sources of documentation and technical assistance;
- Describe basic characteristics of deploying and operating in the AWS cloud.

## Cloud Computing

We've already mentioned the word **cloud** multiple times in a couple paragraphs, but what actually is **cloud computing**?

**Cloud computing** stands for on-demand delivery of IT resources and applications via the internet. In other words, it's the practice of using a network of remote servers hosted on the internet to store, manage, and process data, rather than a local server or a personal computer. Those resources provide:

- Servers;
- Databases;
- Higher level application components;
- New security models:
  - Test often;
  - Patch quickly;
  - Respond incidents fast.

Nonetheless, it also brings:

- Scalability;
- Agility;
- Elasticity;
- Reliability;
- Fault tolerance;
- Continuous monitoring.

## On-premise vs Cloud Providers

When working in a on-premise environment the company will essentially own the servers. It's fully responsible for hiring the IT people, paying for or renting the real state, as well as taking charge of all the risks implied to the operation of a data center.

On the other hand, when a company works with a cloud provider, the company is only responsible for configuring their cloud services and code. The cloud provider takes charge for running the data center and taking the risks for the activities involved. Therefore, **cloud computing** has some noticeable advantages.

## Advantages of cloud computing

### 1. Trade capital expense for variable expense

There is no upfront cost. You are only paying for what you actually use. Instead of paying for data centers and servers, pay only when you consume computing resources.

### 2. Benefit from massive economies of scale

You are sharing the cost with other customers to get unbeatable savings. Usage from hundreds of thousands of customers in the cloud.

### 3. Stop guessing capacity

Eliminate guess work about infrastructure capacity needs. Instead of paying for idle or underutilized servers, you can scale up or down to meet the current resource needs.

### 4. Increase speed and agility

Launch resources within a few clicks, in minutes. There is no need for waiting days or weeks for IT to implement the solution on-premises.

### 5. Stop spending money on running and maintaining data centers

Focus on your own customers rather than on the heavy lifting of racking, stacking and powering servers.

### 6. Go global in minutes

Deploy applications in multiple regions around the world with a set of configurations. This allows the provision of lower latency and a better experience for your customers at a reduced cost.

## Types of cloud computing

**Cloud computing** is offered in three distinctive ways: **SaaS**, **PaaS** and **IaaS**.

1. **Software as a Service (SaaS)**
   1. Targeted for customers;
   2. A complete product that is run and managed by the service provider.

2. **Platform as a Service (PaaS)**
   1. Targeted for developers;
   2. Removes the need for your organization to manage the underlying infrastructure;
   3. Developers can focus on the deployment and management of your applications.

3. **Infrastructure as a Service (IaaS)**
   1. Targeted for administrators;
   2. The basic building blocks for cloud IT;
   3. Provides access to networking features, computers and data storage space.

## Deploying models

When working with the cloud you can either go full cloud or hybrid.

Startups, new companies and projects which are allowed to start fresh may benefit from going full cloud. It's easier to experiment and benefit from SaaS offerings.

A hybrid deployment model exists when a company mix the use of cloud and on-premises resources. It could work for banks, fintechs, investment management companies, large professional service providers and legacy on-premises systems.

Finally, there are those who demand full on-premise operations. When deploying on-premises using virtualization and resource management tools, it's sometimes called **private cloud**. This could be true for the public sector and hospitals, where there lies super sensitive data, or large enterprise with heavy regulations such as insurance companies.

---

## AWS Cloud Based Products

AWS offers a variety of cloud based products covering:

- Compute;
- Storage;
- Databases;
- Analytics;
- Networking;
- Mobile;
- Developer tools;
- Management tools;
- IoT;
- Security;
- Enterprise applications.

AWS resources can be managed via three different interfaces:

- AWS Management Console;
- AWS Command Line Interface (CLI);
- AWS SDKs.

AWS Core services are:

- EC2 (Elastic Compute Cloud);
- EBS (Elastic Block Store);
- S3 (Simple Storage Services);
- Amazon Global Infrastructure.

### EC2

**EC2** provides pay-as-you-go instances for compute power, which can increase or decrease in a configurable manner.

Each EC2 instance requires:

- A region;
- An **AMI** (Amazon Machine Image), which stands for the software which run on the VM;
- Instance type, which is the underlying hardware;
- Network configuration;
- Storage configuration (EBS);
- Security group configuration;
- Key pairs to provide SSH access.

The benefits of using Amazon EC2 instances compared to physical on-premises servers in your own infrastructure are that you pay only for the capacity you use, and the ability to have different storage requirements.

### EBS

**EBS** can be used as store units for EC2 instances. It also runs on a pay-as-you-go model and have the following characteristics:

- Can have magnetic or SSD storage;
- Has block replication;
- Has the ability to take snapshots;
- Copies between EC2 instances are encrypted at the EC2 instance level;
- An EBS must be created in the same availability zone as the EC2 instance to be available for attachment;
- Once created, an EBS must be attached to an EC2 instance;
- An attached EBS can be formatted into a partition and mounted;
- Tags are useful for identifying purpose and group volumes on billing reports.

### S3

**S3** is a fully managed cloud storage service. It's not attached to any server. Bellow are some notes regarding S3:

- It can store virtually an unlimited number of objects, which can be accessed anytime and anywhere;
- It has rich security controls contemplating identity access management policies, bucket policies and even object level access controls;
- When a bucket is created in S3, it is automatically replicated within other facilities in the same availability zone;
- S3 also natively supports high access volumes;
- The object URL is composed of the bucket name, a region specific endpoint and the object key;
- The object key is a string, which is common practice to represent a directory path;
- Each bucket name must be unique within the availability zone, and it can only contain URL safe characters;
- Every bucket has a region.

Common use cases for S3 are:

- Store application assets;
- Static Web Hosting;
- Backup and disaster recovery;
- Storing for Big Data:
  - Data can be loaded into Redshift
  - Processed in EMR
  - Queried in-place with Athena

### Amazon Global Infrastructure

The Amazon global infrastructure is formed by **regions**, **availability zones** and **edge locations**.

**Regions** have two or more Availability zones.

**Availability Zones** are collections of data centers physically separated from one another. Each data center is powered by a different power grid supplier and independent connectivity infrastructure.

**Edge locations** are strategic positioned close to high density areas. It's the Amazon CloudFront (CDN), which is responsible for delivering content to final consumers.

<!-- ---
Introduction
⌨️ (0:00:00) Meet Your Instructor Andrew Brown
⌨️ (0:00:40) Why Get AWS Cloud Practitioner Certified?
⌨️ (0:06:40) Exam Guide Overview

☁️ Cloud Concepts
⌨️ (0:09:57) What is Cloud Computing?
⌨️ (0:12:10) Six Advantages and Benefits of Cloud Computing
⌨️ (0:14:42) Types of Cloud Computing
⌨️ (0:16:48) Cloud Computing Deployment Models

☁️ Getting Started
⌨️ (0:29:20) Creating an AWS Account
⌨️ (0:32:43) Billing Preferences, Budgets and Alarms
⌨️ (0:40:09) Change IAM Users Sign-in Link
⌨️ (0:41:14) Activate MFA on Root Account
⌨️ (0:43:40) Create individual IAM user
⌨️ (0:48:44) Set a password policy -->
