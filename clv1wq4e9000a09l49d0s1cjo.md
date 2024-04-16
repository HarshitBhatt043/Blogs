---
title: "AWS CCP - Day-02 - Different Types of Cloud Computing and AWS Cloud Overview"
seoTitle: "AWS CCP Day-02: Different Types of Cloud Computing and AWS Overview"
seoDescription: "Understand different types of Cloud Computing and glance on AWS Cloud. Get ready for your AWS Cloud Practitioner certification."
datePublished: Tue Apr 16 2024 04:52:11 GMT+0000 (Coordinated Universal Time)
cuid: clv1wq4e9000a09l49d0s1cjo
slug: aws-ccp-day-02-different-types-of-cloud-computing-and-aws-cloud-overview
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713184094248/f4785f40-2b24-4b13-a936-15e869bf3aea.jpeg
tags: cloud, aws, cloud-computing, devops, devops-articles, devops-journey

---

## There are different types of Cloud Computing, and it is important for us to be able to recognize them. 💻🌐

### Infrastructure as a Service (IaaS) 
The first one is called Infrastructure as a Service or IaaS. This is to provide the building blocks for cloud IT. With this IaaS, we're going to provide networking, computers and data storage space in its raw form. And using these building blocks deals building Legos, we're going to be given a very high level of flexibility, and we can easily understand how we can migrate from traditional on-premises IT to the cloud. 🏗️🔌

### Platform as a Service (PaaS) 
Then we're going to get Platform as a Service. In this, we're going to remove the need for your organization to manage the underlying infrastructure. And you can just focus on the deployment and management of your applications. 🛠️🚀

### Software as a Service (SaaS) 
And then one step even further, is Software as a Service or SaaS. This is a completed product that is going to be run and managed by the service provider. 📦🎉

### Comparison of Services 
So if you want to compare all these things, well, let's take an example. On-premise is you're going to manage everything. So your applications, your data, your runtime, your middleware, the operating system, virtualization, servers, storage and networking. And that's a lot. With IaaS, Infrastructure as a Service, we're going to manage the application, the data, the runtime, the middleware, and the OS, but all the virtualization, servers, storage and networking, are going to be managed by others. And in our case, AWS. With Platform as a Service, we manage even less. So everything from the runtime to the networking is managed by AWS. And the only thing we care about when we use a Platform as a Service is our application and our data. And finally, well if you're using Software as a Service, everything is going to be managed by AWS. 🔄💰

### Examples of Service Providers 
So how does it translate? Well, with IaaS, we can use Amazon EC2 on AWS. We have other services such as Google Cloud, Azure, Rackspace, Digital Ocean, and Linode, which will provide us Cloud Computing Infrastructure as a Service. Platform as a Service also exists on AWS with Elastic Beanstalk and we'll see all these services in future. And outside of AWS, we have Heroku, Google App Engine and Windows Azure. For Software as a Service, we'll also have this on AWS, that represents many services of AWS for example, recognition when we want to do some Machine Learning, but we've been using it as well in the real world with Google Apps such as Gmail, or Dropbox or zoom for your meetings. 🖥️📱

### Pricing Models 
So the clouds have different flavors. But one thing is common is that the pricing is very different from what you know. AWS has three pricing fundamentals and it will follow the pay-as-you-go pricing model. So for the compute, and that represents various services, where you're going to pay for the exact compute time. For the storage, we're going to pay for the exact amount of data stored in the cloud. And for the networking, we're going to only pay when the data leaves the cloud. Any data that goes into the cloud is free. And this solves the expensive issue of traditional IT. Because now we only pay exactly what we need and so we have huge cost savings ahead of us. 💸💡

## AWS History and Market Position 
Now let's look at the history of the AWS cloud. So it was launched in 2002 internally at amazon.com. Because they realized that the IT departments could be externalized. So their Amazon infrastructure was one of their core strength and they said, "you know what maybe we can do IT for someone else, for other people." So they launched their first offering publicly which was SQS in 2004. In 2006, they expanded their offering and they relaunched with the availability of SQS, S3, and EC2.Then they expanded and said, "you know what? We don't have to be just in America. We could be in Europe." And then fast forward to today, we have so many applications that used to run or are still running on AWS, such as Dropbox, Netflix, Airbnb, or even the NASA. 🚀📈

Now, let's look at where AWS is today. If we look at the Gartner magic quadrants, which sort of ranks the cloud providers, as we can see AWS is on the top right corner, which is a leader. It's able to execute really well. And it has a really great completeness of vision. It is followed closely by Microsoft and Google. But still in 2023, AWS had $90.8 billion in annual revenue, which is huge and accounted for 32% of the market in 2023. With Microsoft being second with 22%. So by learning AWS you are learning a tool that is widely used. It is a pioneer and leader of the AWS Cloud Markets for the thirteenth consecutive year. And it has over 1 million active users. 🏆💼

### Applications and Use Cases of AWS 
So what can you build on AWS? Well, pretty much everything. AWS will enable you to build sophisticated and scalable applications and they are applicable to diverse set of industries. Every company has a use case for the cloud. So Netflix, McDonald's, 21st century Fox, Activision, they're all using the cloud. And use cases can include just transferring your enterprise IT or using the cloud as a backup and storage, or doing some big data analytics. You can also host a website or create a backend for your mobile and your social applications. Or you could have your entire gaming servers running on the clouds. The applications are endless. 🎮📊

### Overview of AWS Global Infrastructure 
Now AWS is global. And this is where we are going to learn a bit more specifics about how it works. So we have AWS regions, we have availability zones, data centers, edge locations, and points of presence. And all of these can be represented on the map right [here](https://aws.amazon.com/about-aws/global-infrastructure/). So let's go on this website to have a quick look at it. So this is a cool map, because on this website you can see how AWS is global.We can see that AWS has multiple regions and they're in orange and they're all around the world. For example, Paris, in Spain, in Ohio, in Sao Paulo, Cape Town, Mumbai, and everywhere else. So AWS truly is a global service. 🌍🗺️

#### Understanding AWS Regions and Availability Zones 
The first important concept in AWS are regions. So regions are all around the world and we saw it on the map from before the regions have a name, it could be us-east-1, eu-west-3, and we can see the mapping of the name of the region to their code on the console that we'll see in a minute. Now a region, what is it? It's truly, well, it's going to be a cluster of data centers. So many different data centers. Look at it for example, Ohio or Singapore or Sydney or Tokyo. When we use AWS services, most services are going to be linked and scoped to a specific region. That means that if we use a service in one region and we try to use it in another region, it will be like a new time of using the service. 🌐🔍

Now, a question that may come up in the exam is how do you choose an AWS region? So say you're launching a new application. Where should you do it? Should you do it in America, in Europe in South America, or in Australia? Well, the answer is, of course it depends. But let's look at some factors that may impact your choice of a AWS region. The first one is compliance. So sometimes governments want the data to be local to the country you're deploying the application in. For example, France, data in France may have to stay in France and therefore you should launch your application in the French region. Then, there is also a concept of latency. So if most of your users are going to be in America, it makes a lot of sense to deploy your application in America, close to your users, because they will have a reduced latency. If you deploy your application in Australia and your users are in America, they will have a lot of lag at using your application. Then, also not all regions have all services. Okay? Some regions do not have services. And so obviously if you're leveraging a service with your application, you need to make sure that the region you're deploying into is available and does have that service. And finally, pricing. So, pricing does vary from region to region and you need to consult the applicant, the services, pricing, to see what the differences are between the regions. But this could be obviously a factor that could impact your deployment of an application into a specific region. 💼💡

Now, availability zones are what actually are going into the region. So each region will have many availability zones. Usually three, the minimum is three, and the max is six. But, really the usual is three. So, let's take the Sydney region as an example. The senior region code is ap-southeast-2. So, we can have two, have three availability zones in Sydney, ap-southeast-2a, ap-southeast-2b, and ap-southeast-2c. Now, each of these availability zones are going to be one or more, just create data centers that will have redundant power, networking, and connectivity. That means that in southeast-2a, I can have two data centers maybe, as well two in 2b and two in 2c. But it could be one, it could be three, it could be four. We don't really know. AWS doesn't tell us that. But, what we know is that these availability zones are separate from each other so that they will be isolated from disasters. So, if something happens to ap-southeast-2a, we know that it is designed not to cascade into ap-southeast-2b, or ap-southeast-2c. So they're really isolated from disasters. And then these data centers, these availability zones, they are connected with high bandwidth, ultra low latency networking and therefore altogether being linked together, it will form a region. Okay. 🏢🔗

#### Points of Presence 
Next to, the only thing we need to know about AWS for the global infrastructure is the points of presence or edge locations. We will see them in details in future, but you should know that AWS has more than 400 points of presence in 90 cities across 40 countries. And this will be very helpful when we deliver content to the end users with the lowest latency possible.Finally, to know if a service is available in your region, there is a region table you should check out right [here](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/).

## Day-02 Finished

So that's it, we have finished Different Types of Cloud Computing and AWS Cloud Overview. 🎉👍
