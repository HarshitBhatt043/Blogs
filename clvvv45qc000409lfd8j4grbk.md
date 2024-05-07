---
title: "AWS CCP - Day-17 - Understanding Amazon EBS Volumes- Attachments, AZ Boundaries, and Termination Behavior 📑"
seoTitle: "Understanding Amazon EBS Volumes: Attachments, AZ Boundaries, etc"
seoDescription: "Delve into the complexities of Amazon EBS volumes in AWS, exploring attachment processes, AZ constraints, and termination behaviors."
datePublished: Tue May 07 2024 04:00:12 GMT+0000 (Coordinated Universal Time)
cuid: clvvv45qc000409lfd8j4grbk
slug: aws-ccp-day-17-understanding-amazon-ebs-volumes-attachments-az-boundaries-and-termination-behavior
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714917331600/4607d5a8-d72b-420d-b10c-5a53dcc4aceb.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Introduction 🎉

So let's have a look at the EBS volumes attached to your instance. If you click on instance and then you go to the storage tab, you'll find that there is a root device and a block device on it, you've got one volume of eight gigabytes currently attached to your EC2 instance. So what you can do is click on that volume, and it will take you to the volumes interface of AWS. And you can see there, yes, indeed, your volume exists and it's there. It's in use as shown there, and it's attached to an instance right there. So you have a different kind of console there, and to access it, you can just go on the left-hand side and click on volumes.

## Creating a Second EBS Volume 🔄

So as we can see, now you have one EBS of eight gigabytes, and what you can do is create a second volume. So let me create a volume, and you will have many options to choose from, GP2, GP3, and so on, but you will just use GP2 of type of size two gigabytes. Then for the availability zone, you can choose the same one where your EC2 instance is. To do this, go into your EC2 instance, find which availability zone it is on. So you scroll down, and it is going to be in the networking one. Scroll down in the networking, and here, availability zone, it says eu-west-1b. Therefore, the volume you will create is going to be in eu-west-1b because the EBS volumes are bound by specific AZ.

## Attaching the Second Volume 📁

Have it done and create this volume. Now your volume is created. And what you can do is click on it; this one is currently not attached. What you can do is action and then you can attach the volume. Find an instance. You will have one running right there. And so you're going to attach this volume to your instance, click on attach volume, and voila, your instance now has two EBS volumes attached to it.

## Verification ✔️

How do you know? Well, refresh this page, go to storage on your EC2 console, scroll down. As you can see now for block devices, you have two block devices. You have the one of eight gigabytes and the one of two gigabytes.

## Creating a Volume in a Different AZ 🔄

To actually use this new block device, it's a bit more complicated, but you can go to format EBS volume attach EC2, and you should find something like, yes, make an Amazon EBS volume available to use on Linux, and this gives you instructions on how to do it, but again, this is out of scope for this blog. So now if you go into your volumes and create a volume, you can create a volume of two gigabytes of GP2, but this time the AZ is going to be eu-west-1a and not eu-west-1b. So it's going to be a different AZ than the one of your EC2 instance. And the reason you do so is to show you that right now, you have three GP2 volumes.

## Understanding AZ Boundaries 🌐

So let's refresh this. So the last one is available and it's a different AZ, so eu-west-1a. And if you do actions and then attach volume, you cannot attach it to your EC2 instance because your EC2 instance is in eu-west-1b. And so therefore, we can see that the EBS volumes indeed are bound by a specific availability zone.

## Termination Behavior 🔄

Lastly, what you can do is that you can take this volume, do action, delete volume, and it's gone. And that really shows you the power of the cloud. You can just request volumes, delete volumes right on the go in the matters of seconds. Okay, so you have your two EBS volumes here, and what I want to tell you now is a cool behavior. So what happens if you terminate your instance? Well, remember, and I will tell you again, this one root volume of eight gigabytes has the delete on termination attribute.

## Finally 🌟

How do you know? Well, if you go into your storage and then go to your block devices, into this table right here, and scroll all the way right, you see the first one has delete on termination yes and the second one no. So why this one is yes? Well, I don't know if you remember, but when you go through the process of launching an instance, And then you scroll down to the storage, in there, if you click on advanced, you can see the fact that it is your root of eight gigabytes and by default, this delete on termination attribute is yes, which makes sense, but you could set it to no if you wanted to keep the root after terminating your instance. So this explains why we see from before, the yes in the table. And so therefore, if you go ahead and terminate your instance which you should, so it says successfully terminated so it's going to really remove it from here. You can go back into my EBS volumes. You can refresh them. And what's going to happen is that the root one soon is going to be available so because it's going to be detached from your EC2 instance and then it's going to be terminated. So your eight gigabyte volume has now disappeared. Only your two gigabyte volume is left and if you go to your EC2 console, well, it says that your first instance has been terminated.

## Day-17 Finished 🚀🎉

Today you have learned about AWS EBS Volumes Attachments, AZ Boundaries, and their Termination Behavior. 📊
