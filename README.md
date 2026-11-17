# AWS EC2 Secure Web Server Deployment

## Project Overview

This project demonstrates the provisioning, configuration, security and deployment of a basic web server on Amazon Web Services (AWS).

The project uses an Amazon EC2 instance running Amazon Linux 2023 and Apache HTTP Server to host a static HTML website. The website source code is maintained in GitHub and deployed to the EC2 instance.

## Project Objectives

### 1. IAM Security Configuration
- Create an IAM user and group.
- Explore IAM policies and permissions.
- Understand IAM roles and trusted entities.
- Apply the principle of least privilege.

### 2. EC2 Instance Provisioning
- Launch an Amazon EC2 instance.
- Select an appropriate Amazon Machine Image (AMI).
- Configure the instance type and storage.
- Connect to the instance using EC2 Instance Connect.

### 3. Network Security Configuration
- Create and configure an EC2 Security Group.
- Configure SSH access through port 22.
- Allow HTTP traffic through port 80.
- Restrict SSH access to a trusted IP address.

### 4. Linux Server Administration
- Update the Amazon Linux operating system.
- Install Apache HTTP Server.
- Start and enable the Apache service.
- Verify the web server status.

### 5. Website Deployment
- Create a basic HTML website.
- Maintain the source code in GitHub.
- Clone the GitHub repository onto the EC2 instance.
- Deploy the HTML file to Apache's document directory.
- Test website accessibility using the public IPv4 address.

## Technologies and AWS Services

- Amazon Web Services (AWS)
- AWS Identity and Access Management (IAM)
- Amazon Elastic Compute Cloud (EC2)
- Amazon Virtual Private Cloud (VPC)
- AWS Security Groups
- Amazon Linux 2023
- Apache HTTP Server
- HTML and CSS
- Git and GitHub

## Project Implementation

### 1. IAM Security Configuration

- Created an IAM group named `EC2-WebServer-Users`.
- Attached the AWS-managed `AmazonEC2ReadOnlyAccess` policy to the group.
- Created an IAM user named `ec2-webserver-user`.
- Added the IAM user to the `EC2-WebServer-Users` group.
- Created an IAM role named `EC2-WebServer-Role` with EC2 as its trusted service.

**Security consideration:** The IAM role was created without additional permission policies because the static website does not require access to other AWS services. The role was not attached to the EC2 instance during this deployment.

### 2. EC2 Instance Configuration

- Instance name: `AWS-WebServer-Project`
- AMI: Amazon Linux 2023
- Instance type: `t3.micro`
- Storage: 8 GiB
- Connection method: EC2 Instance Connect

### 3. Security Group Configuration

Created a Security Group named `WebServer-SG` with the following inbound rules:

| Type | Protocol | Port | Source |
|---|---|---|---|
| SSH | TCP | 22 | My IP |
| HTTP | TCP | 80 | 0.0.0.0/0 |

### 4. Linux Server Administration

Updated the operating system:

```bash
sudo dnf update -y
```

Installed Apache:

```bash
sudo dnf install httpd -y
```

Started Apache:

```bash
sudo systemctl start httpd
```

Enabled Apache at system startup:

```bash
sudo systemctl enable httpd
```

Verified the Apache service:

```bash
sudo systemctl status httpd
```

### 5. Website Deployment

Installed Git:

```bash
sudo dnf install git -y
```

Cloned the GitHub repository:

```bash
git clone https://github.com/aj-sys/aws-ec2-secure-web-server.git
```

Copied the website file to Apache's document directory:

```bash
sudo cp ~/aws-ec2-secure-web-server/index.html /var/www/html/index.html
```

Configured file permissions:

```bash
sudo chmod 644 /var/www/html/index.html
```

Tested the local web server:

```bash
curl -I http://localhost
```

**Result:** HTTP 200 OK.

### 6. Website Verification

- Accessed the website through the EC2 public IPv4 address.
- Confirmed that the HTML website loaded successfully.
- Verified that Apache served the deployed website.

**Live Website:** http://52.91.66.26

## Project Architecture

```text
                 Internet
                    |
                    |
             Internet Gateway
                    |
                    |
                AWS VPC
                    |
                 Subnet
                    |
              Security Group
                /       \
           SSH : 22   HTTP : 80
                \       /
                    |
              EC