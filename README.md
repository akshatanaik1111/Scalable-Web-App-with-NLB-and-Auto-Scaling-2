# Scalable Web App with NLB and Auto Scaling

## 📌 Project Overview

This project demonstrates how to deploy a scalable and high-performance web application on AWS using Network Load Balancer (NLB) and Auto Scaling Group.

The main objective of this project is to efficiently manage heavy traffic with low latency and high-speed performance. The Network Load Balancer distributes incoming traffic across multiple EC2 instances while the Auto Scaling Group automatically adjusts resources according to traffic demand.

This project helps in understanding scalable cloud architecture and high-performance networking in AWS.

---

# 🎯 Objective

- Handle high-performance traffic
- Reduce latency
- Automatically scale EC2 instances
- Improve application availability
- Build fault-tolerant infrastructure

---

# 🧰 AWS Services Used

## 1. Amazon EC2
Used to host the web application on virtual servers.

## 2. Network Load Balancer (NLB)
Used to distribute TCP traffic with ultra-low latency and high performance.

## 3. Auto Scaling Group
Automatically increases or decreases EC2 instances based on traffic.

## 4. Target Group
Used to route traffic from NLB to EC2 instances.

## 5. Security Groups
Controls secure inbound and outbound traffic.

## 6. AWS VPC
Provides networking environment for deployment.

---

# 🏗️ Project Architecture

The project architecture includes:

1. Creating EC2 instances
2. Configuring Security Groups
3. Creating Target Group
4. Creating Network Load Balancer
5. Connecting NLB with Target Group
6. Creating Launch Template
7. Creating Auto Scaling Group
8. Testing scalability and performance

---

# ⚙️ Step-by-Step Implementation

## Step 1: Launch EC2 Instance

- Open AWS Console
- Go to EC2 Dashboard
- Click Launch Instance
- Select Amazon Linux AMI
- Choose Instance Type
- Configure Security Group
- Allow:
  - HTTP (Port 80)
  - SSH (Port 22)

---

## Step 2: Install Web Server

Connect EC2 using SSH and run:

```bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

Create sample webpage:

```bash
echo "Welcome to NLB Scalable Web App" | sudo tee /var/www/html/index.html
```

---

## Step 3: Create Target Group

- Go to EC2 Dashboard
- Select Target Groups
- Create Target Group
- Choose:
  - Target type: Instances
  - Protocol: TCP
  - Port: 80
- Register EC2 instances

---

## Step 4: Create Network Load Balancer

- Go to Load Balancers
- Create Load Balancer
- Select:
  - Network Load Balancer
- Choose Internet-facing
- Add Listener:
  - TCP : 80
- Attach Target Group

---

## Step 5: Create Launch Template

- Go to Launch Templates
- Create Launch Template
- Configure:
  - AMI
  - Instance Type
  - Security Group
  - User Data Script

User Data Script:

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
echo "NLB Scalable Web App Running" > /var/www/html/index.html
```

---

## Step 6: Create Auto Scaling Group

- Go to Auto Scaling Groups
- Create Auto Scaling Group
- Select Launch Template
- Configure:
  - Minimum capacity
  - Maximum capacity
  - Desired capacity
- Attach NLB
- Enable scaling policies

---

## Step 7: Test Application

- Copy NLB DNS URL
- Open in browser
- Verify application loads successfully
- Test scaling using traffic simulation

---

# 📸 Project Screenshots

## 🔹 Network Load Balancer

<img width="1724" height="764" alt="image" src="https://github.com/user-attachments/assets/788b960f-90ea-4e5b-8d26-08a2c83f11cb" />

---

## 🔹 Auto Scaling Group

<img width="1724" height="766" alt="image" src="https://github.com/user-attachments/assets/6a469927-e7ca-4882-9ec0-7f6a4993e62e" />

---

## 🔹 EC2 Instances

<img width="1594" height="701" alt="image" src="https://github.com/user-attachments/assets/011b324f-0967-4caa-bd56-e933661ca0ca" />

---

## 🔹 Target Group

<img width="1594" height="804" alt="image" src="https://github.com/user-attachments/assets/4628d4f4-ec1e-4964-927f-b5370b1cbe58" />

---

## 🔹 Security Group
<img width="1596" height="666" alt="image" src="https://github.com/user-attachments/assets/17adef06-cbfd-42de-aab1-ebff1abeb057" />


---

## 🔹 Application Output

<img width="1600" height="850" alt="image" src="https://github.com/user-attachments/assets/3551fcbd-0358-4e3d-80aa-1a3a4a39bd1d" />

---

## 🔹 Final Output

<img width="1596" height="810" alt="image" src="https://github.com/user-attachments/assets/c787a59a-0cb5-4be5-b7b6-08d78bd722a4" />


<img width="1591" height="815" alt="image" src="https://github.com/user-attachments/assets/c81bf798-8aa2-435b-a0ce-faba2f0f7b3a" />

---

# ✅ Features

- High Performance
- Low Latency
- Automatic Scaling
- Traffic Distribution
- High Availability
- Fault Tolerance
- Better Network Performance

---

# 📚 Learning Outcomes

Through this project, I learned:

- How Network Load Balancer works
- Difference between ALB and NLB
- How to configure Auto Scaling Group
- How Target Groups route traffic
- Security Group configuration
- Real-world scalable AWS deployment

---

# 🚀 Future Improvements

- Add HTTPS/TLS Support
- Configure CloudWatch Monitoring
- Add Route 53 Domain Mapping
- Implement CI/CD Pipeline
- Add Database Integration

---

# 🏁 Conclusion

This project successfully demonstrates scalable and high-performance application deployment using Network Load Balancer and Auto Scaling on AWS. The infrastructure efficiently manages low-latency traffic and automatically scales resources according to demand.

---

# 👩‍💻 Author

Akshata Naik

---
