# ⚡ AWS Auto Scaling & CloudWatch Monitoring

A hands-on project demonstrating how to build a highly available and scalable application on AWS using Auto Scaling Groups, Application Load Balancer, and CloudWatch monitoring.

---

## 📌 Project Overview

This project sets up an auto-scaling web application on AWS that automatically increases or decreases the number of EC2 instances based on traffic load, with real-time monitoring and alerting using CloudWatch and SNS.

---

## 🛠️ Tools & Services Used

- AWS EC2
- Auto Scaling Groups (ASG)
- Application Load Balancer (ALB)
- Amazon CloudWatch
- Amazon SNS (Simple Notification Service)
- Launch Template

---

## 📋 What I Did — Step by Step

### 1. Created a Launch Template
- Defined EC2 instance type, AMI, security groups, and key pair
- Used the launch template as the base for Auto Scaling

### 2. Set Up Auto Scaling Group
- Created an Auto Scaling Group using the launch template
- Set minimum instances: **1**, desired: **2**, maximum: **4**
- Configured scaling policies based on CPU utilization
  - Scale OUT when CPU > 70%
  - Scale IN when CPU < 30%

### 3. Configured Application Load Balancer (ALB)
- Created an Application Load Balancer in the public subnet
- Created a Target Group and attached the Auto Scaling Group to it
- ALB distributes incoming traffic evenly across all healthy EC2 instances

### 4. Set Up CloudWatch Monitoring
- Enabled detailed monitoring on EC2 instances
- Created CloudWatch dashboards to visualize:
  - CPU Utilization
  - Network In/Out
  - Instance health status

### 5. Configured CloudWatch Alarms + SNS Alerts
- Created a CloudWatch alarm triggered when CPU utilization exceeds **80%**
- Integrated with **SNS** to send email notifications when alarm is triggered
- This helps monitor the application health in real time

---

## 🏗️ Architecture Diagram

```
Internet Traffic
      |
Application Load Balancer (ALB)
      |
  ┌───────────────────────┐
  |   Auto Scaling Group  |
  |  ┌────┐ ┌────┐ ┌────┐ |
  |  | EC2| | EC2| | EC2| |   <-- Scales up/down automatically
  |  └────┘ └────┘ └────┘ |
  └───────────────────────┘
      |
  CloudWatch Metrics
      |
  SNS Email Alert (when CPU > 80%)
```

---

## 🎯 Key Learnings

- How Auto Scaling ensures high availability and cost efficiency
- How Load Balancers distribute traffic to prevent overload
- How CloudWatch metrics help monitor application performance
- How SNS integrates with CloudWatch for real-time alerting

---

## 👨‍💻 Author

**Prasanth S**  
Cloud & DevOps Enthusiast | AWS | Linux | DevOps  
📧 prasanthprasanthleo@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/prasanth-14a620255)
