---
title: "🔒 AWS CCP - Day-03 - Essential Guide to Securing Your AWS Account with IAM 🔒"
seoTitle: "AWS IAM for Cloud Security: Your Essential CCP Guide"
seoDescription: "Secure your AWS account like a pro! Learn IAM fundamentals, user/group best practices, and the power of least privilege."
datePublished: Wed Apr 17 2024 04:00:28 GMT+0000 (Coordinated Universal Time)
cuid: clv3abhgf000m08k0evxagow8
slug: aws-ccp-day-03-essential-guide-to-securing-your-aws-account-with-iam
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713256339243/970639ed-8257-4562-bd1c-b0c9b43b8d89.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Introduction to IAM🚪

IAM stands for identity and access management. It is a global service because in IAM, we are going to create our users and assign them to group. 🌍

### Creating Users and Groups 🧑‍🤝‍🧑

So we've already used IAM without knowing, when we created an account, we created a root accounts, and has been created by default. This is the root user of our accounts. And the only things you should use it for is to set up your account as we'll do it right now. But then you shouldn't use that account anymore, or even share it. 🌱

What you should be doing instead, is create users. So you will create users in IAM, and one user represents one person within your organization. And the users can be grouped together if it makes sense. 👥

### Grouping Users 🔄

Let's take an example we have an organization with six people. You have Alice, Bob, Charles, David, Edward and Fred so all these people are in your organization. Now Alice, Bob, and Charles they work together. They're all developers. So we're going to create a group called the group developers who regrouping Alice, Bob and Charles. And it turns out that David and Edward also work together. So we're going to create an operations group. Now we have two groups within IAM. 🤝

#### Important Group Guidelines

Now groups can only contain users, not other groups. So this is something very important to understand. Groups only contain users. Some users don't have to belong to a group. For example, Fred right here is alone, he does not correspond to any group. That is not best practice. But it is something you can do in AWS. 🚫

### User Permissions and Policies 📜

And also, a user can belong to multiple groups. That means that for example, if you know that Charles and David worked together, and they're part of your audit team, you can create a third group with Charles and David. And as you can see, now, in this example, Charles and David are part of two different groups. 🔄

### IAM Policies and Permissions 🛡️

So why do we create users and why do we create groups? Well, because we want to allow them to use our AWS accounts and to allow them to do so, we have to give them permissions. So users or groups can be assigned what's called a JSON document, an IAM policy. 🗂️

#### Least Privilege Principle 🔐

And so in AWS, you don't allow everyone to do everything that would be catastrophic, because a new user could basically launch so many services and they will cost you a lot of money or would be valid for security. So in AWS, you apply a principle called the least privilege principle. 💼

## Exploring the IAM Console 🔍

Okay, so let's explore the IAM console. For this, just type IAM and go straight into the IAM console. So this is where we're going to be managing our account. And as you can see from the top right corner, it says Global. That means that this does not require a region selection and IAM is a global service. So no matter where you are, you will have the same users across all your regions. That makes sense. 🌐

## Creating IAM Users 🧑‍💻

Next, what we're going to do is to go ahead and create our first users. We go under Users and on user, we're going to add a user. So why do we need users? Well, that's because we're using the root account. If you go on the top right, it just gives your account ID. So that means you’re using the root account and it has too much permissions. And so what you want to do is instead to create admin users and regular users and use them within AWS. So let's go and create our first user. It's going to be named Administrator, and I want to provide myself access to the management console. 🚀

### Creating an IAM User 🧑‍💼

Now you can see right now, there's an option says, Hey, do you want to use a user in Identity Center? That's the recommended way, or do you want to create an IAM user? Choose create an IAM user. So you scroll down and then you have to have a console password. Now, if this was for someone else, we would use an auto-generated password but because this is for yourself, You can just enter a password that you know of. And you need to make sure that you are complaint with the rules of the password right there. Then you can disable the box create a new password at sign in. But you should do this if it was another user you're creating an account for. Then you click on Next. 🔄

## Creating User Groups 👥

Okay, so next, we need to add a user to group or attach permissions to it directly. But we're going to create groups because it's much easier. So let's create a group. And this group name is going to be admin. And the admin group is going to have one policy attached called AdministratorAccess. So you take this one, you scroll all the way down and you click on Create user group. So now the user can be added to the group admin and because we will be in this admin group, we will inherit the policies of that group, which is AdministratorAccess. Click on Next. 🔄

### Review and Creation 🔄

Here we can review and create the user. As you can see, you have optional tags. Tags are everywhere in AWS. They can help to include some extra information about your data but they don't impact how your account is functioning. For example, you could enter a tag and say that the department of Administrator is engineering. This is the kind of usage for tags, but again, it's just information you can add for users, for groups and pretty much any resources within AWS. Okay, so let's create this user. 📝

## User Creation Confirmation ✔️

Now, the user is successfully created, and what you can do is that you can email the sign in instruction. You can download the CSV to have the username and the password, or you can click there and return to the user list. And now let's explore what we have created. So under user groups, you will find the group admin and if you click on it, you can see that there's one user in this group, which is the Administrator user. And if you look at the group permissions, there's a policy name attached to the group, which is the administrator access, which provides full admin access to any users within the group. And so if you go and click on the user, Administrator, so this is a user you can also get back from this menu on the left-hand side and just click on user Administrator. 🧑‍💻

## Logging in with the IAM User 🔑

Okay, so if you click on the user, Administrator, back to it. Okay, great. We have these permissions, and the permissions associated with your user is AdministratorAccess and this is a managed policy that we inherited from the group admin. Okay, so we have our users and we have our groups and now we're going to see how to log in with that user Administrator. So to do so, let's go back into the dashboard. And on the right-hand side of the dashboard, we have some summary about our AWS account. 📊

### Customizing Sign-In 🛠️

So the account ID is right there.The account alias is what you can set to log in to your account faster because remembering numbers sometimes is difficult. So you can create an account alias and you just have to specify an alias that you like. For example, Administrator-aws--v2, and click on Save Changes. Now, this is a unique alias for your account. You're not gonna be able to use this alias for other account. And now we have a sign in URL on the right-hand side that is customized for your alias. 🆔

### Signing in as the IAM User 🔒

So if you click on copy this URL, you need to open it in a new tab, but it must be an incognito tab or a different web browser. Now you are taken again to the login page of AWS and as you can see, you have three fields in a row. You have the account ID, the IAM username, and the password. 🔒

#### Verifying IAM User Status ✅

So what's happening here is that you, using this URL, are taken to a sign in page as an IAM user. And how do we know this? How can we get back to this page if you wanted to? Well, when we went into the sign in, we had two options, either root user which will log you in as a root user or IAM user in which case, you just need to enter the account ID or the account alias. And then click on Next, which will take you into the page we had from before. So now in this page, what you need to do is to enter you're IAM username and the password that you just created, and then click on sign in. 🔄

## IAM User Functionality 🎉

And you are now logged in as an IAM user in the console. So how do we know this? Well, if you're logged in as a root user, as you can see when you click on the account it says My account and the account number. This is a root user. But if we go on the right-hand side, we can see that there is Administrator@ and then the account alias. And so what we can see is that Administrator is the IAM user Administrator, and then we're at my accounts and the account number. So we know on the right-hand side that we're logged in as an IAM user. 🧑‍💼

## Day-03 Finished

So that's it, we have finished Introduction to IAM, IAM Users and Groups 🎉👍