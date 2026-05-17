# 🖥️ Sandbox Lab: Launching My First EC2 Instance

> *"This was the first time I built something in AWS completely from scratch — no guided steps, no Cloud Quest holding my hand. Just me, the AWS Console, and a goal."*

---

## 📋 Lab Overview

**Environment:** AWS re/Start Sandbox Lab
**Region:** US West (Oregon) — us-west-2
**Date:** May 2026
**Outcome:** ✅ Successfully launched, configured and connected to an EC2 instance via SSH

---

## 🎯 What I Set Out To Do

Launch a fully configured EC2 instance from scratch including:
- Choosing the right AMI
- Configuring the instance type
- Setting up a security group with the correct ports
- Creating a key pair for secure SSH access
- Launching and connecting to the instance
- Understanding termination protection

---

## 📸 Step by Step — What I Actually Did

### Step 1: Name The Instance
Every instance needs a name. I named mine **"Web Server"** — keeping it simple and descriptive.

![Name Instance](./screenshots/Name_instance_md.png)

---

### Step 2: Choose An AMI
An AMI (Amazon Machine Image) is the blueprint for your server — like choosing what operating system your computer comes with.

I selected **Amazon Linux 2023** — AWS's own Linux distribution, optimised for cloud workloads and free tier eligible.

![AMI Selection](./screenshots/AMI_md.png)

> **Why Amazon Linux?** It's maintained by AWS, comes pre-configured for the cloud environment, and has 5 years of long term support. For a web server — it's the obvious choice.

---

### Step 3: Choose Instance Type
The instance type defines how powerful your server is — CPU, memory, and network performance.

I selected **t3.micro** — 2 vCPUs, 1 GiB Memory, free tier eligible. Perfect for a sandbox web server.

![Instance Type](./screenshots/Instance_type_md.png)

---

### Step 4: Create A Key Pair
A key pair is how you securely connect to your instance. AWS holds the lock (public key), you hold the key (private key — downloaded as a .ppk file).

I created a new key pair called **sandbox-key** and downloaded the .ppk file for PuTTY access on Windows.

![Key Pair](./screenshots/Key_pair_md.png)

> ⚠️ **Important:** The .ppk file can only be downloaded once. Lose it and you lose access to your instance. I saved mine immediately.

---

### Step 5: Configure Security Group
A security group is a virtual firewall — it controls what traffic can reach your instance.

I created a new security group called **"Web Server security group"** with:
- **Port 22 (SSH)** — for secure remote terminal access
- **Port 80 (HTTP)** — for web traffic

![Security Group](./screenshots/Security_Group_md.png)

> **The rule I learned the hard way:** Public Subnet ≠ Automatic Access. Without the right security group rules, nothing connects — even if everything else is configured correctly.

---

### Step 6: Launch The Instance
With everything configured — AMI, instance type, key pair, and security group — I launched the instance.

![Launch EC2](./screenshots/Launch_EC2_md.png)

---

### Step 7: Instance Running
After launching, the instance appeared in the EC2 Instances list with status **Running** in Availability Zone **us-west-2b**.

![Launched Instance](./screenshots/Launched_Instance_md.png)

---

### Step 8: Instance Booting
The AWS boot screen — confirmation that Amazon Linux 2023 was loading successfully on my instance.

![Instance Screenshot](./screenshots/instance_screenshot_md.jpg)

---

### Step 9: Configuring Inbound Rules
After launch I explored the security group's inbound rules — checking what traffic was allowed in and understanding how to edit them.

**Before adding rules:**

![Edit Inbound Rules](./screenshots/Edit_inbound_rules_md.png)

**After configuring:**

![Inbound Rules Final](./screenshots/Inbound_Rules_final_result_md.png)

---

### Step 10: Changing Instance Type
I also practised changing the instance type — a key skill from Cloud Quest.

Through **Actions → Instance Settings → Change Instance Type** I accessed the menu to modify the instance's compute power.

![Change Instance Type](./screenshots/Change_instance_type_md.png)

> ⚠️ **Remember:** The instance must be STOPPED before you can change its type. Running instances cannot be modified.

---

### Step 11: Termination Protection
I discovered termination protection — a safety feature that prevents accidental deletion of your instance.

**Enabling it:**

![Termination Protection](./screenshots/Termination_Protection_md.png)

**Disabling it (to allow termination):**

![Termination Protection Remove](./screenshots/Termination_Protection_Remove_md.png)

> When I tried to terminate the instance without disabling protection first — AWS blocked it with an error. That's exactly what it's designed to do!

---

## 🔗 Connecting Via SSH (PuTTY)

After launching the instance I connected to it remotely using PuTTY:

1. Opened PuTTY and entered the **Public IPv4 address** as the Host Name
2. Navigated to **Connection → SSH → Auth → Credentials**
3. Loaded the **sandbox-key.ppk** file
4. Clicked **Open** and logged in as **ec2-user**
5. Successfully entered the Amazon Linux 2023 terminal! ✅

```
Authenticating with public key "sandbox-key"
####   Amazon Linux 2023
####
[ec2-user@ip-172-31-7-45 ~]$
```

---

## 💡 What I Learned

**Technical skills gained:**
- How to launch an EC2 instance from scratch
- AMI selection and what it means
- Instance type selection and rightsizing
- Key pair creation and management (.ppk for Windows)
- Security group configuration (Port 22 and Port 80)
- SSH connection via PuTTY
- Termination protection — enabling and disabling
- How to change an instance type

**Conceptual understanding:**
- The relationship between AMI, instance type, and security groups
- Why key pairs exist and why losing them matters
- How ports control access to your server
- The difference between stopping and terminating an instance

---

## ⭐ Key Exam Points From This Lab

| Concept | Remember This |
|---|---|
| **AMI** | Blueprint/template for your EC2 instance |
| **Instance type** | Defines CPU, RAM, network power |
| **Key pair** | .pem for Mac/Linux, .ppk for Windows PuTTY |
| **Port 22** | SSH — remote terminal access |
| **Port 80** | HTTP — web traffic |
| **Termination protection** | Prevents accidental deletion |
| **Stop vs Terminate** | Stop = pause, Terminate = delete forever |
| **Change instance type** | Must STOP instance first! |

---

## 🔗 Related Notes

- [AWS Cloud Quest Notes](../../cloud-quest/notes/aws-cloud-quest-notes.md) — Full concept breakdown with analogies
- [Back to README](../../README.md)

---

*Sandbox Lab completed — May 2026 | AWS re/Start Programme*
