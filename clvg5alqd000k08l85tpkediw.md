---
title: "💻 AWS CCP - Day-10- Launching Your First EC2 Instance and Managing it 🚀"
seoTitle: "Stuck in the Cloud? Learn How to Launch Your First EC2 Instance!"
seoDescription: "Confused about launching EC2 instances on AWS? Get ready to unravel the mystery with a step-by-step guide! From naming to managing"
datePublished: Fri Apr 26 2024 04:00:50 GMT+0000 (Coordinated Universal Time)
cuid: clvg5alqd000k08l85tpkediw
slug: aws-ccp-day-10-launching-your-first-ec2-instance-and-managing-it
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713779596331/facfcc6a-b1b2-402d-b975-9b8b292c9129.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction 📝

You're going to launch your first EC2 instance running Amazon Linux. So for this, you'll be launching your first EC2 instance which is, well, a visual server, and you'll use the console for this. You'll get a high-level approach to all the various parameters you have when launching an EC2 instance, and you'll see there are many, but we'll learn the most important ones. And then we will launch a web server directly on the EC2 instance. Using a piece of code, we will pass to the EC2 instance. That is called the user data. Finally, we'll learn how to start, stop, and terminate our instance.

# Creating an Instance 🚀

## Naming and Tagging 🏷️

For this, you're gonna go into the EC2 console, then you will click on instances and then click on launch instances. So in there, you're able to launch your first EC2 instance, and to do so, you need to add a name and tags. So the name is going to be My First Instance and that is the name tag.

## Choosing Base Image 🖼️

Next, you need to choose a base image for your EC2 instance. This is the operating system of your instance. There's a full catalog that you can search from, but we're going to use the ones from the quick start that are very, very helpful. And the one we'll be using is the Amazon Linux, which is provided by AWS. So in it, you will choose the Amazon Linux 2 AMI. That one is free tier eligible, so we'll just leave it as is. So this gives you Amazon Linux 2, and the architecture you will choose is 64 bit x86. So everything left pretty much as the defaults.

## Choosing Instance Type ⚙️

Next, you need to choose an instant type. And so instant types are going to differ based on the number of CPUs they have, the amount of memory they have, and how much they cost. You have a T2 micro selected. This one is free tier eligible, so it will be free to launch one of them during an entire month if you leave it running, so this is what we'll be using. But in there, you could scroll down and look at other types of instances. For example, T1 micro is also free tier eligible, but that's older generation. And as you can see, you have a bunch of instances right there available to you. Some of them are going to be free tier eligible, some of them will not, and by default, the one that's gonna be free tier eligible is a T2 micro, so we'll be using that one a lot. If you wanted to compare the instance types, you will just click on that link, and it shows you all the type of instances in here as well as how much memory they have and so on. So right now, we'll be using a T2 micro.

## Creating Key Pair 🔑

Next, a key pair to log into your instance. So this is necessary if you use the SSH utility to access our instance, and we will be using the SSH utility, therefore it is required for us to create a key pair. Right now, there is no key pair, and we could proceed without a key pair, but for now we won't do this. So let's go ahead and create a new key pair. And the name is going to be EC2 Tutorial. Then you need to choose a key pair type, so we'll be using the RSA encrypted. And then the key pair formats. So, if you have Mac or Linux or Windows 10, then you can use the .pem format. If you have Windows less than version 10, for example, Windows 7 or Windows 8, then you can do a little shortcut and directly use a PPK which is going to be used for PuTTY, and PuTTY is how you do SSH on Windows 7 and Windows 8. So remember, anything else but Windows 7 and Windows 8, choose .pem, else, use PPK. Okay, that should be clear enough. You're going to create this key pair and it is downloaded for you directly. So now it is selected automatically here.

## Network Settings 🌐

Next, you have to go into network settings, so for now, you will not touch anything. Your instance is going to get a public IP, and then we need to connect to our instance. And so for this, there is going to be a security group attached to our instance which is going to control the traffic from and to our instance, and therefore we can add rules. And the first security group created will be called launch-wizard-1, so created by the console directly, and we can define multiple rules. So the first rule we want to have is to allow SSH traffic from anywhere. So we leave it at this, and this will create a rule in our security group to allow SSH traffic, but we also want to allow HTTP traffic from the internet. So you tick that box, and this is because we're going to launch a web server on our EC2 instance, so we need it as well. As we're now going to use HTTP for now, we don't need to tick the second box.

## Storage Configuration 🗄️

Let's configure the storage so then we can compare the storage and as we can see, we have an eight gigabytes gp2 root volume that we will leave it as is, okay, because in the free tier, you can get up to 30 gigabytes of EBS General Purpose SSD storage, so this is good. And you only have one volume necessary. If you go into advanced, you could configure them and see a little bit more information, okay, and the one important thing to note in there is the delete on termination. By default, it is enabled to yes, That means that once you terminate your EC2 instance, then that volume is also going to be deleted.

## Advanced Details 🛠️

Next for advanced details, this is where it gets interesting. So you will skip spot, you will skip IAM instance profile. You will skip all of that, so let's scroll down, let's scroll down, let's scroll down all the way to the bottom, and at the bottom, there is user data. User data is where you pass a script, so some commands, to your EC2 instance to execute on the first launch of your E2 instance and only the first launch. And therefore, on the first launch, you want to be able to pass these commands right there.

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

So you paste everything, and that means that this script is going to be executed when the instance is first started and only once, in the whole life cycle of the instance. And what it's going to do is that it's going to update a few things, then install the HTPD web server on the machine, and then write a file, an HTML file, that will be a web server.

## Summary and Launching 🚀

So finally, for summary, you want to start one instance, this is great, and you can review everything you have there. So let's launch this instance and the instance is going to be launched. Let's go to view all instances, refresh, and now your instance is in pending state. So it's gonna take about 10, 15 seconds for the instance to come up, and this is the whole power of the Cloud. Thanks to the Cloud, you are able to create an instance or 100 of them very quickly in less than 10 seconds without you owning any single server. So that is extremely powerful, and we just scratched the surface of the power of the Cloud.

# Instance Details

So as you can see now, your instance is running, and right now I wanna tell you a few things. The first one is that the instance name is my first instance and there's an instance ID which is just a unique identifier for your instance. There is a public IPv4 address, this is what you're going to use to access your EC2 instance, or there is a private IPv4 address which is how to access that instance internally on the AWS network, which is private. The instance state is running, and you get some information around host name, private DNS, which instance that you have, so t2 micro, as well as, if you scroll down, the AMI you're using, which is Amazon Linux 2, and the key pair you're using, which is EC2 Tutorial. So you can have a look at a few details in there. You have more information, for example, on security. You get some information on the security group which was created called launch-wizard-1 with these in the rules. So port 22 accessible from everywhere and port 80 accessible from everywhere, so you should have something similar. If you don't, start over because you probably missed a step. And the add on rule allowing all communication outwards, which allows the instance to access the internet.

## Accessing Web Server 🌐

So now let's have a look at the web server running on your instance. And for this, you go on public IPv4 address, you copy that or you click on open address and as you can see, it doesn't work. Or if you click on it, copy, and then paste it, you press enter, it's going to work. So it depends on the web browsers you have and so on, but the reason it doesn't work there is that in the URL, you need to make sure that you're using the HTTP protocol. So HTTP colon slash slash and then the IP, because if you use HTTPs, this is not going to work, it's going to give you an infinite loading screen. So please make sure to use HTTP colon slash slash and then the IP address. And in programming, when you do something for the first time, usually say hello world. So this web server is saying hello world. Cool, you have a web server running, this is great.

## Managing Instances 🔄

Now let's explore a few options. So you have an EC2 instance and it's running, but if you don't need it, you can go to instance state and then click on stop instance. And in the Cloud, you can start and stop instances just as you wish, and why would you stop an instance? Well, the longer you leave it running, the more you're going to pay, of course. But if you decide to stop an instance, then AWS will not bill you for it. The instance state is kept because you have a volume attached to it, but at least you're not paying for it. So you can see right now while the instance is in a stopping state, and if you try to refresh the webserver page, it's not going to work because, well, you don't have the server running anymore. So you can see it gets to some like infinite loading experience. So your instance is now stopped, and if you wanted to, actually, you could get rid of it. And in the Cloud, it's very common to start instances and then get rid of them very quickly just to try it out because this is the Cloud and we can do whatever we want. So, you can go to instance state, and then terminate instance. If you do so, you're going to get a warning message and don't click on terminate because you want to keep this instance with you for now. But this is how you would get rid of it. So you cancel this, but what you're going to do now is you're going to start your instance again. So you go to instance state and then start instance. And now as you can see the state is pending, so it is getting started, and you just wait for it to be started in the green state and I will tell you something very interesting.

## Stopping and Restarting 🔽🔄

Okay, so your instance is now running. And if you go to the webserver page and stop the refresh and try again to refresh, it still goes into an infinite loop. You may say, well, the server is running, so why is it not displaying the message now? So the public IP actually has changed, so if you stop an instance and then you start it later on, then AWS will maybe change its public IPv4. So therefore, you need to copy the new IPv4, make sure to use HTTP, and voila, you have access back to your EC2 instance. But one thing that has not changed is the private IPv4, the private IP will always stay the same, but the public IPv4 may change.

## Day-10 Finished 🎉

Today you have learned about how to Launch Your First EC2 Instance and Manage it.