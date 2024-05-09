---
title: "🌟 AWS CCP - Day-19 - EC2 Deployments with Custom AMIs! 🌟"
seoTitle: "Unlock Efficiency and Harness the Power of Custom AMIs "
seoDescription: "Discover how custom AMIs revolutionize EC2 deployments on AWS, streamlining setup processes, ensuring consistency, and even opening doors to new revenue."
datePublished: Thu May 09 2024 04:00:42 GMT+0000 (Coordinated Universal Time)
cuid: clvyq0inz000609l844ri3s0r
slug: aws-ccp-day-19-ec2-deployments-with-custom-amis
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715199655134/4ea06149-2224-4ea1-8c36-8ea633ff11ca.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to AMI 🖥️

AMI stands for Amazon machine image and represents a customization of an EC2 instance. So you can use AMIs you created by AWS or customize them into your own. What is in an AMI? Well, you have your own software configuration, you can define and set up the operating system, set up any monitoring tool, and if you create your own AMI, you'll get faster boot time and configuration because all the software you want to install onto your EC2 instance is prepackaged through the AMI. 💻

## Types of AMIs 🛠️

So you have to build your own AMIs, which can be built for a specific region and then copied across regions if you want to leverage the AWS global infrastructure. You can launch EC2 instances from different kinds of AMIs. What we've been doing so far in this series is using a public AMI provided by AWS. The Amazon Linux 2 AMI is a very popular AMI for AWS and is provided by AWS themselves. But you can create your own AMI, which means you have to make and maintain them yourself. There are tools to automate this, but this is a task you have to do as a cloud user. Alternatively, you can launch an EC2 instance from an AWS Marketplace AMI, which is an AMI made by someone else and potentially sold by someone else. It's quite common for vendors on AWS to create their own AMIs or software configurations and sell them through the Marketplace AMI to save time. Even you as a user could create a business of selling AMIs on the AWS Marketplace; this is something that some businesses do. 💼

## AMI Process Overview 🔄

The AMI process from an EC2 instance, how does it work? Well, you start an EC2 instance and customize it. Then you stop the instance to ensure data integrity is correct. Then you can build an AMI from it, which also creates EBS snapshots behind the scenes. Finally, you can launch instances from other AMIs. 🔄

# AMI Usage 🚀

So if you have US-EAST-1A, you can create the same instance as US-EAST-1B. The process is to launch the instance in US-EAST-1A, customize it, create an AMI from it; this will be your custom AMI. Then in US-EAST-1B, you can launch from that AMI and effectively create a copy of your EC2 instance. 🌐

## Launching an Instance 🚀

For this, you'll launch an instance. You'll choose Amazon Linux 2, select the T2 micro, choose your key pair, select an existing security group, keep the same storage, and for advanced details, go for user data, copy everything from the given script, and paste it there. 🚀

```bash
#!/bin/bash

# Update package repositories
sudo yum update -y

# Install HTTPD web server
sudo yum install -y httpd

# Start HTTPD service
sudo systemctl start httpd

# Enable HTTPD service to start on boot
sudo systemctl enable httpd
```

### Launching and Waiting 🕒

Then you launch your instance. Your instance is launched, and it will run through the EC2 using the script to install the Apache web server. So even if it says 'running,' you need to give it time for the EC2 user data script to run for the first time. This might take a minute or two. Just wait for it to be done. Then, at some point, when you refresh, you will see the test page from the Apache web server, and you're good to go. ⏳

## Creating an AMI 📸

So what you're going to do is create an AMI to save the state of your EC2 instance and reuse that. Right-click, do image and templates, then create an image. Call it 'demo image,' create your own AMI, leave the settings as is, and click on create image. Now an AMI is being created. When it's done, you'll see your demo AMI registered. 📸

## Launching Instances from AMI 🚀

Now you can launch instances from this AMI by clicking there or from the instance creation page. Choose 'From AMI' and select the demo image. Select a key pair, edit network settings, and copy the below script into user data. Launch the instance. 🚀

```bash
#!/bin/bash

# Create HTML file for web server
cat <<EOF | sudo tee /var/www/html/index.html
<!DOCTYPE html>
<html>
<head>
  <title>Welcome to My Web Server</title>
</head>
<body>
  <h1>Hello, World!</h1>
  <p>This is a test page served by Apache HTTP Server on Amazon EC2 instance.</p>
</body>
</html>
EOF
```

# Final Steps and Benefits 🌟

Wait for it to be fully created. Your instance from your AMI is now running. Take the public IP address and see the ***Hello World*** . As you can see, this was much quicker because you didn't have to install HTTPD again. This is the whole power of AMIs. You can imagine, it could be more than that; it could be security software, prerequisite software, and so on. Install it, package it as an AMI, and then you have a much faster boot-up. And you're good to go. 🎉

# Day-19 Finished 🎉

Today you have learned about how to Launch Your EC2 Instance with Custom AMI. 🚀