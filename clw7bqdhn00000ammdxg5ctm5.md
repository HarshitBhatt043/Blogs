---
title: "🚀 AWS CCP - Day-23 - Conquer Your File System Challenges with Amazon FSx 🚀"
seoTitle: "Conquer Your File System Challenges with Amazon FSx"
seoDescription: "Explore FSx for Lustre and FSx for Windows File Server, tailored for seamless integration and high-performance computing workloads."
datePublished: Wed May 15 2024 04:30:50 GMT+0000 (Coordinated Universal Time)
cuid: clw7bqdhn00000ammdxg5ctm5
slug: aws-ccp-day-23-conquer-your-file-system-challenges-with-amazon-fsx
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715708369321/0305ea18-f059-4029-bc57-9b35d75e9418.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to Amazon FSx 💡

Now let's talk about Amazon FSx, which is a managed service for you to get third-party high-performance file systems on AWS. So if you don't wanna use EFS or S3, and you want something else, then you can use FSX to manage these file systems. So you have three offerings today. You have FSx for Lustre, FSx for Windows File Server, and FSx for NetApp ONTAP. And they can add file systems over time to the FSx service. 📁

# Amazon FSx for Windows File Server 🪟

The first one is Amazon FSx for Windows File Server, which is a fully managed, highly reliable and scalable Windows native shared file system built on Windows File Server. So this is meant for your Windows instances. So the way you do it is that you deploy the FSx usually across two availability zones, and then there is support for all the Windows native protocols, such as the SMB protocol and Windows NTFS, which allows you to mount this file system onto your Windows machines. And so if you look at your corporate data center and you have a Windows Client, for example, over SMB, you're able to access the Windows file server. But also if you have EC2 instances that are Windows-based, then they could also access this Windows file server. So Amazon FSx is the way for you to deploy this Windows file server that leverages the SMB protocol and Windows NTFS. Because this is also a Microsoft type of offering, there is integration with Microsoft Active Directory for user security and Windows file server in Amazon FSx can be accessed from AWS directly. 🖥️

# Amazon FSx for Lustre 🎨

Now, the second flavor of Amazon FSx you have in AWS is called Amazon FSx for Lustre. And you need to remember that this is a fully managed, high-performance, and scalable file storage for high-performance computing. So whenever you see storage for HPC, think FSx for Lustre. Why, well Lustre, this is derived from the name Linux and cluster, so put together it's Lustre. And so imagine cluster-like processing these kinds of things, maybe it's a way for you to remember what Amazon FSx for Lustre is. This allows you to run a lot of use cases for high-performance computing, such as machine learning, analytics, video processing, financial modeling, and it scales to extremely high traffic in terms of hundreds of gigabytes per second of data exchanged, millions of IO operations per second, sub-millisecond latency, so it's really a high-performance file system. So the way it works is that Amazon FSx for Lustre can be connected either to your corporate data center or to your compute instances directly within AWS. And then in the backend, Amazon FSx for Lustre is actually storing your data, possibly onto an Amazon S3 bucket. 🌟

# Summary 📝
| Feature                  | Amazon FSx                                      | Amazon FSx for Lustre                               |
|--------------------------|-------------------------------------------------|-----------------------------------------------------|
| File System Type         | Fully managed file system (Windows/Linux)       | Fully managed file system for Lustre                |
| Supported Protocols      | NFS, SMB                                         | Lustre                                               |
| Data Consistency         | Strong consistency for NFS, eventual for SMB     | Strong consistency                                   |
| Performance              | Designed for a wide range of workloads          | Designed for high-performance computing (HPC)       |
| Storage Capacity         | From 32 GB to 64 TB (SSD) or 120 TB (HDD)       | Scalable from 1.2 TB to hundreds of petabytes       |
| Throughput               | Up to 2 GB/s (SSD) or 12 GB/s (HDD)             | Scales to thousands of gigabytes per second (GB/s)  |
| Use Cases                | General-purpose file storage, business applications | High-performance computing (HPC), machine learning  |
| Backup and Restore       | Automated backups and manual snapshots           | Manual backups and snapshots                        |
| Scalability              | Vertical and horizontal scaling                  | Horizontal scaling                                  |
# Day-23 Finished 🎉
Today you have learned about Amazon FSx. 💡
