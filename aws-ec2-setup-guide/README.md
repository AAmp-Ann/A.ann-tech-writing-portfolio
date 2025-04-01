# AWS EC2 Instance Setup Guide for Developers
## Overview
This guide walks developers through launching and configuring an EC2 instance using the AWS Console.
___
## 1. Prerequisites

Before you begin,make sure you have:
- An active AWS account
- IAM user access with EC2 permissions
- A key pair for SSH access

## 2. Launching and EC2 Instance 

### Step-by-Step

1. Log in to the [AWS Console](Https://console.aws.amazon.com/)
2. Navigate to **EC2 > Instance > Launch Instance**
3. Configiure the following:
   - **Name**: 'dev-ec2-instance'
   - **AMI**: Amazon Linux 2023 or Ubuntu 22.04 LTS 
   - **Instance type**: 't2.micro' (free tier eligible)
   - **Key pair**: Create new or select existing
   - **Network settings**: Allow SSH (port 22) and HTTP (port 80)
   - **Storage**: Keep default (8 GB)
4. Click **Launch Instance**
5. Once initialized,note the **public IPv4 address**

## 3. Connecting via SSH

Once your EC2 instance is running , you can connect to it using SSH (Secure Shell). This allows you to access the server through your terminal.

### Step-by-Step

1. Locate the '.pem' file (your private key) you downlaod when you created the key pair.
2. Open your terminal.
3. Navigate to the directory where your '.pem' file is located.
4. Run the following command to set proper permission on your key file:

   ```bash
   chmod 400 your-key-name.pem

5. Then connect to the EC2 instance:
   ```bash   
   ssh -i your-key-name.pem ec2-user@<your-ec2-ip>

- **Replace your-key-name.pem with your actual file name**.
- **Replace<your-ec2-ip> with your instance's public IPv4 address (found in the EC2 dashboard)**
- **If you're using an Ubantu image,change ec2-user to ubantu.**

## 4. Configuring Security Groups

Security groups act like virtual firewalls. They control inbound and outbound traffic to your EC2 instance and help secure your cloud enviroment.

### Common Ports to Configure:

- **SSH (Port 22):** Used to access your instance from the terminal.
  Best practice : Only allow your personal IP address.
 
- **HTTP (Port 80):** Used to host a website or web server.
  This can be open to everyone (0.0.0.0/0) for testing public access.

- **HTTPS (Port 443):** Used for secure websites with SSL/TLS encryption.
  Optional,depending on whether you're using HTTPS.

### How to Configure in the AWS Console:

1. In the AWS Console, go to **EC2 > Instances** and select your instance.
2. Scroll down to the **Description** tab and find the **Security groups** section.
3. Click the name of the sercurity group linked to your instance.
4. Under the **Inbound rules** tab, click **Edit inbound rules**.
5. Add the following rules:
   - **Type:** SSH, **Port Range:** 22, **Source:** My IP
   - **Type:** HTTP, **Port Range:** 80, **Source:** Anywhere
   - **Type:** HTTPS, **Port Range:** 443, **Source:** Anywahere (Optional)
6. Click **Save rules** to apply your changes.

## 5. Installing Devlopment Tools

To prepare your EC2 instance for devlopment, You'll need to install commonly used tools like Node.js and Git.

### For amazon Linux 2023:

1. First, update your system packages:

   ```bash
   sudo yum uodate -y

2. Install Node.js(version 18) and Git:
   ```bash
   curl -fsSL https://rpm.nodesource.com/setup_18.x | sudo bash -
   sudo yum install -y nodejs git

3. Confirm the installations:
   ```bash
   node -y
   git --version
   
You should see version numbers in your terminal for both commands.
   

  
 
  


