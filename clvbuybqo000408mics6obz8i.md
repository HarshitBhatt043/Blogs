---
title: "🔑 AWS CCP - Day-07 - Creating Access Keys and Configuring AWS CLI with Cloud Shell 🔑"
seoTitle: "Master AWS CLI & Access Keys with Cloud Shell!"
seoDescription: "Unlock the secrets of AWS CLI setup and access keys creation with Cloud Shell! "
datePublished: Tue Apr 23 2024 04:00:16 GMT+0000 (Coordinated Universal Time)
cuid: clvbuybqo000408mics6obz8i
slug: aws-ccp-day-07-creating-access-keys-and-configuring-aws-cli-with-cloud-shell
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713702725908/f793838f-6cc9-4d53-9e60-ec5161f66029.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Creating Access Keys 🗝️

So let me show you how to create access keys. So you're gonna click on your username, and you're gonna go under Security credentials. You will scroll down and you will create an access key. There are some selections you need to make and based on the selection you're doing, for example, you want access key for the CLI, AWS is going to have an alternative recommendation. For example, for the CLI, it's better to use CloudShell. Or to use the CLI V2 and an authentication through the IAM Identity Center. So based on what you wanna do, if it's local code, application running outside of AWS or in AWS and so on, you will have some recommendation in the bottom. For now, we're going to use the CLI and we'll use these access keys and we'll click on to say you understand the above recommendation and you still want to create an access key. So let's create this access key and now this is the only time you'll be able to have access to the access key and the secret access key.

## Configuring AWS CLI ⚙️

The first thing you have to do is to configure your AWS CLI. So you're going to type `aws configure`, and then you are greeted with entering your access key ID. You can just enter your access key ID and press Enter. And then you're greeted with entering your secret access key, which you will enter right here as well. The default region name. So this is a region that is close to you. Choose your own region and you can enter your own region name. The region name, by the way, you can get directly from the dropdown. It shows you the name of the region, as well as the region code. So for me, I'am going to use eu-west-1. You'll press Enter and then the default output format. You'll just press Enter as well. So now your AWS CLI is configured and so you can have a look at how it works.

### Testing AWS CLI ✅

You can do `aws iam list-users` and press Enter. And this will list all the users in your accounts. The user we have right now is called Administrator. It will also give your user ID, ARN, when it was created and when the password was last used, which is very similar to what you would get if you were to go into this UI right here. So the management console and the CLI do provide similar kind of information.

### Managing User Permissions 🚫

Next, I want to tell you what happens if you remove permissions from your users. So you're gonna go to admins and you're going to remove the Administrator user from the group admin. And so again, if you go back to your user Administrator, it doesn't have any permissions. And you did this obviously with your root accounts, not the other accounts. So now if you go into your UI and obviously refresh this page, you're going to get an error saying that yes, you do not have the permissions to do this but let's try to do the same thing with the CLI. So we're going to do an `iam list-users` call and we get no response because actually it was being denied. So the CLI permissions are obviously going to be the exact same as the permissions you get from the IAM console.

## Introduction to Cloud Shell 🌩️

Okay. So I would like to talk to you about an alternative to using the terminal to issue commands against AWS. And this is using cloud shell.

### Accessing Cloud Shell 🛠️

So cloud shell is this icon right there on the top right corner of your screen. And if you don't see it, just make sure you check out the cloud shell availability regions because it's not available everywhere.

### Availability and Region Selection 🌍

And so if you go [here](https://docs.aws.amazon.com/general/latest/gr/cloudshell.html), you can see that there are some regions that's not available. So let's have a look right now with the regions. It's only available in one of these regions. So by the way, I would recommend if you want to follow along to just use one of these regions, then so we can use cloud shell, but if you don't use cloud shell, that is completely fine. If the terminal was working for you, do not worry. You're good to go.

### Features of Cloud Shell ⚡

Okay. So we have cloud shell in here and within cloud shell you could take a minute maybe to launch your environment. You can issue commands. For example, you can issue the AWS commands.

### Default Settings and Functionality 🔄

So cloud shell is basically a terminal in the cloud of AWS. That's free to use. And the cool thing about cloud shell is that whenever you are using the CLI, so for example it was `iam list users`. This is going to return for you an API call as if the credentials being used, where the credentials of the accounts of you using the cloud right now which is why the API calls are working.

### File Management 📁

And by default, you can specify any kind of region you want to do. The API call using the management is region arguments, but in cloud shell, the default region is going to be the region you're currently in logged in right now in cloud shell. So this is another thing that's good to know. Other things that you should know about cloud shell is that you have a full repository. So for example, right now, as you can see you have zero files within cloud shell. But if you just do `echo tests > demo.txt`, this is going to create a text file that contains the word texts tests. And so it turns out that if you happen to restart your cloud shell then this file will stick. So all the files you are creating within your cloud environment, for example this `demo.txt` are going to stay.

### Customization Options 🎨

And the other cool thing you can do about cloud shell is that you can configure it. So you can say what font size you want, smallest medium and large. And so on the tech, the theme you want, so light or dark if you wants safe based or nuts. So resist like a bigger cloud shell for you right now. And also you have the possibility to download and upload files.

### Downloading and Uploading Files 📥📤

So for example, if you want to get the full path to your file, you can just copy it right now. Action and download file, and then do `demo.txt`. And this will go ahead and download the file for you. And alternatively, you could upload your own files into your cloud environments.

### Multi-Terminal Environment 🔗

So I want to tell you these handy options because for us, they are lifesavers. And finally, if you wanted more tabs into this environment you could have a new tab. You can split into column. You have two terminals into cloud shell connected at the same time. So really that once show you the power of cloud shell in this hands-on again, you're doing it. You know, all the commands that data just wants to show you. If you're a power user, then you can do these commands and how they would work with cloud shell.

## Day-07 Finished 🎉

So that's it, you have learned how to create access keys and configure AWS CLI with Cloud Shell 🎉👍