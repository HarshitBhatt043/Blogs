---
title: "🔒 AWS CCP - Day-04 - Master AWS IAM Policies for Secure Access Control 🔒"
seoTitle: " Learn AWS IAM Policies | AWS Cloud Practitioner"
seoDescription: "Day 4 of your AWS CCP prep: Dive into IAM policies. Understand how they work and why they're crucial for cloud security."
datePublished: Thu Apr 18 2024 04:00:56 GMT+0000 (Coordinated Universal Time)
cuid: clv4prxob000908jzeyh4g40t
slug: aws-ccp-day-04-master-aws-iam-policies-for-secure-access-control
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713327857339/e0aecb6a-5465-4034-a6ac-b85d023b340f.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## IAM Policies Overview 📜

Okay, so now let's discuss IAM policies in depth. So let's imagine you have a group of developers, Alice, Bob, and Charles, and you attach a policy at the group level. In that case, the policy will get applied to every single member of the group so both Alice, Bob, and Charles, you all will get access and inherit this policy. Now, if you have a second group with operations with a different policy, David and Edward will have a different policy than your group of developers. If you're Fred, you have the possibility not to belong to a group. And you have the possibility to create what's called an inline policy which has a policy that's only attached to you. So you could or could not belong to a group, you can have inline policies for whatever user you want. And finally, if both Charles and David belong to the audit team and you attach a policy to the audit team as well, Charles and David will also inherit that policy from the audit team. So in this case, Charles has a policy from developers and a policy from the audit team. And David has a policy from the audit team and a policy from the operations team. 🤝

### Policy Structure 📋

Now, in terms of the policy structure, you just need to know at a high level how it works, as well as how it is named. So this is something you will see quite a lot in AWS, so get familiar with this structure.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "1",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::example-bucket/*"
    }
  ]
}
```

And so an IAM policy structure consists of a version number, so usually it's 2012-10-17, this is the policy language version. And ID which is how to identify that policy, this is optional. And then more statements, and statements can be one or multiple ones, and a statement has some very important parts. So the Sid is a statement ID, which is an identifier for the statement, which is optional as well, so on the right-hand side is the number one. The effect of the policy itself, so it is whether or not the statement allows or denies access to certain API, so in the right-hand side, this says allow, but you can see deny as well. The principle consists of which accounts, user or role which, to which this policy will be applied to. So in this example, it's applied to the root accounts of your AWS accounts. Action is the list of API calls that will be either denied or allowed based on the effect. And the resource is a list of resources, to which the actions will be applied to. So in this example, it is a bucket, but it could be many different things. And finally in, not represented here but there's a condition to which when this statement should be applied or not, and this is not representative here because it is optional. 🤖

## Introduction to IAM Policies 🛡️

Okay, so let's play with IAM policies. So if you go into your user groups right now, you can see that your group admin contains, and this UI is a bit bugged, contains one user, Administrator. So if you go on the right-hand side and go to your services and go to IAM, so you'll go to the IAM service. So, this user is an admin user. And therefore, if you go to, for example, users, you can see all the users. Okay, great. 🚀

### Removing User from Admin Group 🚫

So, now what you're going to do is you're going to remove Administrator from the admin groups. You're going to remove this user and the user will lose the group permissions, that's true. So the user has been removed from the group and how do you make sure that this is applied? Well, if you go on the right-hand side and now refresh this page, as you can see, you need permissions to access this page and your user Administrator is not authorized to perform IamListUsers on this page. So that makes sense, right? Because you removed the user Administrator from the admins group. 🔄

### Attaching Permissions to User Directly 🔗

So, what you can do is you can fix this and to fix it, you can go into your users. Go to Administrator and now you can attach permissions directly to your Administrator user. So two ways of doing so, number one is to add permissions and use policies that already exist or that you created or add an inline policy to just add policies directly to the user. 🧩

### Adding IAM Read-Only Access 📖

So, you're going to add permissions and you're going to attach existing policies directly and you will search for IAM. And you're going to look for IAM read-only access. You review, you add these permissions and now your user Administrator has IAM read-only access. What does that mean? That means that, for example, if you refresh this page... Then, as we can see, the user Administrator does exist. 📚

### Testing Restricted Access 🚧

But, for example, if you go to groups and try to create a group and call it "developers" and create this group, you're going to get an exception because you're not authorized to do create group, you were only authorized to have read-only access to IAM. So this really shows the power of IAM and so on. 🚫

### Adding User to Multiple Groups 🤹‍♀️

So, now if you go to your user groups, you can do two things. So number one, you can go into the admin group and you're going to add back this Administrator user so that you have administrator access. The second thing you're going to do is you're going to create a group named "developers". And you're also going to add Administrator into this group and you're going to attach a policy, whatever the first policy you found it was direct connect to read-only access and then create this group. 🔄

## Understanding Inherited Policies 🧬

It doesn't matter which policy you're attached to, I just want to show you a behavior. Okay so, now you have two groups, you have the admins and the developers, and the user Administrator is in both groups. So what's going to happen is that if you click on the user Administrator and look at the policies it has, it has three policies. 🤔

## Exploring IAM Policies 🗺️

One that was attached directly named IAM ReadOnlyAccess. One that was in two that were in Attached From Groups. The first one is administrator access from the group admin. And this one, it was direct connect read-only access from the group's developers. So, as we can see, the policies get inherited in different ways through the IAM permissions. 🧭

### Understanding Policy Structure 🏗️

So finally, I want to show you how policies work. So if you go to policies, you have a list of all the policies available within AWS right here, their managed policy.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*"
    }
  ]
}
```

So this one is administrator access and you've been using it before. And if you look at the policy, JSON forum, as we can see we have a version and we have a statement that statement contains one statements and the effect is allowed. So to authorize action is "", that means any action resource is "", that means any resource. So you allow all the actions on all the resources therefore making this policy an administrator access policy. 📃

### Creating Custom Policies 📝

There's also a way for you to create your own policy. So you can go back to your policies and create a policy and you have two ways of doing it. Either, you want to write plain and simple JSON or you can use the visual editor, and this is quite handy. ✏️

## Clean-up 🧹

Okay. So, just to finish, let's do a few things. In user groups, you're going to delete the developers group cause you don't need it and you need to type the name of the group, so you will type developers and click on delete. And also on your user as Administrator, you're going to remove the policy that was attached directly because you don't need this IAM read-only policy, you will just remove it and you're good to go. So, now your user Administrator has full administrator access because it is inherited from the admin group. And so obviously if you go back to your IAM also on the right side, as we can see, everything is working just fine. So you will refresh and here we go, things are working.

## Day-04 Finished

So that's it, we have finished AWS IAM Policies for Secure Access Control 🎉👍