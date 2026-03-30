# AWS EC2 Lab

## Objectives
- Launch an EC2 instance on AWS
- Connect to EC2 using EC2 Instance Connect
- Understand Security Groups and Key Pairs

## Technologies Used
- AWS EC2
- Amazon Linux 2023
- AWS Security Group
- EC2 Instance Connect

## Steps

### 1. Launch EC2 Instance
- AMI: Amazon Linux 2023 (Free Tier eligible)
- Instance type: t3.micro (Free Tier eligible)
- Key pair: RSA, .pem format

### 2. Configure Security Group
- Allow SSH (Port 22) from anywhere
- Principle of Least Privilege: only open necessary ports

### 3. Connect to EC2
- Used EC2 Instance Connect via AWS Console
- No key pair required, connect directly from browser

## What I Learned
- EC2 is an IaaS service on AWS
- Security Groups act as a virtual firewall
- Difference between Public IP and Private IP
- EC2 Instance Connect does not require a key pair
- Principle of Least Privilege in Security Groups

## Screenshots
### Launch Instance
![Launch Instance](screenshots/01.EC2_name.png)

### AMI Selection
![AMI Selection](screenshots/02.Choose_AMI.png)

### Instance Type
![Instance Type](screenshots/03.Instance_Type.png)

### Key Pair
![Key Pair](screenshots/04.Keypair.png)

### Security Group
![Security Group](screenshots/05.Network_Settings%20.png)

### Summary
![Summary](screenshots/06.Summary.png)

### Instance Running
![Instance Running](screenshots/07.Instance_Running.png)

### EC2 Instance Connect
![EC2 Connect](screenshots/08.EC2-Connect%20.png)