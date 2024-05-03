---
title: "AWS CCP - Day-15- AWS EC2 Purchasing Options for Maximum Savings and Performance 💰"
seoTitle: "Maximize Your AWS EC2 Savings: Guide  to Purchasing Options"
seoDescription: "Explore the flexibility of on-demand instances, the discounts of reserved instances and savings plans, and the risk-reward balance of spot instances."
datePublished: Fri May 03 2024 04:00:18 GMT+0000 (Coordinated Universal Time)
cuid: clvq5cw0p000c08jy06n31pbr
slug: aws-ccp-day-15-aws-ec2-purchasing-options-for-maximum-savings-and-performance
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1714328675269/620fb8d5-f58f-4cf7-8421-0f25f3fcb9e9.jpeg
tags: cloud, aws, devops, devops-articles, devops-journey, devopscommunity

---

# Introduction to EC2 Instances Purchasing Options 🛒

You've been using so far, on-demand EC2 instances. They allow you to run instances on demand, that means they're good for short workloads, you get predictable pricing, and you're going to pay by the second. But if you have different kinds of workloads, you can optimize your discounts and your pricing by specifying it to AWS. For example, you can use reserved instances and you have one year or three years term, and they're meant for long workloads. So if you know you're going to run a database for a long time, then a reserved instance is great. And if you want to have a flexible instance type, so for example, you want to change the instance type over time, then convertible reserved instances are for you.

## On-Demand Instances 💡

Now let's look at EC2 on-demand. So you're going to pay for what you use. So that means that if you're using Linux or Windows, you're going to be getting a billing per second after the first minute, or for all the other operating systems, you're going to get a billing per hour. It has the highest cost but no upfront payments and no long-term commitments. That means it's definitely recommended for a short-term and uninterrupted workload where you cannot predict how the application will behave.

## Reserved Instances 📦

Now for reserved instances, and by the way, the numbers I show you can change over time, but it gives you an idea of what the numbers can be. So the reserved instances give you a 72% discounts compared to on-demand. And you reserve a specific instance attributes. For example, the instance type, the region, the tenancy, and the OS. You specify a reservation period one year or three years, to get even more discounts, and whether or not you wanna pay upfront, partially upfront, or not upfront. And all upfront of course gives you the maximum amount of discounts. In terms of the scope, do you want the scope to be into a specific region or a zone? That means reserve capacity in a specific AZ. And so you would use reserved instances for the steady-state usage applications, think for example, for a database. And you can buy or sell your reserved instances in a marketplace if you don't need them anymore. And there is a specific kind of reserved instances called the convertible reserved instance, which is allowing you to change the instance type, the instance family, the operating system, the scope and the tenancy. And because you have more flexibility, well you get a bit less discounts you get up to 66% discounts. So that's for reserved instances.

## EC2 Savings Plans 💡

And now you have the EC2 savings plans which is to allow you to get a discount based on long-term usage, which is the same 70% as reserved instances. But instead, you're going to say, "I want to spend $10 per hour for the next 1, 2, 3 years." And any usage beyond the savings plan is going to be billed at the on-demand price. So with savings plans, you're locked to a specific instance family and region. For example, you say, "I want to have M5 type of instance family in us-east-1." But you're flexible across the instance size. So you can have m5.xlarge, m5.2xlarge and so on. The OS, so you can switch between Linux and Windows and so on. And the tenancy, you can switch between host, dedicated and default.

## Spot Instances 🔍

Now, for spot instances, they have the most aggressive discounts, so up to 90% discounts compared to on-demand, but they are instances you can lose at any point of time because you define a max price you're willing to pay for your spot instances. And if the spot price goes over it, then you're going to lose it. So they're the most cost-efficient instances in AWS and they're going to be very helpful if you have a workload that is resilient to failure. So what could they be? Well, it could be batch jobs, data analysis, image processing, any kind of distributed workloads, or workloads that have a flexible start and end time. They are not suited for critical jobs or databases and the exam will test you on that.

## Dedicated Hosts and Instances 💼

Next we have dedicated hosts. So you get an actual physical server with EC2 instances capacity fully dedicated to your use case. And you want to have dedicated hosts in the use case of, you have compliance requirements or you need to use your existing server-bound software licenses that has billing based on a per-socket, per-core, per VM software licenses. This is in these kind of use cases that you need to access the physical server and get a dedicated host. So for dedicated hosts, you get on-demand, and you're gonna pay per second, or you can reserve them for one or three years. They're the most expensive option of AWS because you actually reserve a physical server. And so again, a use case is when you have a software that comes with a licensing model that is bring your own license. Or if you have a company that has strong regulatory or compliance needs. We also have dedicated instances, and there are instances that runs on hardware that's dedicated to you, which is different from the physical server. But you may share the hardware with other instances in the same accounts and you have no control over instance placements. So there's a difference between dedicated instances and hosts. At the exam, honestly, it doesn't trick you into one or the other, but remember that dedicated instances mean that you have your own instance on your own hardware, whereas dedicated host, you get access to the physical server itself and it gives you visibility into the lower level hardware.

## Capacity Reservations 🔒

Next, we have capacity reservations for EC2. So you can reserve on-demand instances in a specific AZ for any duration. And then you get access to that capacity whenever you need it. You have no time commitment so you can reserve capacity or cancel your reservation at any time. And no billing discounts. The only purpose is to reserve capacity. So if you want to get billing discounts, you need to combine it with regional reserved instances or your savings plan. And you're charged at the on-demand rates, whether or not you run instances. So that means that your reserved capacity, you're going to be billed for it, and you know for sure that if you want to launch instances they're going to be available, but if you don't launch them, you're still going to get charged. So they're very suitable for short-term uninterrupted workloads that need to be in a specific AZ.

# Summary and Price Comparison 📊

Understanding the different purchasing options for cloud services can be confusing, especially for beginners. Let's use a resort analogy to simplify things:

**On-Demand:** Think of this like booking a resort room whenever you want, but you pay the full price each time.

**Reserved:** If you like to plan ahead and know you'll be staying for a long time (like one, two, or three years), you can get a good discount by reserving your room in advance.

**Savings Plan:** With this option, you commit to spending a specific amount on your resort stay every month for a set period, usually 12 months. You can change the type of room you book over time.

**Spot Instances:** These are last-minute discounts offered by the resort when they have empty rooms. You can bid on these rooms for significant discounts, but you might get kicked out if someone else is willing to pay more.

**Dedicated Host:** If you want exclusive use of the entire resort building (your own hardware), this is the option for you.

**Capacity Reservation:** This option allows you to book a room in advance, even if you're not sure you'll use it. You pay the full price for the booking regardless.

## Comparison for an m4.large instance in the us-east-1 region:

| Pricing Option            | Price (per hour) | Description                                       | Terms of Commitment                           | Flexibility                                | Risk Factors                                        | Use Cases                                      | Additional Notes                                                                                   |
|---------------------------|-------------------|---------------------------------------------------|-----------------------------------------------|--------------------------------------------|-----------------------------------------------------|------------------------------------------------|--------------------------------------------------------------------------------------------------|
| On-Demand                 | $0.10             | Full price, pay as you go.                        | None                                          | Highly flexible, no upfront commitment      | None                                                | Short-term or unpredictable workloads         | -                                                                                                  |
| Spot Instances   | Up to 61% off    | Variable discount, may result in termination.    | None                                          | Highly flexible, but risk of termination   | Termination risk if bid price is surpassed           | Non-essential or batch processing tasks       | Prices fluctuate based on supply and demand.                                                        |
| Reserved Instances        | Variable          | Discounts for 1-year or 3-year commitments.      | 1-year, 3-year                               | Less flexible, long-term commitment        | Unused capacity for unutilized reservations          | Stable workloads with predictable usage       | Savings increase with longer commitment.                                                            |
| EC2 Savings Plan          | Variable          | Similar to Reserved Instances, with flexibility. | Variable                                     | Flexible with commitment to spending amount | Unused capacity for unutilized reservations          | Predictable spending with variable usage       | Allows commitment to a specific spending amount per month.                                        |
| Dedicated Host            | $0.10             | Exclusive use of dedicated hardware.             | None                                          | Highly inflexible, exclusive use           | Higher cost and limited flexibility                   | Regulatory or compliance requirements          | Ensures dedicated resources with no risk of sharing hardware with other users.                     |
| Capacity Reservation      | $0.10             | Pre-book capacity, pay full price upfront.       | None                                          | Guarantees availability                    | Risk of unused capacity if not utilized               | Predicted future needs with immediate usage   | Guarantees capacity availability but requires paying upfront regardless of usage.               |

# Day-15 Finished 🚀🎉

Today you have learned about AWS EC2 Purchasing Options.🌟
