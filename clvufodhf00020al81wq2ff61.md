---
title: "AWS CCP - Day-16 - EBS Volumes Your AWS Sidekick for Data Adventures 💾"
seoTitle: "Explore EBS Volumes for Data Persistence & Flexibility!"
seoDescription: "Discover how EBS Volumes offer data persistence, flexibility, and seamless failover capabilities, ensuring your AWS architecture is primed for success."
datePublished: Mon May 06 2024 04:00:15 GMT+0000 (Coordinated Universal Time)
cuid: clvufodhf00020al81wq2ff61
slug: aws-ccp-day-16-ebs-volumes-your-aws-sidekick-for-data-adventures
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714887936253/5b8634c7-2c3b-45a5-944b-5ad1ceef349e.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to EBS Volumes 📚

Now we will look at the different storage options for EC2 instances. So first, the most important ones are going to be EBS Volumes, so let's define what they are. An EBS Volume stands for Elastic Block Store. It's a network drive that you can attach to your instances while they run, and you've been using them without even knowing.

## Persistence with EBS Volumes 🔄

So these EBS Volumes allow you to persist data, even after your instance is terminated. And so that's the whole purpose, you can recreate an instance and mount to the same EBS Volume from before and you'll get back your data. That is very helpful. So these EBS Volumes, at your CCP level, can only be mounted to one instance at a time. And when you create an EBS Volume, it is bound to a specific availability zone.

## Understanding EBS Volumes 🤔

That means that you cannot have an EBS Volume created, for example, in us-east-1a and use it in us-east-1b as we'll see in the diagram later. So how do you think of EBS Volumes? Well, you can think of them as network USB sticks. So, it's a USB stick that you can take from a computer and put it in another computer but you actually don't physically put it in a computer. It's attached through the network.

# Features and Benefits 🎁

The feature gives you 30 GBs of free EBS storage of type General Purpose or SSD or Magnetic per month. You'll be using this with the GP2 to GP3 Volumes. Now let's look at it. So EBS Volumes are network drivers that are not a physical drive, So to communicate between the instance and the EBS Volume, you'll be using the network.

## Flexibility of EBS Volumes 🌐

And because the network is used, there may be a bit of latency from one computer to reach to another server. Now, EBS Volumes, because they are a network drive they can be detached from an EC2 instance and attached to another one very quickly. And that makes it super handy when you want to do failovers for example.

## Availability and Provisioning ⏳

EBS Volumes are locked to a specific availability zone, that means that, if it's created in us-east-1a it cannot be attached to us-east-1b but, if we do a snapshot, then we are able to move a volume across from different availability zones. And finally, it's a volume, so you have to provision capacity in advance. So you need to say how many GBs you want in advance and the IOPS, which is I/O operations per second, and you're basically defining how you want your EBS Volume to perform. You're going to get billed for that provisioned capacity and you can increase the capacity over time if you want you to have better performance or more size.

# Representation 🖥️

```markdown
+-------------------------------------+ +-------------------------------------+
|           AWS Region: us-east-1a    | |           AWS Region: us-east-1b    |
+-------------------------------------+ +-------------------------------------+
|            EC2 Instance 1           | |            EC2 Instance 1           |
|        +---------------------+      | |        +---------------------+      |
|        | Attached EBS Volume |      | |        | Attached EBS Volume |      |
|        |       Volume 1      |      | |        |       Volume 1      |      |
|        +---------------------+      | |        +---------------------+      |
|-------------------------------------| |-------------------------------------|
|            EC2 Instance 2           | |            EC2 Instance 2           |
|        +---------------------+      | |        +---------------------+      |
|        | Attached EBS Volume |      | |        | Attached EBS Volume |      |
|        |       Volume 2      |      | |        |       Volume 2      |      |
|        +---------------------+      | |        +---------------------+      |
+-------------------------------------+ +-------------------------------------+
```

We have us-east-1a with one EC2 instance and you can attach, for example one EBS Volume to your EC2 instance. If you create another EC2 instance, as I said an EBS Volume cannot be attached to two instances at a time at the Certified Cloud Practitioner level. And therefore, what you wanna say is that this other EC2 instance needs to have its own EBS Volume attached to it, but it is very possible for you to have two EBS Volumes attached to one instance think of it as two network USB sticks into one machine that makes a lot of sense.

## EBS Volumes and Availability Zones 🌐

Now EBS Volumes are linked to an availability zone. So as we can see, all this diagram has been so far using us-east-1a. So if you want to have other EBS Volumes in another AZ then you would need to create this separately in the other availability zone. So just same way that your EC2 instances are bound to an AZ, so are the EBS Volumes.

## Unattached EBS Volumes and Delete on Termination 🚫

Finally, it is possible for you to create EBS Volumes and leave them unattached they don't need to be necessarily attached to an EC2 instance, they can be attached on demand and that makes it very, very powerful. Finally, when you go ahead and create EBS Volumes through EC2 instances, there is this thing called a Deletes on Termination attribute and this can come up in the exam so, if you look at this when you create an EBS Volume in the console, when you create an EC2 instance there is the second to last column called Delete on Termination. And by default, it is ticked for the Root Volume and not ticked for a new EBS Volume. So this controls the EBS behavior when an EC2 instance is being terminated. So by default, the root EBS Volume is deleted alongside the instance being terminated. So it's enabled and the default any other attached EBS Volume is not deleted because it's disabled by default. But obviously, you can control if you want to enable or disable delete on termination. And so use case right, would be for example, if you want to preserve the root volume, when an instance is terminated, for example, to save some data then you can disable delete on termination for the root volume, and you'll be good to go and it could be an exam scenario at the exam.

# Day-16 Finished 🚀🎉

Today you have learned about AWS EBS Volumes.🌟 📊