# Frontend Web Application Deployment on AWS EC2

## 📌 Project Overview
This project demonstrates the manual deployment of a **frontend web application** on an **AWS EC2 instance** using **Nginx** as a web server.

The application is built using **HTML, CSS, and JavaScript** and hosted on an Amazon Linux EC2 server.  
This project focuses on understanding **EC2 basics, Linux commands, Nginx setup, and AWS security groups**.

---

## 🛠️ Tech Stack
- **Frontend:** HTML, CSS, JavaScript  
- **Cloud Platform:** AWS  
- **Service:** EC2  
- **Web Server:** Nginx  
- **Operating System:** Amazon Linux  
- **Version Control:** Git & GitHub  

---

## 🏗️ Project Architecture
- Source code stored in GitHub
- EC2 instance acts as the web server
- Nginx serves static frontend files
- Security Group allows HTTP traffic on port 80

---

## 🚀 Deployment Steps

### 1️⃣ Launch EC2 Instance
- Created an EC2 instance using **Amazon Linux**
- Selected a free-tier eligible instance type
- Generated a `.pem` key pair for SSH access

---

### 2️⃣ Connect to EC2 via SSH
```bash
chmod 400 your-key.pem
ssh -i your-key.pem ec2-user@<EC2-PUBLIC-IP>

**Install and Configure Nginx**
sudo yum install nginx -y
sudo systemctl start nginx
sudo systemctl enable nginx

**Clone GitHub Repository**
git clone https://github.com/jacksamson1503/Frontend_Web-Application-Deployment-on-AWS-EC2.git

**Deploy Application Files**
sudo cp -r Frontend_Web-Application-Deployment-on-AWS-EC2/* /usr/share/nginx/html/
sudo chown -R nginx:nginx /usr/share/nginx/html

**Configure Security Group**
Added inbound rule:
HTTP (Port 80) → 0.0.0.0/0

**Access the Application**
Open a browser and visit:
http://<EC2-PUBLIC-IP>
