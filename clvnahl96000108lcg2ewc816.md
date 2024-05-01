---
title: "🔗 AWS CCP - Day-13- SSH & EC2 Instance Connect for Windows & Linux/Mac 🔌"
seoTitle: "Mastering SSH & EC2 Instance Connect: Windows & Linux/Mac"
seoDescription: "Learn how to effortlessly connect to your AWS EC2 instances from Windows & Linux/Mac! From PuTTY installation to troubleshooting permission issues."
datePublished: Wed May 01 2024 04:00:37 GMT+0000 (Coordinated Universal Time)
cuid: clvnahl96000108lcg2ewc816
slug: aws-ccp-day-13-ssh-ec2-instance-connect-for-windows-linuxmac
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714309489555/69ea1515-84ad-469d-886c-c4444eb18cc6.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Connecting to Servers in the Cloud 🌐

You're getting to one of the trickier bits of running in the Cloud, which is how do you connect inside of your servers to perform some maintenance or action.

# SSH on Different Operating Systems 💻

The SSH is a command-line interface utility that can be used on Mac or Linux as well as Windows over version 10. Then if you have Windows less than version 10, you can use something called putty. Putty will exceed the exact same thing as SSH. So when I say you should SSH, if you're on Windows, you can use putty. And putty is valid for any version of Windows.

We have our EC2 machine, and we launched Amazon Linux 2 on it, and our machine has a public IP. Now we want to access that machine. And so for this, I don't know if you remember but we have a security group and on it we allowed the Port 22 of SSH. So what's going to happen is at your computer, you access over the web. Through that Port 22, it will access the EC2 machine. Basically, your command-line interface is going to be just as if you were inside that machine. So let's get started.

## Preparing the PEM file 📁

Okay. So we are going to SSH into our instance. So remember that PEM file you've downloaded called EC2 Tutorial.pem? Please make sure to remove the space in it if you have a space, even if you have a PPK file. Please rename it and remove the space from it. So EC2Tutorial.pem is removed for you. And then, you go ahead and place it in a directory you like. So for you, take your file and paste it, and place it in a folder called aws. So this is the first step to making sure you are ready.

## Accessing the EC2 Instance 🛠️

So next, what you're going to do is go to your EC2 instance overview page and find your first instance. So you're going to open a remote terminal into it. And for this, you need to get the public IPv4 address, so you can copy this, and you will use it later. The other thing you need to do is to look at the security of your instance. So again, if you did everything right, then your security groups have this rule in it called Port 22 which is the SSH port from anywhere by 0.0.0.0/0. So if you have that rule, then you're good to go. If not, please click on the security group and add the missing rule.

# Linux/Mac SSH Connection 🐧

## Initiating the SSH Connection ⚡

Next, you need to try to do an SSH. So first of all, `ssh ec2-user@` and then the IP you have. So the reason we do ssh ec2-user is because the Amazon Linux 2 AMI has one user already set up for us and that user is named ec2-user. Then we have at, to say that we want to access that user on the specific server. And then, we have the IP right here. This is the public IP of our EC2 instance. So you do SSH and then you're going to get a too many authentication failure. That means that you don't authenticate into your EC2 instances. Well, that makes sense because we haven't specified the key that we downloaded from before yet.

### Specifying the PEM File and Permissions 🔑

So for this, you need to reference the file you just downloaded called EC2Tutorial.pem into your command. Make sure your terminal is exactly where your file is. So if you do `ls` right here to list the files in your folder. It says EC2Tutorial.pem that's because you placed your command line in the correct directory on your computer.

## Logging into the EC2 Instance 🖥️

The SSH command, you do `ssh -i` then you specify the EC2Tutorial.pem file and then, `ec2-user@` and you reference the public IP of your instance. Press enter, and now you get another kind of error which is saying that you have an unprotected key file and you need to change the permissions for it. So for that reason, you'll have to enter another command and that command is `chmod`. So `chmod 0400`, and then you pass in the file itself so `EC2Tutorial.pem`. So you clear your screen and then you're going to try the exact same command as before. So you press enter and you are logged into your machine. So you may have seen a screen where they prompt you for yes/no to trust the instance as well, just enter yes if you do get that screen. Now you have done the SSH into your instance and now it says ec2-use at this IP, which means that now all the commands you issue are going to be issued directly from the Amazon Linux 2 AMI EC2 instance that you've just launched from before.

## Using Commands on the EC2 Instance 🛠️

So let's try a few commands. For example, if you do `whoami` then it says `ec2-user` or you can `ping google.com` and you'll see that google.com is responding to your pings. So you can launch some commands directly from the Amazon Linux 2 AMI, and if you press `control C`, it will stop that command.

### Exiting the EC2 Instance 🚪

Now to exit the instance itself, you can either type `exit` or you do `control G` and then you will close the connection into the EC2 instance. And if you ever want to get back into it remember this command, `ssh -I EC2Tutorial.pem` if you are in the correct directory. Please make sure to do so. Also, remember that if you stop and then start your instance then the public IP can change. So make sure to change that part as well.

# Windows 7 SSH with PuTTY 🪟

## Installing PuTTY 🧩

So you are going to SSH into your EC2 Instance and you're running on Windows. And for this, I assume that you have Windows 7, or Windows 8, or an older version Window. If you have Windows 10, there is an alternative. So let's try for, even if you're on Windows 10 you can do this technique. So for this, you would go and download PuTTY. So PuTTY is a free SSH client for Windows. So download PuTTY. And then you will choose, for example, the 64 bits installer, the first one. Then you go ahead. You perform the install of PuTTY. So next, next, yes. And yes, you want to install PuTTY. Perfect. So PuTTY is installed. And you have to install PuTTY.

### Generating PPK File with PuTTYgen 🔑

So, you have two things here on PuTTY. You have the PuTTY app, as well as PuTTYgen. So let's first open PuTTYgen. And in case you did not download your file in the PPK format, you can actually generate the PPK format directly from here. So, you need to go ahead and load your file. So you click on load, and then find where your file is. It says, okay, you have successfully imported this. And then you can save it as a private key. So click on save private key. And said you want to have a pathway, you say, if you don't want to have a path, you say yes. And then you save it on your desktop. So EC2tutorial.PPK Now your file is saved and you have successfully converted a PEM file into the PPK format. If you have done this already, then you're good to go.

## Setting Up PuTTY 🚀

Next, you need to set up PuTTY to access your EC2 Instance. So, this time you open the PuTTY app, and here you have to enter a host name or an IP address of where you are trying to connect. So this you know it's My First Instance. You copy the public IPv4 address. You paste it. And it's SSH. You're going to save this under EC2 Instance. And then you click on save, but we're not done just yet. We need to specify the key itself. So let's specify the key in here. So, you have it saved under EC2 Instance. You double click. So as you can see, you have to accept this. So if you accept because you trust the host, you say, yes, accept. But you still have the login as prompt and it will not work.

### Configuring PuTTY for Authentication 🔐

So if you do, for example, EC2 user, it says okay, I cannot authenticate right now. So for this, you go back into PuTTY, and you're going to fix things. So click on EC2 Instance and load this profile. The first thing you're going to add is in the host name. You have EC2 minus user at the IP. So the IP is where you access your server, and the EC2 user is a user already created for us on Amazon Linux 2. So you can click on save again. So you're done in here. This will be saved. And then for the key, you need to go into the SSH. So you just click on Auth, and then you need to find a private key file for authentication. Click on browse, go to your desktop. And then you find the EC2 tutorial, that PPK file, you have just generated using Puttygen. Or, if you had downloaded it already from the AWS console, that works as well. So this file is good.

## Connecting to EC2 Instance 🌐

Don't click on open just yet, go back to session, and then click on save, to save this profile. This way you don't have to redo all these steps all at once, over again. So click on open. And now it says, you're authenticating using the EC2 user. And you have this file you just opened. And so now you are into your Amazon Linux 2 AMI. So you have successfully performed the SSH using PuTTY. Okay. And now what you can do, who am I? And you find that you are EC2 user. Or ping google.com and start running some commands. So to stop this, just do control C, and it will stop the command. And then if you want to just exit this, you can just close this, exit this session, and you're good to go. And let's check if you go back into PuTTY. So click back on PuTTY, and you load the EC2 Instance. Hopefully all you're seeing there is save. So as you can see, the top settings are saved, and your SSH Auth also has saved. And therefore, if you click on open, then yes, you have access directly into your EC2 Instance. So you've successfully performed SSH on this Windows 7 or Windows 8, through PuTTY.

# Windows 10 SSH with PEM File 🪟

## Navigating to PEM File Directory 📂

The first thing you have to do is to be in the directory of where your pem file is. So right now, you do `ls` and you can see your EC2Tutorial.pem file which is the one you downloaded, as well as the ppk file but this is not relevant, if you don't have it, it is fine, this is only if you want to use PuTTY. The only file that is of relevance for you is the EC2 tutorial.pem file.

## Configuring Security Group and Running SSH Command 🔒

Okay, so you need to make sure that on the security group of course you have the port 22 open for SSH, which you do and next you need to enter your SSH command. So for this, it is very similar to the one we have on Linux, so you do `ssh -I` then you pass in the name of the tutorial file. So you did to get this, you did EC2 and then you press tab and you get auto suggested the EC2Tutorial.pem file. You press tab again, you can switch between ppk and pem. Okay so, by pressing tab, you get the autocomplete of this, so you do `ssh -I` or you can just type this, `EC2Tutorial.pem` and then when to type `EC2-user@` and at, well, the public IP of your EC2 instance which is right here, so you copy and paste it. So now this command is saying, please enter this IP using this user, the EC2 user which is the one we have because we use Amazon next to using this key right here, so let's press enter. And it says, well, the authenticity of the host cannot be trusted, do you want to continue? You say, yes and you are in the machine.

### Dealing with Permission Issues ⚠️

So sometimes you will get permission issues. So sometimes the permissions will not be happy and I will tell you how to fix them. So in case you get a permission issue when running ssh command, what you have to do is to find your keys. You right-click on your pem file, you do properties, you go to the security tab and this is where we're going to change permissions. To do so, we're going to do advanced and the first thing you need to make sure of is that the owner of this file is yourself. So it's working for you, but you can just click on change and then for object types, you can find yourself, locations make sure it's on your computer and then type the object name. So it would be for you, Admin but you're already an owner so just type your name and then you can be an owner of this file. The owner is also indicated in here, in your app permission entries. The second thing you have to do is just remove these entities, so system and administrator don't need to have access to it and we need to disable inheritance. So first let's disable inheritance, for this, we're going to remove all inherited permissions from this object. And then in here, you just select the principal so yourself, you just go enter YourName. So as you can see, you did YourName in here, check names and this entered your principal name and you are going to give yourself full control over this, press okay. So now the owner is yourself and the principal that owns that file is yourself as well. You do okay and okay, so if you right-click again on this file and do properties under security now, you only see yourself, Admin with full permission. And then if you have that and you do this command again for sure you will not have any permission issues and you will not be prompted with a yes, no question ever again.

# Introduction to EC2 Instance Connect 💻

I want to tell you an alternative to SSH that I found a lot easier which is the EC2 Instance Connect. So for this, you click on My First Instance and then you click on the top, it says connect. You have multiple options including the SSH client we saw from before. But one option I wanna show you is the EC2 Instance Connect. So this allows us to do a browser-based SSH session into our EC2 Instance.

## Connecting to EC2 Instance 🌐

For this, you verify the public IP address, which is good. The username is provided by default, which is EC2 user because it gets guessed by AWS that you are using Amazon and X2 and therefore EC2 User is the right username, but if you wanted to, you could override it, but it doesn't work unless you enter EC2 users. So you'll leave it as is for now, and then, as you see there's no SSH key option, because, well, when you connect to it, it's going to upload for you a temporary SSH key and establish a connection this way. So with this methodology, you don't even need to manage SSH keys which I found lovely.

## Browser-Based SSH Session 🌐

So you click on Connect and it's going to open a new tab. And very quickly you are into your Amazon Linux 2 AMI and you can start running some commands such as whoami or ping google.com. And as you can see, everything is working. So the cool thing about it is that, well, your session is in the browser instead of using a different command-line interface such as terminal and so on. And so you do ping google.com or do any kind of commands you want really on it without using the SSH utility beforehand.

# Day-13 Finished 🎉

Today you have learned about how to SSH & Use EC2 Instance Connect.
