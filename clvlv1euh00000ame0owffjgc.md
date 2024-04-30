---
title: "💻 AWS CCP - Day-12- Exploring AWS Security Groups and Keeping Your Instances Safe 🔒"
seoTitle: "AWS Security Groups: Essential Insights & Advanced Tips"
seoDescription: "AWS Security Groups with insights on network protection, simplified management, and advanced communication between EC2 instances."
datePublished: Tue Apr 30 2024 04:00:22 GMT+0000 (Coordinated Universal Time)
cuid: clvlv1euh00000ame0owffjgc
slug: aws-ccp-day-12-exploring-aws-security-groups-and-keeping-your-instances-safe
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714292097716/456db373-6273-4372-8cb1-69d81445f6bb.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to Security Groups 🛡️

Let's talk about these firewalls around our EC2 instances. So we briefly configured one in the previous Blog but security groups yet again, are going to be fundamental into doing network security in the AWS cloud. They will control how the traffic is allowed into and out of your EC2 instances.

# Functionality of Security Groups 🔐

Security groups are going to be very easy, they only contain allow rules, so we can say what is allowed to go in and to go out, and security groups can have rules that reference either by IP addresses, so, where your computer is from or by other security groups, so as we'll see, security groups can reference each other.

## Inbound and Outbound Traffic Control 🔄

So here, let's take an example, you are on your computer, so you are on the public internet and you're trying to access your EC2 instance from your computer. You are going to create a security group around your EC2 instance, that is the firewall that is around it and then this security group is going to have rules. And these rules are going to say whether or not some inbound traffic, so from the outside into the EC2 instance is allowed, and also if the EC2 instance can perform some outbound traffic.

## Anatomy of Security Group Rules 📜

Now let's do a deeper dive, right? Security groups are a firewall on our EC2 instances and they're going to regulate access to ports. They're going to see the authorized IP ranges. Would it be on IPv4 or IPv6? These are the two kinds of IP on the internet, and this is going to control the inbound network. So from the outside to the instance and the other network from the instance to the outside.

## Configuration and Best Practices ⚙️

So they will be the type, the protocol, so TCP, the port allowing it, so where the traffic can go through on the instance and the source which represents an IP address range and 0.0 0.0/0 means everything and this here means just one IP. So you're not expected to know how to properly configure a security group for the (indistinct) exam, but they're so important, so I wanna talk about them.

## Implementation and Use Cases 🛠️

So we have our EC2 instance and it has one security group allow attached to it that has inbound rules and outbound rules. Your computer is going to be authorized on say port 22. So the traffic can go through from your computer to the EC2 instance, but someone else's computer, that's not using your IP address because they don't live where you live, then if they're trying to access your EC2 instance they will not get through it because the firewall is going to block it and it will be a timeout.

## Security Group Management 🛡️

Then for the outbound rules by default, our EC2 instance for any security group is going to be by default allowing any traffic out of it. So our EC2 instance, if it tries to access a website and initiate a connection it is going to be allowed by the security group. So this is the basics of how the firewall works.

# Additional Considerations 📌

Now good to know, what do you need to know with security groups? Well, they can be attached to multiple instances. There's not a one to one relationship between security group and instances and actually an instance can have multiple security groups too. Security groups are locked down to a region/VPC combination.

## Troubleshooting and Advanced Features 🛠️

So if you switch to another region, you have to create a new security group or if you create another VPC, you have to recreate the security groups. The security groups live outside the EC2. So as I said, if the traffic is blocked the EC2 instance won't even see it. It's not like an application running on EC2 it's really a firewall outside your EC2 instance. To be honest, and that's just an advice to you from devops person to devops person but it's good to maintain one separate security group just for SSH access, usually SSH access is the most complicated thing and you really wanna make sure that one is done correctly.

### Testing and Troubleshooting 🛠️

So I usually separate my security group for SSH access separately. If your application is not accessible, so timeout, as we saw this in the last Blog, then it is a security group issue. So if you try to connect to any port and your computer just hangs and waits and waits that's probably a security group issue, but if you receive a connection refused error, you actually get a response and connection refused, then the security group actually worked, the traffic went through and the application was errored or it wasn't launched or something like this. So this is what you would get if you get a connection refused. By default, all inbound traffic is blocked and all outbound traffic is authorized.

### Advanced Features and Load Balancers 🔄

| Source Security Group | Destination Security Group | Description                                                                                                                                                       |
|-----------------------|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Group 1               | Group 2                    | Allows EC2 instances associated with Group 2 to communicate with EC2 instances associated with Group 1 on specified ports, simplifying security configurations. |
| Group 1               | Group 1                    | Enables communication between EC2 instances associated with the same security group (Group 1), regardless of their IP addresses.                                 |
| Group 2               | Group 1                    | Allows EC2 instances associated with Group 1 to communicate with EC2 instances associated with Group 2 on specified ports, facilitating secure communication. |
| Group 3               | Group 1                    | Denies communication between EC2 instances associated with Group 3 and EC2 instances associated with Group 1 since Group 3 is not authorized in Group 1's inbound rules. |

Now there is a small advanced feature that I really, really like, and I think it's perfect if you start using load balancers, which is how to reference security groups from other security groups. So let me explain things. So we have an EC2 instance, and it has a security group, what I call group number one, and the inbound rules is basically saying, I'm authorizing security group number one inbound and security group number two. So, why would we even do this? Well, if we launch another EC2 instance and it has security group two attached to it, well, by using the security group (indistinct) rule that we just set up, we basically allow our EC2 instance to go connect straight through on the port we decided onto our first EC2 instance.

# Exam Preparation and Port Knowledge 📚

Similarly, if we have another EC2 instance with a security group one attached, while we've also authorized this one to communicate straight back to our instances. And so regardless of the IP of our EC2 instances because they have the right security group attached to them they're able to communicate straight through to other instances. And that's awesome because it doesn't make you think about IPs all the time. And if you have another EC2 instance maybe with security group number three attached to it, well, because it group number three wasn't authorized in the inbound rules of security group number one, then it's being denied and things don't work. So that's a bit of an advanced feature.

## Recap of Key Concepts 🔑

| Service                      | Port | Protocol | Description                                             |
|------------------------------|------|----------|---------------------------------------------------------|
| SSH (Secure Shell)           | 22   | TCP      | Used to login to an EC2 instance on Linux securely.     |
| FTP (File Transfer Protocol) | 21   | TCP      | Used to upload files into a file share.                 |
| SFTP (Secure FTP)            | 22   | TCP      | Secure File Transfer Protocol, using SSH for security.  |
| HTTP (Hypertext Transfer Protocol) | 80 | TCP   | Access unsecured websites.                              |
| HTTPS (HTTP Secure)          | 443  | TCP      | Access secured websites, standard for secure browsing.  |
| RDP (Remote Desktop Protocol)| 3389 | TCP     | Used to log into a Windows instance remotely.           |

Now going into the exam, what ports you need to know? Well, you need to know something called SSH or Secure Shell. This is the port 22. And this allows you to login to an EC2 instance on Linux. You have port 21 for FTP or File Transfer Protocol which is used to upload files into a file share. And you have SFTP, which is also using port 22, why? Well, because we're going to upload file but this time using SSH because it's going to be a Secure File Transfer Protocol. Then we have port 80 for HTTP and we been using it in the previous blog. This is to access unsecured websites. And you've seen this whenever you go on the internet and you enter HTTP:// and then the address of the website. And you've seen it most likely a lot more like this, you've seen HTTPS, which is to access secured websites which are the standard nowadays. And for HTTPS, it is port 443. Finally, the last port you need to remember is 3389 for RDP, or the Remote Desktop Protocol which is the port that's used to log into a windows instance.

# Day-12 Finished 🎉

Today you have learned about AWS Security Groups.