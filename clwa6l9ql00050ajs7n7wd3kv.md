---
title: "🚀 AWS CCP - Day-25 - Enhance Scalability and Security with AWS Elastic Load Balancing 🚀"
seoTitle: "Enhance Scalability and Security with AWS Elastic Load Balancing"
seoDescription: "Discover how AWS Elastic Load Balancing can transform your cloud infrastructure with scalable, reliable, and secure traffic management."
datePublished: Fri May 17 2024 04:30:12 GMT+0000 (Coordinated Universal Time)
cuid: clwa6l9ql00050ajs7n7wd3kv
slug: aws-ccp-day-25-enhance-scalability-and-security-with-aws-elastic-load-balancing
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1715888150120/7a099248-78a1-4a76-8652-70016b6f6262.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to Elastic Load Balancing 🌟

Let's see, the first service that will allow you to be more elastic on AWS is called elastic load balancing. A load balancer is a server that will forward the internet traffic down to multiple servers downstream. For you, these will be EC2 instances. They're also called the backend EC2 instances. So elastic load balancing is something that is managed by AWS.

## Load Balancer Configuration ⚙️

So you have a load balancer and this is what you will be publicly exposing for your users. And behind that load balancer, you will have multiple EC2 instances, maybe three, in that case. And then you have your first user talking to your load balancer, And the load balancer will be directing the traffic to one of these EC2 instances. And the EC2 instance will reply back with something and the user will get the response. But now if a second user comes in, then they will get the reply from another EC2 instance. And if a third user comes in, as you can expect, it will be replying from another EC2 instance. And so the load balancer, the more users you have, the more it will balance the load across multiple EC2 instances and that will allow you to scale better your backend.

## Benefits of Using a Load Balancer 💡

So why would you use one? I think it's clear. You can spread the load across multiple downstream instances. You can expose a single point of access, DNS host name, for your application. You can seamlessly handle the failures of downstream instances. So you do regular health checks on them and if one of them is failing, then the load balancer will not direct traffic to that instance. So you can hide the failure of an instance using a load balancer. You can also provide SSL termination, so HTTPS for your websites very easily. And you are able to use a load balancer across multiple availability zones which was making your application highly available.

## Management of Elastic Load Balancers 🛠️

The ELB is a managed load balancer, so you don't need to be provisioning servers. AWS will do it for you and AWS will guarantee that it will be working. AWS will take care of all the upgrades, maintenance, and high availability of that elastic load balancer. And the only thing you have to do is to configure a few things for the behavior of that load balancer. It's obviously less expensive if you want to set up your own load balancer on EC2. It is definitely possible, but in the end, there will be a lot more effort on your end for maintenance, integration, maintaining and taking care of the operating system, upgrades, et cetera, et cetera.

# Types of Load Balancers 🧩

So there are four kinds of load balancers offered by AWS and you need to know the differences between them. So the first one is the application load balancer, which is for HTTP or HTTPS-only traffic which is called a Layer 7 type of load balancer because it's HTTP and HTTPS. Next, you have the network load balancer. It's ultra high performance. So look for that keyword. It allows for TCP and UDP actually. And it's Layer 4. So it's Layer 4 because it's lower level, so TCP and UDP. Then you have the gateway load balancer. It's Layer 3. And then finally, you have the classic load balancer but it has been retired in 2023, so it's not going to appear at the exam anymore I feel. But if you want to know, it was a Layer 4 and Layer 7 type of load balancer of older generation. And it's been replaced by the ALB, the application balancer and the NLB, the network load balancer.

## Differences Between Load Balancers 🔍

| Feature/Characteristic | Application Load Balancer (ALB) | Network Load Balancer (NLB) | Gateway Load Balancer (GWLB) | Classic Load Balancer (CLB) |
| --- | --- | --- | --- | --- |
| **Layer** | 7 (HTTP/HTTPS) | 4 (TCP/UDP) | 3 (GENEVE protocol) | 4 & 7 (Retired in 2023) |
| **Protocols Supported** | HTTP, HTTPS, gRPC | TCP, UDP | IP packets (GENEVE) | HTTP, HTTPS, TCP, SSL |
| **Performance** | High | Ultra High (Millions of requests per second) | Moderate | Moderate |
| **Static IP/URL** | Static URL | Static IP (Elastic IP) | Not typically used for static IP/URL | Both (depending on configuration) |
| **Use Case** | HTTP routing features, HTTP/HTTPS traffic | High-performance network traffic, static IP | Routing traffic to firewalls, intrusion detection, deep packet inspection | General purpose (legacy) |
| **Traffic Handling** | Routes traffic to downstream EC2 instances | Routes traffic to downstream EC2 instances | Routes traffic to virtual appliances for security analysis | Routes traffic to downstream EC2 instances |
| **SSL Termination** | Yes | No | No | Yes |
| **Health Checks** | Yes | Yes | Yes | Yes |
| **Availability Zones** | Multi-AZ support | Multi-AZ support | Multi-AZ support | Multi-AZ support |
| **Managed by AWS** | Yes | Yes | Yes | Yes |
| **Use Case Keywords** | HTTP, HTTPS, gRPC, static DNS | TCP, UDP, static IP, high performance | Firewall, intrusion detection, deep packet inspection | Legacy, general purpose |

So if you have a look at the differences between the ALB, the NLB, and the gateway load balancer, also GWLB, then what you'll need to look at for the exam are these kinds of keywords. So if you see HTTP, HTTPS or gRPC protocol, it means it's Layer 7 and it's the ALB. Also, anytime you need HTTP routing features, this will be requested. For a static DNS as well, this would be very helpful if you want to have a static URL. So the architecture is very simple. The users access your load balancers on one of the protocols I just mentioned and then the load balancer routes traffic to the downstream EC2 instances. For example, if you've chosen the targets to be EC2 instances.

### Network Load Balancer 🌐

For the network load balancer, it is Layer 4. So TCP and UDP protocol, and it's very high performance. We're talking millions of requests per second. It gives you a static IP this time, so not a static URL, but a static IP through the use of elastic IP which are IPs that you own that you can move around. So this NLB gives you a static IP and the architecture is the exact same as the ALB. The traffic is being sent to the NLB on the TCP and UDP protocol, and then sent, forwarded to downstream targets. For example, EC2 instances.

### Gateway Load Balancer 🛡️

Now, the gateway load balancer is using the GENEVE protocol on the IP packets themselves. So it's Layer 3. And the use case you need to look at for the exam is to route traffic to firewalls that you manage on EC2 instances, so that you can do, for example, classic firewall or intrusion detection or deep packet inspection. And the architecture, it is a little bit more complicated. So the gateway load balancer doesn't balance the load to your application. It actually balances the load of the traffic to the virtual appliances that you run on EC2 instances so that you can analyze the traffic or perform firewall operations. That's why it's called third-party security virtual appliances. And they can be, many of them address. And so therefore, the traffic, when it goes to the gateway load balancer, first sends the traffic to these EC2 instances that will analyze the traffic. The traffic will be sent back afterwards to the gateway load balancer and then forwarded back to the applications. So the gateway load balancer here is in the middle to allow you to inspect the IP packets themselves and to perform firewall features or intrusion detection or deep packet inspection.

# Day-25 Finished 🎉
Today you have learned about Elastic Load Balancing in AWS. 🌐🛡️🚀🌟