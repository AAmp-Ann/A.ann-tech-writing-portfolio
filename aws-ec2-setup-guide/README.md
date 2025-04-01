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
  


