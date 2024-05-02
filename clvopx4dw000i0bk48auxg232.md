---
title: "AWS CCP - Day-14- Securely Connecting and Configuring IAM Roles for AWS Instances 🛡️"
seoTitle: "Mastering AWS Security: Configuring IAM Roles for EC2 Instances"
seoDescription: "Learn how to securely manage AWS credentials on EC2 instances with IAM roles. Enhance your AWS security and protect sensitive information effectively."
datePublished: Thu May 02 2024 04:00:22 GMT+0000 (Coordinated Universal Time)
cuid: clvopx4dw000i0bk48auxg232
slug: aws-ccp-day-14-securely-connecting-and-configuring-iam-roles-for-aws-instances
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714312043661/0e303739-2f93-43d3-9989-fedfcc40cd19.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Connecting to EC2 Instance 🔌

So let's practice using IAM roles for your EC2 Instance. So at first, you're going to connect to your EC2 Instance. You can SSH, or you can use EC2 Instance Connect if you want to. So back into your instance with EC2 Instance Connect right here. And you are in your Instance. So as you can see, you are ec2-user@ and the private IP. So regardless if you're using EC2 Instance Connect or SSH through your terminal, or whatever, through PuTTY. Then if you see this, you are at the same stage.

## Using Linux Commands 💻

So now you can just do some Linux commands. For example, ping Google, and you can get some information out of Google. And you can do Control + C to go out of it or issue any kind of Linux commands you want. So you'll type clear to clear the screen and next you have to run some IAM commands.

## Configuring IAM 🛡️

So the cool thing is that's the Amazon Linux AMI you're using right now comes with the aid of a CLI. And so, as you can see, it is installed. So what you can do is start using some commands. For example, `aws iam list users`. And if you do so, it says unable to look at credentials. You can configure credentials by using `aws configure`.

### The Problem with `aws configure` ❌

So you could indeed run `aws configure` to configure the credentials and specify an Access ID a Secret Access key, and a region name. But this is a really, really, really bad idea. And the reason is that if you run `aws configure` and enter your personal details onto this EC2 Instance, then anyone else in your accounts could again connect to your EC2 Instance, for example, using EC2 Instance Connect and retrieve the value of these credentials in your instance, which is not what you want. This is something that's really, really bad. And so as a rule of thumb, never, ever, ever enter your IAM API key. So the Access Key ID and the Secret Access key into an EC2 Instance. This is horrible and if you see someone doing it, stop them.

## Using IAM Roles 🛡️

Instead, what you have to do is use IAM roles. So if you remember, earlier in this series when we were in the management console and we were in IAM, we had created an IAM role. So let's go back into the Roles. You had this demo role for EC2 that had one policy attached called IAMReadOnlyAccess. So you are going to attach this role onto your EC2 Instance to provide it with credentials. So how do you do this?

### Attaching IAM Role 🔄

For this, you can go into Security. And as you can see, there is no IAM Role right now onto your instance. So what you can do is go back to your Instances, Action, Security, and then Modify IAM role. Here you have to choose an IAM role. So you have DemoRoleForEC2 and click on Save to attach this IAM role into your Instance. So if you go back to Security, now the IAM role attached to Instance DemoRoleForEC2. So the effect of this is that now if you do `aws iam list users` and press Enter, where you are getting a response around the users from IAM. So as we can see, you did not run the command `aws configure`. You just attached an IAM role and ran this command. And it works. And as a proof, if you go into this role and detach this permission, so now it's gone, and run the command again, you're getting an access denied.

## Finally 🎉

So the role is really linked now to the EC2 Instance. And this is how you provide AWS credentials to your EC2 Instances only, only through IAM roles, So if you go back to IAM and you attach a policy to this role and go back to IAMReadOnlyAccess, attach this policy and then rerun the command, you get an access denied because sometimes it can take a little bit of time to propagate the changes from IAM into AWS. But if you run it one more time, you're getting the output you expect, which is what you want. So this is very important for you to understand this, use IAM roles for your EC2 Instances.

# Day-14 Finished 🚀🎉

Today you have learned about how to Securely Connect and Configure IAM Roles for AWS Instances.
