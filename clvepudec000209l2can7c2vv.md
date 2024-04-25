---
title: "💳 AWS CCP - Day-09 - Navigating Billing, Budgets, and EC2 Instances 💻"
seoTitle: "Master AWS Cost Control & EC2 Selection"
seoDescription: "Learn how to wield IAM access for billing insights & set up budgets! Plus, unravel the mysteries of EC2 instance types for optimal app performance"
datePublished: Thu Apr 25 2024 04:00:32 GMT+0000 (Coordinated Universal Time)
cuid: clvepudec000209l2can7c2vv
slug: aws-ccp-day-09-navigating-billing-budgets-and-ec2-instances
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713723313977/f6987e3d-10cc-497b-8944-be14d185effa.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Setting Up IAM Access to Billing Information 🛠️

So in your account, you're going to make sure to spend the least amount of money or no money, and I will let you know when something will cost you some money. But nonetheless, it is a good idea to set up a billing budget so that we know when we go over spending some money and we can get alerted in case of that.

## Accessing the AWS Billing Dashboard 💼

What you're going to do is click on My Account, and then click on My Billing Dashboard. Now as you can see, you need permissions, and this is because you're logged in as an IAM user on your account, and we need to change something on the root account before we get access with IAM users, even administrators, to the Billing & Cost Management Dashboard.

## Investigating Charges 🔍

So to solve this you logged in as your root account, as you can see, now it just says your account number, it doesn't say the IAM user, so you're logged in as your root account, and then you click on My Accounts. So you need to be your root account to do this. You scroll down and you're going to find this one setting called IAM User and Role Access to Billing Information. And we'll edit this and we'll activate IAM access, and this will allow IAM users who are administrators to access billing data.

## Understanding Your Charges 💰

If you don't want that, you can also set up a billing alarm using the root account, if you wanted to. But I want to tell you how to set up a billing alarm using an IAM user, in case this is something you wanted to do. So once this setting is activated, you can go back into your IAM user, and then refresh this page. So here we are in the AWS Billing Dashboard home, and this is where you can see the charges for your month. We do the best to remain within the free tier, but sometimes, if you have any charge, you would see it here, and then let me tell you how you can find the source of your charge.

## Setting Budgets for Cost Control 📉

So if you go on the left-hand side into Bills, and you are on this Bills page. Okay, so once we are here in this interface, you would see your grand total, and then you can scroll down and you can go to Charges by Service. And this is to see which service is incurring you some charges.

## Creating Budgets and Alerts 🚨

So for example, if you go and scroll down and go into your Elastic Compute Cloud service, you can see that some charges were incurred in the US East, Northern Virginia region. So you click on it and open this in a new page. And on the new UI, you see that, yes, this is the charge, and it comes from the EBS part of it. So this is the Usage Description, and it says that you've been using some gigabyte month of the gp2 type of EBS volume. So this information is enough for you to figure out that you've probably left a volume unused in your account.

### Note 📝

So it's up to you, of course, to debug your own costs, and so this is the way you would do it. Also, if you go over the free tier, this is going to be on the left-hand side. So if you go on the left-hand side, you will see all your services, as well as what is the free tier usage and your current usage. So you know right away if you are, for example, at 100% of your free tier or if you're about to hit it and so on, so this really helps you to understand what you've been doing wrong as well. Now to get alerts about your upcoming costs, the best thing to do is to go into creating an AWS budget. So you are now in the budget console, and you're going to create a budget in here so that we can track our cost and we can make sure we receive alerts if we're about to hit our limits.

# Introduction to EC2 🚀

Been on EC2 in which we will create our first website on AWS. So what is Amazon EC2? Well, EC2 is one of the most popular of AWS' offering. It is definitely used everywhere. And what is it? Well, it stands for Elastic Compute Cloud and this is the way to do Infrastructure as a Service on AWS.

## Components of EC2 🔧

So EC2 is not just one service. It's composed of many things at a high level. So you can rent virtual machines on EC2, they're called EC2 instances. You can store data on virtual drives or EBS volumes. You can distribute load across machines, Elastic Load Balancer. You can scale services using an auto-scaling group or ASG, etc.

## Importance of EC2 📊

Knowing how to use EC2 in AWS is fundamental to understand how the cloud works. Because as I said from before, the cloud is to be able to rent these compute whenever you need, on demand, and EC2 is just that.

## Customization Options ⚙️

So, EC2, what can we choose for our instances so there're virtual server that were rent from AWS? So what Operating System can we choose for our EC2 instances? Three options: Linux, and it's going to be the most popular, Windows or even Mac OS. How much compute power and cores you want on this virtual machine? So how much CPU? Then you need to choose how much random access memory or RAM you want, and how much storage space.

## Networking and Security 🔒

So for example, do you want storage that is going to be attached through the network and we'll see about it with EBS or EFS, or do you want it to be hardware attached? In this case, it will be an EC2 instance store. And then finally, the type of network you want to attach to your EC2 instance. So, do you want a network card that is going to be fast? What kind of public IP do you want? And finally, we need to handle the firewall rules of our EC2 instance, and that is the security group.

## Bootstrap Script 🚀

And I lie, finally, finally, there's the Bootstrap script to configure the instance at first launch, which is called the EC2 User Data. So we have lots and lots of options and, even more options at other certification levels that you need to know in EC2 instances, but at a core of it what you need to remember is that you can choose pretty much how you want your visual machine to be and you can rent it from AWS.

### Automating Tasks with User Data 🤖

So it is possible to bootstrap our instances using the EC2 User Data script. So what does bootstrapping mean? Well, bootstrapping means launching commands when the machine starts. So, that script is only run once and when it first starts, and then will never be run again. So the EC2 User Data has a very specific purpose. It is to automate boot tasks, hence the name bootstrapping.

## Instance Types 💻

What type of instances do we get for EC2? And this is an example. We have hundreds and hundreds of EC2 instance types, but, here are five for you. So the first one is a t2 micro, very very simple. It has one vCPU, one gigabyte of memory. The storage is only for EBS, and it has a low to moderate network performance. But as soon as you increase the instance type like for example if you stay in the same family, so we stay in the t2 family but we go to t2.xlarge, now you have access to four vCPU 16 megabytes of RAM, gigabytes of RAM, sorry, and network performance of moderate.

### Understanding Instance Characteristics 🧠

If we go to complete different new levels, so c5d.4xlarge, which is a very complicated name, you get 16 vCPU, so 16 cores, you get 32 gigabytes of memory, so a lot more, you get some storage that is attached to your EC2 instance, this is where it says 400 NVMe SSD. Now the network is going to get really good up to 10 gigabytes, as well as the bandwidth to talk to network storage. And so, as you can see, if you go to r5.16xlarge or m5.8xlarge, again you have different characteristics.

### AWS Free Tier 🆓

So, the idea with this is that you choose the kind of instance that fits best your application, and you can use that on the cloud on demand. Now, for this instance, t2 micro is going to be part of the AWS free tier. You can get up to 750 hours per month of t2 micro which represents basically running that instance continuously for a month.

# Day-09 Finished 🎉

So that's it,today you have learned about AWS Billing,Budgets and EC2.