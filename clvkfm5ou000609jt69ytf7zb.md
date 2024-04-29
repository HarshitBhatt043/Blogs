---
title: "💻 AWS CCP - Day-11- Dive into AWS EC2 Instance Types and Unleash Your Cloud Potential 🚀"
seoTitle: "AWS EC2 Instance Types: Your Roadmap to Cloud Success"
seoDescription: "Unlock the power of AWS EC2 instance types! Dive into our insights and supercharge your cloud journey today!"
datePublished: Mon Apr 29 2024 04:00:49 GMT+0000 (Coordinated Universal Time)
cuid: clvkfm5ou000609jt69ytf7zb
slug: aws-ccp-day-11-dive-into-aws-ec2-instance-types-and-unleash-your-cloud-potential
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714282962649/50e6d8da-0cea-4455-b933-bf3c3d2048c0.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to EC2 Instance Types 📝

There are different types of EC2 instances that you can use for different use cases and they have different types of optimization. Let's go check out this [Docs](https://aws.amazon.com/ec2/instance-types/) and we'll see we have for now, seven different types of EC2 instances. So this website on the AWS website is what you're interested in. And as we can see, we have different types of instances. We have general purpose, compute, optimized, memory optimized, and so on.And so for each type of instance we have different families, this website is going to be the reference for you to look at Institute Instance types and know their costs and other specificity.

# Naming Convention and Overview 🔍

What I'm going to do though, is just walk you through a high-level overview of how they work in AWS. AWS will have the following naming convention. For example, we'll be talking about an m5.2xlarge type of instance. What does that mean? Well, M is going to be called the Instance Class. And this is going to be, for example, in this case a general purpose type of instance, five is generation of the instance. So as AWS improves the hardware over time if they release a new generation of hardware, and so after M five, if they improve the M type of instance class then we'll go to M 6 and then finally the 2xlarge represented the size within the instance class. So, it starts as small and then large and then two X large four X large and so on. So it represents the size of the instance, and the more the size, the more the memory the more the CPU is going to have on your instance. So from an exam perspective, what do you need to know?

## General Purpose Instances 💡

Well, we'll talk about a few different types of instance types. So you have a general purpose and these are great for diversity of workloads such as web servers or code repositories. They will have a good balance between compute, memory, networking. You'll be using the T2 micro which is the free tier, general purpose type of instance. On the website that I just showed you, you will see all the different types of instance that are general purpose and this is going to evolve over time.

## Compute Optimized Instances ⚡

Then we have compute optimized, and these instances are great, and optimized for compute intensive tasks. So what requires a high level of processor? Well, if, for example, it could be if you're batch processing some data if you're doing media transcoding if you need high-performance web servers if you're doing high performance computing is called HPC. If you're doing machine learning or if you have a dedicated gaming server. So all these things are tasks that require a very good CPU very good compute side. And so Ec2, instances do have this kind of particularity and for now all the computer optimized instances in EC2, are of the C names. So C5, C6, and so on.

## Memory Optimized Instances 🧠

Next, we have some EC2 instances that are memory optimized and there are going to have a really fast performance for the type of workloads that will process large datasets in memory. So memory means RAM. And so the use cases are going to be high performance for relational or non-relational databases are mostly going to be in memory databases, distributed web-scale cache store. So for our elastic cache, for example in memory databases that are optimized for business intelligence or BI. And applications performing real-time processing of big unstructured data. So in terms of the names for the memory optimized instances there's going to be the R series because R stands for RAM but there's also going to be X one high memory and Z one, but again, you don't have to remember the name of the instances, but good to know at a high level.

## Storage Optimized Instances 🗄️

Okay. And finally we'll have storage optimized instances. They're great when you are accessing a lot of data sets on the local storage. And so the use cases for storage optimized instances are going to be high-frequency online transactional processing, so OLTP systems. Relational and NoSQL databases. Cache for in-memory databases, for example, Redshift data warehousing application distributed file systems and the search optimized instances in AWS will start with an I, a G, or H one. Okay. But again, don't have to remember this. I'm just giving you examples.

# Instance Comparison 🔄

| Instance Type | vCPUs | Memory (GB) | Network Performance | EBS Bandwidth | Cost (Linux On-Demand) | Cost (1-Year Reserved) |
|---------------|-------|-------------|---------------------|---------------|------------------------|------------------------|
| t2.micro      | 1     | 1           | Low to Moderate    | Moderate      | $0.0116/hr             | $77.63/yr              |
| r5.16xlarge   | 16    | 512         | High                | High          | $3.2000/hr             | $22,364.80/yr          |
| c5d.4xlarge   | 16    | 32          | High                | High          | $0.9520/hr             | $6,665.60/yr           |

So what does it mean? Let's compare a few instance types. So for example, for t2.micro we have one VCPU and one memory, one gigabytes of memory. And if you look for example, at r5.16xlarge we have 16 VCPU and 512 gigabytes of memory. So we can see there's a lot of more emphasis on the memory. If we compare it to example, to a c5d.4Xlarge we can see we have 16 VCPU and 32 gigabytes of memory. So less memory, more CPU and so on different network performance different EBS bandwidth and so on. So just to give you a point of comparison, and because you're using t2.micro, So you get up to 750 hours per month of t2.micro. And if you want a website to compare all the EC2 Institute instances together, there's one that you will really like, it's [here](https://instances.vantage.sh/), or you can also use your EC2 console to compare. So you are on the website and as we can see, we have a list of all the instances available in AWS. So really, a lot. We also get some information around the Linux on demand cost and an X reserves cost, and so on, so some cost information. We get information around the memory the number of VCPU. We can order by name, we can search it. So it's, it's quite handy. And you will really like this website.

# Day-11 Finished 🎉

Today you have learned about EC2 Instance Types.
