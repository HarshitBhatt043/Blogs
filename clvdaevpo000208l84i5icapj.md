---
title: "🛡️ AWS CCP - Day-08 - IAM Roles Empowering AWS Services for Secure Access & Control 🛡️"
seoTitle: "Unlocking AWS Security: IAM Roles Unleashed "
seoDescription: "Discover the power of IAM Roles in bolstering AWS security, optimizing permissions with Access Advisor insights, and enhancing security awareness."
datePublished: Wed Apr 24 2024 04:00:49 GMT+0000 (Coordinated Universal Time)
cuid: clvdaevpo000208l84i5icapj
slug: aws-ccp-day-08-iam-roles-empowering-aws-services-for-secure-access-control
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713719457949/7540c119-0a5f-40db-9543-9fcaf2f0f803.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to IAM Roles 🛡️

So we have to talk about the last component of IAM, which is called IAM Roles. On the left-hand side of IAM, you may see zero roles. So some AWS services that you'll be launching will need to perform actions on your behalf, on your account.

## Need for Permissions 🤔

And for you to do these actions, they're just like users, you will need some kind of permissions. So you need to assign permissions to AWS services and to do so, you're going to create what's called an IAM Role.

## IAM Roles: Purpose and Function 🔄

So these IAM roles will be just like a user, but they are intended to be used not by physical people, but instead they will be used by AWS services. So what does that mean? It's a bit confusing.

### Example: EC2 Instance 💻

So for example, you are going to create, an EC2 Instance. An EC2 Instance is just like a virtual server. But so this EC2 Instance may want to perform some actions on AWS and to do so, we need to give permissions to our EC2 Instance. To do so, we're going to create an IAM Role and together they're going to make one entity.

## Role in Action 🚀

And together, once the EC2 Instance is trying to access some information from AWS, then it will use the IAM Role. And if the permission assigned to the IAM Role is correct, then you're going to get access to the call you're trying to make.

## Common Roles 🔄

So some common roles include, EC2 Instance roles, but also other things that perform actions against AWS. For example, Lambda Function Roles or CloudFormation.

## Types of Trusted Entities 🤝

You are going to choose a trusted entity type. And as you can see, we have different types. So we can create roles for either services, if you will. There are also accounts with identities, SAML Federation custom trust policy.

# Creating a Role for AWS Services 🛠️

The only thing you need to know is just that you can create a role for AWS services and amongst them the two most common use cases are to create a role for an EC2 instance or for Lambda function. But when you go here. There are lots of AWS services that can support having roles, okay.

## Creating an IAM Role for EC2 Instances 🖥️

To keep it simple right now, you are going to create a role, an IAM role for the EC2 instances. So let's click on next.

### Assigning Policies and Permissions 📑

Next you're going to have to assign policies and permissions to that role. So you will allow that role to do IAM read-only access. This is going to allow your EC2 instance to read from IAM. You click on next.

### Defining Role Name 📛

Then you have to define a role name. So you choose whatever you want for role name for example, you will enter demo role for EC2. And then you verify that, yes you did have the IAM read-only access and you create this role.

### Role Creation Confirmation ✅

The role has now been created. And if you click on it you can verify that the permissions are applied correctly, the IAM read-only access. And we are not going to use this role right now. You will stop right here.

### Future Use of the Role 🔮

But when we get to the EC2 section in future you will be leveraging this role allowing the EC2 instance to perform actions against IAM and read data from IAM.

# Security Tools in IAM 🔐

## IAM Credentials Report 📊

So you can create an IAM Credentials Report and this is at your account-level. This report will contain all your account's users and the status of their various credentials.

### Generating Credential Report 📈

Let's generate a credential report. So, on the bottom left, you are going to create a credential report. And you can click on Download Report to just download this report and this will be a CSV file.

As you can see, you have two rows in it. You have your root account, and your account named Administrator. You can see when the user was created, if the password was enabled, When the password was last used, and last changed. When is the next rotation to be expected if you do enable password rotation. Is MFA active? So you can see it's active for your root account, but it is not active for your Administrator account. Then access keys, are they generated or not? Yes, they are created for your Administrator account, but not for your root account. And when were they last rotated, last used, and so on. You can get more information about other access keys and certificates and so on.

This report is extremely helpful if you want to look at some users that haven't been changing their password, or using it or their account. It could be giving you a great way to find which users that deserve your attention from a security standpoint.

## IAM Access Advisor 👩‍🏫

The second security tool you're gonna use in IAM is called IAM Access Advisor. This one is at the user-level and the Access Advisor is going to show the service permissions granted to a user and when those services were last accessed. This will be very helpful because we are talking already about the principle of least privilege, and so using this tool, we're able to see which permissions are not used and reduce the permission a user can get to be inline with the principle of least privilege.

### Understanding IAM Access Advisors 🧭

Next, you want to look at IAM Access Advisors, so you're going to click on your user. Your user is Administrator, and on the right-hand side it says Access Advisor. So this is going to show you when some services were last used. And the recent activity usually appears within four hours. So if you don't see all the data, that's why.

So you can see that, for example, Identity and Access Management was last accessed today. And also the Health APIs and Notifications were accessed today. Why? Well, there is a little bell right there, automatically will be accessed to see if there are any notifications for your accounts. And you'll see what this is, this is the Personal Health Dashboard, okay.

But for the other services, for example, Alexa for Business, or AWS Accounts, or Certificates Manager, you haven't been using them. And so maybe it makes sense for you to remove these permissions from this user because it seems this user is not using these services.

### Understanding Access Advisor's Power 💪

This is the whole power of Access Advisor. And as you can see, there are lots of services in AWS. About 23 pages just like this, so this is about more than 200 services in AWS.

# Day-08 Finished 🎉

So that's it, you have learned about IAM Roles and Security of IAM.