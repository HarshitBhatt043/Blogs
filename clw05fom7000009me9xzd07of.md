---
title: "🌟 AWS CCP - Day-20 - Streamlining Deployment with AWS EC2 Image Builder 🌟"
seoTitle: "Streamlining Deployment with EC2 Image Builder"
seoDescription: "Discover how EC2 Image Builder automates AMI creation, maintenance, and testing, ensuring reliability and efficiency in your deployment process."
datePublished: Fri May 10 2024 04:00:10 GMT+0000 (Coordinated Universal Time)
cuid: clw05fom7000009me9xzd07of
slug: aws-ccp-day-20-streamlining-deployment-with-aws-ec2-image-builder
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715287323233/b1f0465d-4bdf-4fd2-aafc-5b0d02d41762.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction 🚀

So let's talk about a new service that you might really like, and that does come up in your exam now. It's called EC2 Image Builder. It's used to automate the creation of virtual machines or container images. Concretely, what does that mean for you in the exam? That means you'll be able to automate the creation, maintenance, validation, and testing of AMIs for EC2 instances. 🤖

# Overview 🔄

| Process Stage        | Description                                                                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1. Initialization    | - EC2 Image Builder service initiates the process. <br> - Automatically creates a builder EC2 instance.                                                                    |
| 2. Customization     | - Builder EC2 instance builds components and customizes software according to predefined specifications. <br> - Tasks may include installing software, updating system, configuring firewalls, and installing applications. |
| 3. AMI Creation      | - Once customization is completed, an Amazon Machine Image (AMI) is created from the builder EC2 instance.                                                                 |
| 4. Validation        | - EC2 Image Builder automatically creates a test EC2 instance from the generated AMI. <br> - Runs predefined tests to validate the functionality and security of the AMI. |
| 5. Test Customization| - Tests can be customized to check various aspects like functionality, security, and application performance.                                                               |
| 6. Test Execution    | - Tests are executed on the test EC2 instance.                                                                                                                              |
| 7. Test Result       | - Test results are collected to determine if the AMI meets the defined criteria.                                                                                           |
| 8. Distribution      | - Once the AMI passes validation, it can be distributed to multiple regions. <br> - Allows global availability of the application and workflow.                           |
| 9. Scheduling        | - EC2 Image Builder can be scheduled to run at specific intervals (e.g., weekly) or triggered manually. <br> - Offers flexibility based on package updates or predefined schedules. |

So you have the EC2 Image Builder service, and when it runs, it automatically creates an EC2 instance called a builder EC2 instance. That EC2 instance builds components and customizes the software. For example, it can install Java, update the CLI, update the software system, maybe install firewalls, or whatever you define to happen on that EC2 instance, maybe even install your application. Once this is done, an AMI is created out of that EC2 instance. 🔧

**Additional Information:**

* **Supported Platforms**: EC2 Image Builder supports various platforms, including Linux distributions (e.g., Amazon Linux, Ubuntu) and Windows Server.
    
* **Configuration Options**: Users can specify detailed configuration options during customization, such as selecting specific software packages, applying custom configurations, and defining security settings.
    
* **Test Scenarios**: Test scenarios can include checks for application functionality, security vulnerabilities, compliance with industry standards, and performance benchmarks.
    
* **Distribution Methods**: AMIs can be distributed to multiple regions using AWS services like AWS Resource Access Manager (RAM) or AWS Lambda functions for automated deployment.
    
* **Scheduling Flexibility**: EC2 Image Builder offers flexible scheduling options, allowing users to trigger builds based on events like package updates, system patches, or custom-defined schedules.
    
* **Cost Considerations**: Users should consider costs associated with EC2 instances, EBS volumes, data transfer, and any additional AWS services used in conjunction with EC2 Image Builder.
    
* **Integration with Other AWS Services**: EC2 Image Builder can integrate with AWS services such as AWS Systems Manager for managing EC2 instances, AWS Lambda for automated workflows, and AWS CloudFormation for infrastructure as code deployments.

# Automation Process 🛠️

But all of this is obviously automated. Then the image is created, but we want to validate it. So EC2 Image Builder will automatically create a test EC2 instance from that AMI and run a bunch of tests that you define in advance. And if you don't want to run a test, obviously you can just skip that test. But the test can be asking Is it working? Is it secure? Is my application running correctly? All these kinds of things. And then once the AMI is tested, then the AMI is going to be distributed. 🤖

## Distribution and Management 🌐

So while EC2 Image Builder is a regional service, it's possible for you to take that AMI and distribute it to multiple regions, therefore allowing your application and your workflow to be truly global. Next, EC2 Image Builder can be run on a schedule, so you can define a weekly schedule or you can say it can run whenever packages are updated, or you can run it manually. 📦

## Cost and Conclusion 💰

And it's a free service, so you're only going to pay for the underlying resources. What does that mean? Well, that means that if you create an EC2 instance during this process, EC2 Image Builder will create these EC2 instances. Then you're going to pay for these EC2 instances. And when the AMI is created and distributed, you're going to pay for the storage of that AMI wherever it has been created and wherever it has been distributed. 💸

# Day-20 Finished 🎉

Today you have learned about how to use AWS EC2 Image Builder. 🚀