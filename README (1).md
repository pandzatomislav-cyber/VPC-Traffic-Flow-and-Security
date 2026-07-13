<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-security)

**Author:** Tomislav Pandza  
**Email:** pandza.tomislav@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

An Amazon VPC (Virtual Private Cloud) is your own private, logically isolated section of the AWS Cloud. Think of it like renting a secure, private plot of land in a massive digital city where you get to decide how the roads are built, who is allowed to enter, and which houses can talk to each other.

Complete Control: You get to design the network from scratch. You choose the IP address ranges, divide them into smaller neighborhoods called subnets, and decide which areas are public or private.

Layered Security: You can secure your resources at multiple levels. You do this using virtual firewalls like security groups (which protect individual resources) and Network ACLs (which protect entire subnets).
Flexible Connectivity: You choose exactly how your resources connect to the world. You can connect them to the public internet using an internet gateway, connect them to other networks, or keep them entirely isolated.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to route tables, security groups and network ACL's. I also created all of it through a console and the Amazon CLI as well as doing that in a different availability zone. Finally, I used EC2 Global View to navigate through my resources in one place with a lot more ease and efficiency

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that there was such a thing as the EC2 Global vew where you can see all your resources in different zones.

### This project took me...

This project took me about an hour and a half with all the reading and executing step by step

---

## Route tables

Route tables are tables of rules, called routes, that decide where the data in your network should go. Like a GPS that navigates traffic.

Routes tables are needed to make a subnet public because the subnet on its own is isolated from the outside world and only can talk to other subnets in the same VPC.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target. Destination is the IP address range that traffic wants to reach and target is the way or the route how that traffic gets there.

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of igw-00be0860f08b5aa1b.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are like security checkpoints for each resource in a subnet.

### Inbound vs Outbound rules

Inbound rules refer to any data from the internet being able to have access to your resources. I configured an inbound rule to be HTTP type and Destination 0.0.0.0/0, which means any IP can have access to my resource.

Outbound rules refer to any data coming from the resources to the internet. By default, my security group's outbound rule is All traffic and Destination 0.0.0.0/0.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are checking each data packet against a table of ACL rules before allowing them through. Positioned at every entry and exit point for your subnet.

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that security groups are bound to your individual resources and network ACLs are bound to whole subnets.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will be All traffic with the destiantion being 0.0.0.0/0 which allows any data coming in and out.

In contrast, a custom ACL’s inbound and outbound rules are automatically set to nothing which denies any traffic in or out so we can tailor it later on.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

I created additional VPC, internet gateway and security group. Instead of my usual region, I used Asia Pacific Osaka - ap-northeast-3. Teams would use multiple regions to improve latency.

EC2 Global View is a tool where you can find Key networking resources and Key cimpute & storage resources. I could even narrow down my search by going into regions as zones and seing my exact resources.

Now that I've learnt about EC2 Global View, I'd use it again to see all resources in all regions.

![Image](http://nextwork.ai/elated_teal_vibrant_raccoon/uploads/aws-networks-security_b03ea6162)

---

---
