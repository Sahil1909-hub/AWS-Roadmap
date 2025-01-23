# AWS-EC2-SETUP-NGINX

---

# 🚀 Hosting a Website on Nginx Server on AWS EC2 (Amazon Linux)

This guide will walk you through the process of setting up an **Nginx** web server on an **Amazon EC2 instance** running **Amazon Linux**. By the end, you'll have a simple website hosted and accessible via your public IP address.

---

## 🖊️ Prerequisites
![Image](https://github.com/user-attachments/assets/21cb2614-4b0e-40f4-b979-80632e10b2a3)

Ensure you have the following:
1. ✅ An **AWS account** and access to the **AWS Management Console**.
2. ✅ A **running EC2 instance** (preferably **Amazon Linux 2**).
3. ✅ SSH access to the EC2 instance using a **.pem private key**.
4. ✅ **Default VPC** and **Security Group** configured.
5. ✅ A **Security Group** allowing **HTTP (port 80)** and **HTTPS (port 443)** inbound traffic.

If you don't have an EC2 instance, create one using the **Amazon Linux 2** AMI within the **default VPC**.

---

## 🛠️ Step-by-Step Guide

### Step 1: Connect to Your EC2 Instance via SSH

1. Open a terminal.
2. Use the following command to connect to your EC2 instance (replace `your-key.pem` with your private key file and `your-ec2-public-ip` with your instance's public IP):

   ```bash
   ssh -i "your-key.pem" ec2-user@your-ec2-public-ip
   ```

   For **Ubuntu**-based instances, replace `ec2-user` with `ubuntu`:

   ```bash
   ssh -i "your-key.pem" ubuntu@your-ec2-public-ip
   ```

---

### Step 2: Update Your EC2 Instance

Update the instance’s package list:

```bash
sudo yum update -y
```

---

### Step 3: Install Nginx

Install **Nginx** with the following commands:

```bash
sudo amazon-linux-extras install nginx1 -y
