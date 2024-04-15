---
title: "AWS CCP - Day-01 - Cloud and the Cloud Computing"
seoTitle: "AWS CCP Day-01: Cloud Computing Basics"
seoDescription: "Understand the core principles of cloud computing and AWS. Get ready for your AWS Cloud Practitioner certification."
datePublished: Mon Apr 15 2024 04:43:51 GMT+0000 (Coordinated Universal Time)
cuid: clv0gzkcn000008le636d0o6u
slug: aws-ccp-day-01-cloud-and-the-cloud-computing
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713155721255/3870fbc2-2c6c-4c80-ab36-25f2c9302bdc.jpeg
tags: cloud, aws, cloud-computing, devops, amazon-web-services, devops-articles, devops-journey, devopscommunity

---

## Introduction to Website Functionality 🌐

So let's go back to the very basics. How do websites work? Well we have a server hosted somewhere, and we, as a web browser, want to get access to that server to visualize a website. What we are going to do as a client is use a network. A network between ourselves and the server, and the client will find the network and will use the network to route the packets, the data into the server, then the server will reply to us, and we will get the response, and we can view a website.

## Understanding the Basics 💡

Now for the clients to find the server and the server to find the clients, you need to have IP addresses. So clients have IP addresses and a server also have an IP address. And so the idea is that when you use an IP address, you can send a request to wherever you want to the server you want, and the server can know how to find you back. This is very similar to when you are writing some letters to your friend. For example, you would write a letter, and that would be your data, and you would be the client, then when you send the letter you put it in your mailbox, and then the network will be the network of the post office, then the post office will use network and the address you put on the letter to route your letter to the destination, which is, in this case, the server, and then if your correspondent wants to reply you back, they can use the address you put on the back of the envelope to write you back, and again, use the same network to get the letter back to you. So servers are just like the network of your mail. Hopefully that's a good analogy.

### Server Components 🖥️

So what is in a server? Well a server is going to contain a CPU, and a CPU is a little piece that will be doing some computations, it will be very helpful to do some calculations and find results, and then, your server also needs RAM, or memory. This is going to be very, very fast memory, which will allow us to store information and retrieve it very quickly. So when we have a CPU and a memory bar, what do we get? Well we get a brain. Think of your brain. When you are thinking, you are actually making computations, very complicated ones, but they are computations, but then you need to retain some information, and again, we have memories and these memories are in our brain, so if we think of the CPU and the RAM together, they sort of look like a brain. Now we also need to have some more long-term storage of data. Obviously it's still in our brain as humans, but in computers, we have included some special storage to store data, for example, files, and then if we want to store the data in a more structured way, we're going to use a database, and a database is going to be data formatted in a way that we can easily search it and query it. Finally in the server, we're also going to have some networking aspect. So there's going to be the routers, switch, DNS servers, and don't worry, all these terms, we'll be seeing them later on. So in the server, we an aspect of compute, memory, storage, maybe your server sometimes is a database, and we have a networking aspect. All these things are gonna super important going forward because the cloud is going to be giving these things for us on demand.

### Traditional IT Infrastructure 🏢

So if we just want to define a little bit of IT terminology before we get started, the network is a bunch of cables, routers, and servers that are going to be connected with each other, and the router is a specific device that will forward the data packets between computer in the networks, and they will know where to send your packets on the internet, just like your post delivery service. Now when we have a packet and it arrives as a destination, there's a switch, and the switch will send the packet to the correct clients on your network.

So why do I introduce all these things? Well, let's go back to traditional IT. When people used to start websites or companies before, they used to do it in their home or their garage, and so they would literally go to the store, buy a server, and they put the server in their home. You may have seen TV shows, you may have read some documentation on the internet that describes on how Google was made. You know, Google was started in a garage. Now, as your website grows, you need to add more and more servers to serve that demand, and so your home starts to be filled with servers. So this bad right, but your company is getting bigger, you're generating some money, so you're going to move to your own office, and you decide to allocate a special room which is going to be called a data center. In a data center, you're going to have, again, your servers, and you're going to be able to scale them by adding and purchasing more and more servers. Now this worked, and this worked for so many years, but there are a few problems with this approach.

### Challenges of Traditional IT Infrastructure ⛓️

Number one is that when you have a data center or your own home, you're going to have to pay your rent, then you're going to have to add power supply, cooling, and maintenance because it does require some electricity to run your servers, it does require some cooling because the servers do get hot, and sometimes they break down, so you need someone to do the maintenance. On top of it, if you want to add or replace servers, it will take a lot of time because you have to order them, and then you have to hook them up in your center. Scaling is limited. If tomorrow you're getting 10 times bigger, you're going to need 10 times more servers, but you may not have the time or the space to do so. You also need to hire a team that is going to be there all the time, 24/7 to monitor the infrastructure in case something goes wrong. And what if there is a disaster, what if there is an earthquake, what if there's a power shutdown, or even a fire? That would be bad, right? So can we externalize all this? And the answer is yes, and that will be the cloud.

## Introduction to Cloud Computing ☁️

What is cloud computing? The definition is as such, cloud computing is the on-demand delivery of compute power, database storage, application, and other IT resources. The very important keyword here is on-demand, you get it when you need it. And then through a cloud service platform, you're going to get a pay-as-you-go pricing. That means that you're only going to pay for what you requested when you requested it and as you're using it, when you're done using it, you're not going to pay anymore. This is a big shift, right? Then this is cloud computing. So we can provision exactly the right type and size of computing resources you need. Do you need a big server? We have that for you. Do you want a small one? We have that too. Do you want 10? Yes. Do you want two tomorrow? Of course. The cloud really allows you to adapt to the type and size you need. Then you can access all these resources, not with 24-hour notice, not with two hours notice, but instantly, you don't need to order things in advance. When you want a server, and you'll see, you'll have it within seconds. Then the cloud will also give you a really nice interface so you can easily access your servers, your storage, databases, and a set of application services. Something about the cloud, but in specific AWS, which is Amazon Web Services owns and maintains the network-connected hardware required for these application services while you provision and use what you need via a web application. So with this interface, we'll make all these things a reality. Now, let's go back to our traditional IT. So we're changing. We have our office or our garage, but now instead of building our own data center we're going to use the cloud, and in the cloud, which is also a data center, is just not our data center, we're going to have servers one, two, three, as we need and as we go and we're just going to pay for exactly what we're using. So you have actually been using the cloud without even knowing it because it is omnipresent, but not necessarily visible. So if you use a web client such as Gmail, well, for example, it's an email cloud service and you're going to pay only for the emails you stored. You're not provisioning servers when you use Gmail, you just use it. Maybe you've stored some data on the cloud, maybe through Dropbox, Google Drive, Google Photos, iCloud, I don't know. But with Dropbox, for example, it's a cloud store service, you're going to put your files on Dropbox. And originally, fun fact, Dropbox was built on AWS. So we've been using a cloud storage service as well without knowing it. And Netflix, it's huge. It is built entirely on AWS and it provides you a cloud service, which is to get video on-demand. Now, obviously these cloud services are very different from AWS, but we'll learn what it goes behind these services and how AWS can help you build these kinds of cloud services. So let's go one step further. There are different kinds of clouds out there. The first one is called a private cloud and the provider is, could be Rackspace. This is cloud services used by a single organization, they're not exposed to the public, so you get your own private cloud, your own private data center, it's just managed by someone else. You still have complete control over it and you have more security for a sensitive application, which may need some specific business needs. Now the public cloud is more interesting. So three famous cloud providers that are public, are Microsoft Azure, Google Cloud, and Amazon Web Services that we'll be learning, obviously. So in this case, the cloud resources own and operated by a third party cloud service provider and they're delivered over the Internet and we'll see the six advantages of using cloud computing. So in this instance, that means that from AWS, we'll be able to request what we need when we want it. And then lastly, which is also important for the exam is the concept of a hybrid cloud. So with hybrid, we're actually getting the mix of private and public. We're going to keep some servers on premises and we'll extend some of the capabilities we need into the cloud. That means that we'll have a hybrid of our own infrastructure and the AWS cloud. We'll have control over sensitive assets in your private infrastructure, but we'll have the flexibility and the cost effectiveness of using the public cloud.

### Characteristics of Cloud Computing 🌩️

Now, five characteristics of cloud computing. The first one is that it's fully on-demand and self-service. Users, we will be able to provision resources and use them without having anyone from AWS intervene. Then we'll be having access to a broad network, the resources will be available over the network, and it can be accessed in diverse ways. It'll be multi-tenancy and we'll have resource pooling. So that means that not just us, but other customers from AWS can share the same infrastructure and applications while still having security and privacy. And then these multiple customers are getting serviced from the same physical resources. So here, me, you, and other customers, we're going to share this entire data center of the cloud. This gives us rapid elasticity and scalability. That means that we can automatically and quickly acquire and dispose resources when we need. And that means that we can quickly and easily scale based on demand. And that is a major advantage of the cloud. Finally, it's a measured service, so the usage is going to be measured and we're going to pay exactly for what we have used. This is a big shift from on premises.

### Advantages of Cloud Computing 🚀

Now, six advantages. We're going to trade capital expenses for operational expenses, so CAPEX or OPEX. That means that you don't own hardware, you're going to pay on-demand and that will reduce your total cost of ownership, your TCO, and your operational expense. That means that you don't buy the hardware in advance, you're just going to rent it from AWS. Then we're going to benefit from massive economies of scale. The price is because we are using AWS, not just us, but other customers and so many people are using it, then the prices will be reduced by AWS over time because AWS will be more efficient at running due to its large scale. We also need to stop guessing capacity. Before we had to plan and buy servers in advance and hope that it would meet the capacity, but now we can actually scale automatically based on the actual measured usage for our application. And because everything's on-demand, we have increased speed and agility. We can create, operate and do stuff right away, no blockers for us to be efficient. And finally, we have a huge cost that we don't need to have anymore, which is we can stop spending money running and maintaining data centers. And this allows a team of say five people to create a global application in minutes, thanks to leveraging this AWS global infrastructure that is going to be worldwide. Okay. So the problems we've just solved by using the cloud is that we're more flexible, we're more cost effective, we are more scalable because we can add resources as we need to go along, we're elastic, we can scale out and scale-in when needed, we also have high availability and fault tolerance because we don't really on the one data center, we rely on the fleet of data centers all around the world. We're more agile, we can rapidly develop, test and launch software applications, and although this make the cloud a really no brainer.

## Day-01 Finished

So that's it, just for an introduction of how the cloud is going to be effective.