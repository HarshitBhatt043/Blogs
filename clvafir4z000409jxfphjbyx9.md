---
title: "🖥️ AWS CCP - Day-06 - Mastering AWS Access From Console to CLI and SDKs 🖥️"
seoTitle: "Unlock AWS Access Mastery: From Console to CLI and SDKs"
seoDescription: "Dive into the CLI's command-line wizardry, flex your coding muscles with SDKs, and safeguard your digital treasure with security best practices."
datePublished: Mon Apr 22 2024 04:00:29 GMT+0000 (Coordinated Universal Time)
cuid: clvafir4z000409jxfphjbyx9
slug: aws-ccp-day-06-mastering-aws-access-from-console-to-cli-and-sdks
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713696533018/f17b7797-cd6d-4ac3-af4a-0346a31ce30e.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

## Management Console 💻

So you've seen how to access AWS using the Management console, which is the Web interface that you've done so far, but there are actually three different options to access AWS.

## CLI (Command Line Interface) 🖥️

Then there is the CLI, Command Line Interface, and this is something you will set up on your computer, and this is protected by access keys, and access keys are credentials that will allow you to access AWS from your terminal.

## SDK (Software Development Kit) 🛠️

Then, finally, there is the SDK, the AWS Software Development Kit, which is used whenever you want to call APIs from AWS from within your application code.

## Generating Access Keys 🔑

So how do you generate access keys? Well, you will do this through the Management console, and users are responsible for their own access keys, and access keys, from the user perspective, are secret, just like a password, so if you generate your own access keys do not share them with your colleagues, because they can generate their own access keys as well.

## Security Reminder 🚨

So again, remember, I want to make sure that you don't have any security issues, do not share your access keys, they are private to you.

## CLI Overview 📜

If you're new to the Cloud, and programming and so on, or IT, then you might not know what's a CLI. So CLI stands for Command Line Interface, and the AWS CLI is a tool that allows you to interact with the AWS services using commands from your command-line shell.

## CLI Usage 📋

So whenever you see some code where you type a command line, and then it returns a result, for example, `aws s3 cp`, and so on, this is what we call the CLI.

## Benefits of Using CLI 📊

Now with this CLI, you get direct access to the public APIs of your AWS services which is going to be very helpful. And, then, using the CLI you can develop scripts to manage your resources and automate some of your tasks.

## SDK Overview 🛠️

So what's the SDK now? SDK stands for Software Development Kit, and this is a set of library, this is going to be language-specific, so you're going to have an SDK for different programming languages, and similarly, it will allow you to access and manage your AWS services and APIs programmatically.

## SDK Usage 📦

But this time the SDK is not something that you use within your terminal, it is something that you embed within your application that you have to code. So your application will have the AWS SDK from within them.

## Supported Languages 💻

It supports many different programming languages, such as JavaScript, Python, PHP.NET, Ruby, Java, Go, Node.js, C++, all of those are programming languages.

## Specialized SDKs 📱

There's also the mobile SDK, if you're using Android or iOS, and the IoT, so Internet of Things device SDK in case you're using some thermal sensors or bike locks that are connected, all these kinds of things.

## Example: AWS CLI Built on AWS SDK 🏗️

So to give you an example of what you can build with the SDK, well, the AWS CLI that we're going to be using later is actually built on the AWS SDK for Python named Boto.

## Installing AWS Command Line 💻

### Windows 🖥️

Okay so you are going to install the aws command line on Windows. So for this you do aws CLI install windows on Google. And [this](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) will give you the list link and you want to install the aws-cli version 2 on Windows.This is the latest and so you'll be up to date. It doesn't change much versus version 1, it is just some improved performance and capability, but the API's exactly the same and there's also an improved installer.

#### Downloading the Installer 📥

So you're going to scroll down, in there and to Install on Windows where you can just simply install it using the MSI installer, so you click on this link to download the MSI installer.

#### Running the Installer ⚙️

Then you're going to run the installer so it should be very, very simple. Now the installer is starting, you click on Next. You accept the terms of the license, click on Next, Install and then you wait for the installer to be done.

#### Completing the Installation ✅

Yes, you want to allow whatever this is doing. Okay so the installer is now complete. You click on Finish and now you can go ahead and open a command line, so you'll do command line, Command Prompt here we go on Windows.

#### Verifying the Installation ✔️

And to be sure that it's fully installed you just type `aws --version` and press enter, and if you get a result like this: `aws-cli, a version that starts with a 2, then Python, Windows`, that means that your aws-cli is now properly installed on Windows and you're good to go.

#### Notes 📝

Finally just note that if you want to upgrade your aws-cli then you just need to re-download that MSI installer and just re-run the install and it will be automatically upgraded.

### MacOS 🍎

So let's install the AWS CLI on Mac and for this you're just going to go on Google and make sure to choose a [link](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) installing the AWS CLI version 2 on macOS. And then you're just going to follow the process, so you'll scroll down and see what they say.

#### Downloading and Installing 📥

Here is how to install it. So you can just download a pkg file and this will be a graphical installer. So you download the pkg file. Then you click on continue, continue, continue and you agree. Then you say, "Okay, install for all the users on this computer." Click on continue and then click on install, and this goes ahead and installs the CLI on mac. So you wait for everything to be done, the files are being written. Okay, the installation is now successful and you'll move the installer to trash.

#### Verifying Installation ✔️

And now to fill this out, you open a terminal on mac. So you just go ahead and type, for example, "terminal", and this will give you a terminal app. And then you just type `aws -- version` and if everything is going well, then it should give you back the version of the AWS executable.

### Linux 🐧

Okay, so let's proceed with installing the AWS CLI on Linux. So for this you just google it, and you will choose installing the AWS CLI Version 2 on Linux because this is the latest one, and you're going to scroll down.

#### Downloading the Installer 📥

And to install the CLI it goes installing. You just have to run these three commands. So the first one is to get a Zip file. So you copy this,
`curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"`
go into a terminal, and then you will paste it. And it will download the installer.

#### Unzipping the Installer 📦

The next thing you have to do is to unzip it. So you copy this command and paste it,
`unzip awscliv2.zip`
and this will unzip your installer. Great.

#### Running the Installer ⚙️

And the last thing is to run the installer as root, so you'll do sudo and then install.
`sudo ./aws/install`
This should prompt you for your password, which you'll enter right now, and then the installation will proceed.

#### Verifying Installation ✔️

Now it says you can run, `user/local/bin/AWS minus minus version,` or very simply, `AWS minus minus version` if your user local bin is in your path, and there you go. The AWS CLI has been installed as you can see.

## Day-06 Finished 🎉

So that's it, we have learned different types of AWS Access methods from console to CLI and SDKs 🎉👍
