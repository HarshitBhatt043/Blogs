---
title: "🌟 AWS CCP - Day-18 - Unveiling the Magic of EBS Snapshots for Effortless Data Protection! 🌟"
seoTitle: "Unlocking the Power of EBS Snapshots in AWS"
seoDescription: "Discover how EBS snapshots revolutionize data management in AWS! Learn key insights and strategies for seamless backup, restoration, and cost optimization."
datePublished: Wed May 08 2024 04:00:40 GMT+0000 (Coordinated Universal Time)
cuid: clvxakmi900040ambhhcq7u2b
slug: aws-ccp-day-18-unveiling-the-magic-of-ebs-snapshots-for-effortless-data-protection
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715110915901/d7e94094-5467-4107-8792-7d3716239d8f.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to EBS Snapshots 📸

So now let's talk about EBS snapshots. You can take your EBS volumes and make a snapshot, which is also called a backup, at any point in time that you want to. The idea is that you will be able to back up the state of it, and even if your EBS volume is terminated later on, you could restore it from that backup. 🔄

## Creating EBS Snapshots 📷

Now to make a backup, it is not necessary to detach your volume prior to doing the backup, but it is recommended just to make sure that everything is clean on your EBS volume. And why do you do snapshots? Well, you can obviously restore them, but you can also copy snapshots across availability zones or regions, and the idea is that you would be able to transfer some of your data to a different region on AWS to leverage the global infrastructure. 🌐

## Transferring EBS Volumes 🔄

So if you look at US-EAST-1A, and you want to transfer an EBS volume to US-EAST-1B, the way you do it is that you would have the EBS volume attached to the EC2 instance, and then you would snapshot it. So maybe you would stop the EC2 instance ahead of time to make sure the snapshot is clean or you could just do it on the fly. It is really up to you and based on how you have programmed your EC2 instance. Now the EBS snapshots exist in your region. And that EBS snapshot can be used to restore a new EBS volume in another availability zone. And then now that this is done, you can attach the new EBS volume to an EC2 instance in US-EAST-1B. And there you go. You have successfully and effectively transferred an EBS volume through a snapshot across AZ. 🚀

## Additional Features of EBS Snapshots 🌟

So some features you need to know about for EBS Snapshots is the first one, an EBS snapshot archive. So it allows you to move your snapshots to another storage tier called an archive tier, and that tier is 75% cheaper. So your snapshot is going to be moved, you know, manually or however you set it to the archive tier. But if you have it in the archive, it takes you between 24 to 72 hours to restore from the archive. So these are for snapshots that are not very important to you to restore it in a rush, okay, but you wanna save some cost on them. The second feature is around recycle bin for EBS snapshots. So by default, when you delete snapshots, they're gone. But you can set up a recycle bin, and the recycle bin will have all the snapshots that are deleted. And then after a while, maybe you can specify from one day to one year, the snapshots are gone from the bin. So on deleting the snapshots, they would go into the recycle bin. And you may have, for example, one year to recover the snapshots, which allows you to protect yourself against accidental deletion. 🗑️

# Snapshots 📸

So you have this two gigabytes gp2 EBS volume available to you and you can take a snapshot from it. So if you do actions, you can create a snapshot. So you can add a description, for example, demo snapshots and then click on create snapshots. So then on the left-hand side menu, instead of volume, you can click on snapshots and snapshots should use a list of all the snapshots you have. And you will see, it is completed, it is 100% available, and you get some information around that snapshot itself. 📷

## Copying Snapshots ✨

First of all, what you can do is that you can copy that snapshot into another region. So if you right-click and do copy snapshots then, you can copy the snapshot into any destination region that you want. And this can come in very handy in case you want, for example, to have a disaster recovery strategy to make sure your data is backed up in another region of AWS. 🔄

## Recreating Volumes 🔄

Another thing you can do is take the snapshot and you can recreate a volume from it. So, action, create volume from snapshots and you choose a two gigabytes, gp2 volume and then the target AZ doesn't have to remain eu-west-1a, it can be, for example, eu-west-1b. And you can also encrypt this volume if you want to and add some tags. And so, when you click on create volume what's going to happen is that if you go back into your volumes, well now you have two volumes. And one of them, was restored through snapshots. And it is an eu-west-1b. So the idea is that thanks to snapshots you can copy EBS volumes across different availability zones. And that's very handy. 💡

# The Recycle Bin ♻️

If you look again at snapshots you can have a look at what's called the recycle bin. So the recycle bin is a way for you to protect your EBS snapshots from accidental deletion, as well as your Amazon Machine Images. So you can create a retention rule and saying demo retention rule. And then you're saying you'll apply this to all EBS snapshots. And you want them to be retained for one day after deletion which allows you to recover them. So if you click on create retention rule now it has been created and it is going to appear right here at some point. So just refresh the page, and now on the resources, you will see if you have resources in the recycle bin. ♻️

## Archiving Snapshots 🗄️

So let's go back into our snapshots in the EC2 console. So you're going to go into EC2, here you go into snapshots. And what you're going to do is take the snapshots. And first, before you delete it I wanna tell you about the storage tier. So right now it is a standard storage tier. But you can move the storage tier by archiving snapshots. And so like you to move the storage tier into another pricing level, but if you want to restore it of course you will have to wait 24 to 72 hours. So let's go ahead and delete the snapshot. 🗑️

## Recovery from Recycle Bin 🔄

So you'll delete the snapshots. And before it used to completely delete the snapshots and you couldn't recover it. But now, thanks to the recycle bin, well, if you refresh there your resources you can now see that your snapshot will appear there. And what you can do is click on it and recover it. Yes, recover resources and voila. It's back into your snapshots on your EC2 console. That was pretty awesome, right? 🎉

# 🎉 Day-18 Finished 🎉  
Today you have learned about AWS EBS Snapshots and about their Backup, Recovery, Transfer. 🚀