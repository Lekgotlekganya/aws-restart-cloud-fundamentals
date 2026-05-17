# ☁️ Kganya's AWS re/Start Journey

> *"I didn't come from a cloud background. I came from data, curiosity, and the belief that understanding how technology works — really works — is worth every confusing moment."*

---

## 👋 Who Am I?

I'm Kganya — a Data Analysis background, a cloud beginner, and someone who decided to go all in on understanding the infrastructure behind the data I love working with.

This repository is my living, breathing record of that journey through the **AWS re/Start Programme** — every lab, every concept, every "I finally get it" moment. Nothing here is polished for the sake of it. It's real, it's honest, and it's mine.

---

## 🎯 The Goal

To earn my **AWS Certified Cloud Practitioner** certificate — and actually understand every single concept behind it, not just pass a test.

---

## 🗺️ What I'm Learning

The programme covers everything from the ground up:

**Compute** — Understanding virtual servers, how to launch them, connect to them, and scale them automatically.

**Networking** — Building private cloud networks, securing them, connecting them, and understanding how internet traffic actually flows.

**Storage & Databases** — The difference between storing files, structured data, and unstructured data — and when to use which.

**Security** — Who gets access to what, why it matters, and how one misconfigured port can bring everything down.

**Cloud Economics** — Because understanding the cloud isn't just technical — it's knowing how to build things that make financial sense.

**Python** — Automating and scripting in the cloud environment.

**AI & Machine Learning fundamentals** — Where cloud meets intelligence.

---

## 🏆 Certifications & Badges

### ✅ Earned
- 🎖️ **AWS Cloud Quest: Cloud Practitioner** — Completed all 12 activities including EC2, VPC, RDS, DynamoDB, EFS, IAM, Auto Scaling, High Availability and VPC Peering
- 🤖 **AI Badges** — Foundations in AI/ML concepts
- 📚 **Simulean Learn Badge** — Completed

### 🔜 In Progress
- 📜 **AWS Certified Cloud Practitioner** — The big one. Coming soon.

---

## 🎮 Cloud Quest — AWS Skill Builder

Cloud Quest is AWS's gamified learning platform. You take on real-world solution requests, configure actual AWS services, and validate your work. Every activity below was completed hands-on — no shortcuts.

### Activity 1 — Cloud First Steps
**The Brief:** Deploy a stabilization system across two EC2 instances in separate Availability Zones.

**What I Did:**
- Launched an Amazon EC2 instance
- Configured a user data script to display instance details in a browser
- Launched a second EC2 instance in a different Availability Zone for redundancy

**What I Learned:** Every EC2 instance lives in an Availability Zone. Spreading across zones means if one goes down, your system keeps running.

![Cloud First Steps](./cloud-quest/screenshots/Lesson-02__EC2_.jpg)

---

### Activity 2 — Computing Solutions
**The Brief:** Scale up an EC2 instance by selecting a larger instance type to enhance application performance.

**What I Did:**
- Explored Amazon EC2 instance types and their attributes
- Connected to an EC2 instance using EC2 Instance Connect
- Stopped the instance and changed the type from t3.micro → m4.large
- Verified the change without starting the instance (sandbox restriction)

**What I Learned:** You cannot change an instance type while it's running. Instance types define your compute power — rightsizing saves money without sacrificing performance.

![Computing Solutions](./cloud-quest/screenshots/Lesson-03_Change_size_of_EC2.jpg)

---

### Activity 3 — Networking Concepts
**The Brief:** Configure VPC networking components including routing tables, an internet gateway, and security groups to enable secure internet connectivity.

**What I Did:**
- Explored Virtual Private Cloud (VPC) components
- Configured a route table attached to a subnet
- Set up internet-bound traffic routing to the Internet Gateway
- Configured inbound security group rules to allow traffic on port 3306 into the DB server

**What I Learned:** A VPC is your private building in the cloud. The Internet Gateway is the front door. Route Tables are the GPS. Security Groups are the bouncers. Miss one — nothing connects.

![Networking Concepts](./cloud-quest/screenshots/Lesson_04.png)

---

### Activity 4 — Cloud Economics
**The Brief:** Create a cost estimate for a varying EC2 architecture based on peak demand.

**What I Did:**
- Created logical pricing groups in the AWS Pricing Calculator
- Built an estimate for Amazon EC2 usage
- Rightsized the instance from t3.medium → t2.micro
- Generated a new shareable price estimate link

**What I Learned:** The cloud can get expensive fast if you're not intentional. Rightsizing and Reserved Instances are how you build cost-predictable infrastructure.

![Cloud Economics](./cloud-quest/screenshots/Lesson_07.png)

---

### Activity 5 — Databases in Practice
**The Brief:** Migrate to Amazon RDS to automate routine database administration tasks while implementing Multi-AZ deployment and read replicas.

**What I Did:**
- Explored AWS database offerings
- Launched an Amazon RDS instance
- Configured a Multi-AZ deployment for high availability
- Set up Amazon RDS automated backups
- Created a Read Replica using a db.t3.xlarge instance

**What I Learned:** RDS removes the undifferentiated heavy lifting of database management. Read Replicas offload read traffic from your primary database — keeping everything fast under load.

![Databases in Practice](./cloud-quest/screenshots/Lesson_08.png)

---

### Activity 6 — First NoSQL Database
**The Brief:** Implement Amazon DynamoDB to store and process viewer behaviour data including content consumption and device analytics.

**What I Did:**
- Created a NoSQL DynamoDB table (UserVideoHistory)
- Added records with dynamic schema
- Created a new item with a unique userId and a Number attribute called "rating"
- Queried the DynamoDB table

**What I Learned:** NoSQL means no fixed structure — perfect for user data that varies per record. DynamoDB handles millions of requests per second with millisecond latency. Netflix runs on this.

![First NoSQL Database](./cloud-quest/screenshots/Lesson_9.png)

---

### Activity 7 — File Systems in the Cloud
**The Brief:** Implement Amazon EFS to provide a fully managed, scalable file system accessible across multiple branch locations.

**What I Did:**
- Launched and configured an Amazon EFS file system
- Mounted the EFS file system to an EC2 instance via terminal
- Connected a second EC2 instance to the same file system
- Mounted EFS to a third EC2 instance and verified file accessibility
- Used Linux terminal commands: `sudo mkdir`, `sudo mount -t efs`, `ls`

**What I Learned:** EFS is a shared network drive for your EC2 instances. Multiple servers, one file system. Unlike EBS which is locked to one instance, EFS scales across your entire infrastructure.

![File Systems in the Cloud](./cloud-quest/screenshots/Lesson_10.png)

---

### Activity 8 — Highly Available Web Applications
**The Brief:** Deploy a web application across multiple Availability Zones with an Application Load Balancer and health checks.

**What I Did:**
- Created a Target Group (TravelAgencyWebServer-TG)
- Created a Security Group (TravelAgencyLoadBalancer)
- Configured an Application Load Balancer (TravelAgencyServers-ALB)
- Added a second Availability Zone to the Auto Scaling group
- Extended to a third Availability Zone with increased desired capacity

**What I Learned:** High availability isn't one big powerful server — it's multiple servers across multiple zones with a Load Balancer distributing traffic between them. If one zone fails, nobody notices.

![Highly Available Web Applications](./cloud-quest/screenshots/Lesson_11.png)

---

### Activity 9 — Connecting VPCs
**The Brief:** Implement VPC peering to enable communication between VPCs, allowing Marketing and Developer EC2 instances to access the Finance VPC.

**What I Did:**
- Set up VPC peering connections between department VPCs
- Configured route tables in both VPCs to route traffic correctly
- Verified that Marketing and Developer servers could reach the Finance server

**What I Learned:** VPC Peering is a private tunnel between two separate networks. It's not transitive — A talking to B and B talking to C doesn't mean A can talk to C. Route tables must be updated on both sides.

![Connecting VPCs](./cloud-quest/screenshots/Lesson_12.png)

---

## 🧪 Labs

Every lab I complete gets documented here — not just what I did, but what I actually learned from it.

### Compute
- Launching EC2 instances from scratch
- Connecting via SSH using PuTTY and key pairs (.ppk)
- Configuring Security Groups (Port 22 for SSH, Port 80 for HTTP)
- Changing instance types and understanding rightsizing
- Sandbox environment exploration

### Networking
- Building VPCs and configuring subnets
- Setting up Internet Gateways and Route Tables
- Security group inbound and outbound rules
- VPC Peering across departments
- Understanding CIDR notation (0.0.0.0/0 vs /32)

### Database
- Setting up managed RDS instances with Multi-AZ
- Creating Read Replicas for performance
- Building NoSQL tables in DynamoDB with dynamic schemas
- Understanding SQL vs NoSQL use cases

### Python
*(Coming soon — labs being added)*

---

## 📝 Notes & Documentation

I learn best by visualising — so every concept in these notes has a real world analogy, a story, and an exam tip.

- 📄 [AWS Cloud Quest Notes](./cloud-quest/notes/aws-cloud-quest-notes.md) — Full breakdown of every Cloud Quest activity with analogies, stories and exam points

---

## 💡 Projects

*(This section grows as I build — real projects using real AWS services)*

---

## 🧠 A Note On Why

I come from Data Analysis. I know how to work with data — but I kept hitting a wall when it came to understanding *where* that data lives, *how* it moves, and *why* some systems are fast and others aren't.

AWS re/Start answered all of that.

Now I'm building towards being someone who doesn't just analyse data — but understands the entire infrastructure it sits on. Cloud + Data is not a common combination. That's exactly why I'm building it.

---

## 📬 Connect With Me

*(Add your LinkedIn/GitHub profile link here)*

---

*This repository is updated as I learn — imperfect, intentional, and completely mine.* ☁️
