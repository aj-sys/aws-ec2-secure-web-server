
# AWS EC2 Secure Web Server Deployment

## Project Overview

This project demonstrates the practical implementation of basic AWS cloud infrastructure, security and web server deployment.

The project uses the AWS Management Console to configure Identity and Access Management (IAM), launch an Amazon EC2 instance, configure network access and deploy a basic HTML website using Apache.

## Project Objectives

1. Understand IAM users, groups, roles, policies and permissions.
2. Apply basic AWS security principles, including least privilege.
3. Launch and configure an Amazon EC2 instance.
4. Configure a Security Group and connect to EC2.
5. Install a web server and deploy a basic HTML website.

## Technologies and AWS Services

- Amazon Web Services (AWS)
- AWS Identity and Access Management (IAM)
- Amazon Elastic Compute Cloud (EC2)
- Amazon VPC
- EC2 Security Groups
- Amazon Linux
- Apache HTTP Server
- HTML and CSS
- Git and GitHub

## Project Structure

```text
aws-ec2-secure-web-server/
│
├── index.html
├── .gitignore
└── README.md
```

## Implementation Plan

### 1. IAM Security Configuration
- Create an IAM user and group.
- Explore IAM policies and permissions.
- Understand IAM roles.
- Apply the principle of least privilege.

### 2. EC2 Instance Configuration
- Launch an EC2 instance.
- Select an appropriate Amazon Machine Image (AMI).
- Configure instance settings.
- Connect to the instance.

### 3. Security Group Configuration
- Configure inbound rules.
- Allow HTTP traffic on port 80.
- Configure appropriate SSH access.

### 4. Web Server Installation
- Install Apache on the EC2 instance.
- Start and enable the Apache service.
- Configure the web server.

### 5. Website Deployment
- Deploy the HTML website.
- Access the website using the EC2 public IP address.
- Verify that the website loads successfully.

## Website Preview

The website is contained in `index.html` and will be hosted on the EC2 instance after the web server configuration is completed.

## Project Status

- [x] Create project folder.
- [x] Develop basic HTML website.
- [x] Initialise local Git repository.
- [x] Create GitHub repository.
- [ ] Configure IAM users, groups, roles and policies.
- [ ] Launch EC2 instance.
- [ ] Configure Security Groups.
- [ ] Install Apache web server.
- [ ] Deploy and test website.

## Repository

GitHub: https://github.com/aj-sys/aws-ec2-secure-web-server

---

**Author:** Ajara Amadu

**Project:** AWS Cloud Computing Internship Practical Project
