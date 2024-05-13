---
title: "🌟 AWS CCP - Day-21 - Unleash EC2 Instance Store and Supercharge Your EC2 Performance! 🌟"
seoTitle: "Unleash EC2 Instance Store and Supercharge Your EC2 Performance!"
seoDescription: "Discover how EC2 Instance Store offers unparalleled I/O performance, ideal for demanding workloads."
datePublished: Mon May 13 2024 04:30:44 GMT+0000 (Coordinated Universal Time)
cuid: clw4gujaj000109mhemedfs4m
slug: aws-ccp-day-21-unleash-ec2-instance-store-and-supercharge-your-ec2-performance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715536172270/82d5ed13-efe4-4f14-a8ce-81c981840bcb.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction 💡

So you've seen a way to attach a network drive onto your EC2 Instances but they have limited performance and I told you with cause because it's a really good performance but sometimes you want something even higher performance and that is going to be a hardware disk attached onto your EC2 Instance. 💻

# Understanding EC2 Instance Store 📚

So the EC2 Instance is a virtual machine but it is obviously attached to a real hardware server. And some of these servers do have disk space that is attached directly, you know, with a physical connection onto the server. And so a special type of EC2 Instance can leverage something called an EC2 Instance Store, which is the name of the hardware, the hard drive attached to the physical server. 🛠️

## Benefits of EC2 Instance Store 🚀

So what you do with EC2 Instance Store, you use them for better I/O performance. You also make sure that they have good throughput and so on, so they're a great choice when you want to have extremely high disk performance. ⚡

## Limitations of EC2 Instance Store 🚫

But the caveat is that if you stop or you terminate your EC2 Instance, that has an Instance Store, then the storage will be lost. And therefore it's called an ephemeral storage so that means that the EC2 Instance Store cannot be used as a durable long term place to store your data. 🗄️

## Use Cases 📊

So what is a good use case for it then? Well if you have a buffer, a cache, you want to have scratch data or temporary content, this would be a great place to do these things but not for long term storage. For long term storage, EBS for example is a great use case. 🔄

# Responsibilities and Considerations 🛡️

Finally, in case the online server of your EC2 Instance does fail, then you'll risk to have a dear loss because the hardware attached to your EC2 Instance will fail as well. So if you do decide to use an EC2 Instance Store, then it is your entire responsibility to make sure that you back it up and that you replicate it correctly based on your needs. 🔐

# Performance Comparison 📈

So what I mean by better performance, this is just an example to illustrate it. If you look at for example, the Instance size of I3 dot something, there is an Instance Store attached to these kinds of instances and if you look at the Read IOPS and the Write IOPS which correspond to how many I/O operations you can do per second.

| Instance Type | Read IOPS | Write IOPS | Volume Type | Max IOPS | Latency | Durability | Cost | Availability | Use Cases | Scalability | Management Overhead |
|---------------|-----------|------------|-------------|----------|---------|------------|------|--------------|-----------|--------------|---------------------|
| I3.xlarge     | 3.3M      | 1.4M       | Instance Store | - | Low      | Lower      | Lower | Limited to Instance Availability | High-performance databases, caching, temporary storage | Limited to the instance type, does not persist data | Requires data backup and replication for durability |
| GP2           | -         | -          | EBS         | 32,000   | Medium   | High       | Higher | Highly Available | General-purpose workloads, boot volumes, development/test environments | Scales dynamically with provisioned capacity | Requires regular snapshotting and backup for data protection |

Then you can see at some of these random Read IOPS and Write IOPS can reach 3.3 million or 1.4 million, for the most performant one. And to put this in comparison with an EBS volume of type GP2 for example, you can reach thirty two thousand IOPS. So this is a lot more. But again, it's just to illustrate my point from an exam perspective anytime you see very high performance hardware attached volume for your EC2 Instances, think local EC2 Instance Store. 📊

# Day-21 Finished 🎉 
Today you have learned about EC2 Instance Store. 🚀
