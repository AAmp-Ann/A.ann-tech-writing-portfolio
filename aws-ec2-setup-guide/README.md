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


