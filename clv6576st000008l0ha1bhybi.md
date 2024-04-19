---
title: "🔒 AWS CCP - Day-05 - Fortify Your AWS Security By Mastering Password Policies and MFA Implementation 🔒"
seoTitle: "Mastering AWS Security: Password Policies & MFA Implementation"
seoDescription: "Learn how to fortify your accounts against cyber threats by setting up robust  Password Policies and Multi-Factor Authentication (MFA)."
datePublished: Fri Apr 19 2024 04:00:28 GMT+0000 (Coordinated Universal Time)
cuid: clv6576st000008l0ha1bhybi
slug: aws-ccp-day-05-fortify-your-aws-security-by-mastering-password-policies-and-mfa-implementation
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713348444590/805a79df-47e8-41db-a191-979a959f339f.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Password Policy 🛡️

Now that you have created users and groups, it's time for you to protect these users and groups from being compromised. So for this, you can have two defense mechanisms. The first one is to define what's called a Password Policy. Why? Well, because the stronger the password you use, the more security for your accounts. So in AWS, you can set up a password policy with different options. The first one is you can set a minimum password length, and you can require specific character types, for example, you may want to have an uppercase letter, lowercase letter, number, non-alphanumeric characters, for example, a question mark and so on. Then you can allow or not, IAM users to change their own passwords or you can require users to change their password after some time, to make your password expired, for example, to say every 90 days, users have to change their passwords. Finally, you can also prevent password reuse so that users when they change their passwords, don't change it to the one they already have or change it to the one they had before. So this is great, a password policy, really is helpful, against brute force attacks on your accounts. 🛡️

## Multi-Factor Authentication (MFA) 🚀

But there's a second defense mechanism that you need to know, going into the exam, and this is the Multi-Factor Authentication or MFA. It is possible you already to use it, on some websites, but on AWS it's a must and it's very recommended to use it. So, users have access to your account, and they can possibly do a lot of things, especially if they're, administrators, they can change configuration, delete resources and other things. So you absolutely want to protect at least your Root Accounts and hopefully all your IAM users. So how do you protect them on top of the password? Well, you use an MFA device. 🛡️

## Understanding MFA 🧠

So what is MFA? MFA is using the combination of a password that you know, and a security device that you own, and these two things together, have a much greater security than just a password. So for example, let us take Alice. Alice knows her password, but she also has an MFA generating token, and by using these things together while logging in, she is going to be able to do a successful login on MFA. So the benefit of MFA is that even if Alice has lost her password, because it's stolen or it's hacked, the account will not be compromised because the hacker will need to also get a hold of the physical device of Alice that could be a phone, for example, to do a login. Obviously, that is much less likely. 🛡️

### Types of MFA Devices in AWS 💻

So what are the MFA devices option in AWS and you should know them going to the exam but don't worry they're quite simple. The first one is a Virtual MFA device, this is what we'll be using and so you can use Google Authenticator, which is just working on one phone at a time, or using Authy which is multi-device they both work the same except one is multi-device. And personally I use Authy because I like the fact that I can use it on my computer and on my phones. So, for Authy you have support for multiple tokens on a single device. So, that means that with a Virtual MFA device, you can have your root account, your IAM user, and another account, and another IAM user, it's up to you, you can have as many users and accounts as you want on your Virtual MFA device, which makes it a very easy solution to use. Now we have another thing called a Universal 2nd Factor or U2F Security Key, and that is a physical device, for example, a YubiKey by Yubico and Yubico is a 3rd party to AWS, this is not the AWS that provided, this is a 3rd party and we use a physical device, because maybe it's super easy, you put it your Key Fobs and you're good to go. So this YubiKey supports multiple root and IAM users using a single security so you don't need as many keys as users otherwise that will be a nightmare. Then your other options, you have a Hardware Key Fob MFA device for example this one provided by Gemalto which is also a third party to AWS and finally, if you are using the cloud of the government in the US, the AWS GovCloud then you have a special Key Fob, that is provided by SurePassID which is also a 3rd party. 📱

# Defining Password Policy 🔐

So you are going to first define a password policy. For this click on Account Settings on the left-hand side. You will find Password Policy and you can edit it. So here you can use the IAM default password policy which composes of kinds of requirements, or you can customize the password policy and force a password minimum length. You can also require uppercase letter, lowercase letter, a number, a non-alphanumeric character. You can also turn on password expiration to turn on, for example, expire after 90 days, or that a password expiration requires administrative resets, or you can allow the users to change their own password, or you can prevent password reuse. So this password can be edited directly from the IAM console, and that's the first part of security. 🔐

## Setting up Multi-Factor Authentication (MFA) for Root Account 🛡️

The second part is around setting multi-factor authentication for your root account. So if you click on the account name and then click on Security Credentials, if you are logged in with the root user you will see My Security Credentials, Root User. You will not have access to this if you're not logged in with a root user. Now, there is a way for you to actually protect your root user, which is the most important account in your AWS accounts, and you can protect it by using multi-factor authentication. 🛡️

### Configuring Authenticator App 📱

So you will call this one your iPhone/android because that is what you have, but you can name it whatever you want. Then you can select the type of MFA device. So it could be an authenticator app, which is something you're going to use, but also it can be a security key or a hardware TOTP token. So you're going to use an authenticator app because it will be virtual. And now you go into the setup of the app. 📱

### Adding MFA Codes and Completing Setup ✅

So what you have to do then is actually launch the app on your phone, and then you click on Show QR Code. So when you show the QR code you need to scan this QR code directly on your phone. So for this you add an account, you scan the QR code, and once scanned it will add the account and start naming it. So you'll just save this, this looks good. And then you get access to MFA codes. ✅

### Using MFA for Login 🔑

So this is a code generated by your phone in real time. And this code is going to change over time. And the reason why the two codes are asked by AWS is that it wants to make sure that the MFA device is set up correctly, and that the codes are accurate. So put the first and second MFA codes into the AWS. And, of course, they will be different on your device. And once these two codes are entered, you click on Add MFA. And as you can see we can register up to eight MFA devices currently. And you can scroll down and see them right here on the list. 🔑

### Login Using MFA 🔒

So the multi-factor authentication MFA 1 is called your phone that's been created right now. So if you wanted to remove it, you can remove it, and so on. But so how do you use MFA? Well now if you log out of AWS and you log back in, so you're going to use your root account and your password. Now after doing a successful login you have the MFA code to enter. And so you open your app and enter the code that you see, and press Submit. And this way you are logged in. And this is perfect because, well, we add an extra level of security on our account. 🔒

# Day-05 Finished 🎉

So that's it, we have increased our AWS Security By Using Password Policies and MFA 🎉👍