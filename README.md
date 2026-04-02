# 🥋 Zenith Karate Dojo – Azure VM Web Server Deployment

## 📌 Overview

This project demonstrates the deployment of a production-style web server on a Microsoft Azure Virtual Machine using Linux, Nginx, and Bash automation. A fully styled static website is hosted and made accessible via a public IP address.

---

## 🎯 Key Highlights

* Automated web server deployment using Bash
* Azure Virtual Machine provisioning and configuration
* Nginx installation and service management
* Structured project organization (scripts, website, documentation)
* Public web access via HTTP

---

## 🏗️ Architecture

Client Browser → Internet → Azure Virtual Machine → Nginx → Hosted Website

---

## 🛠️ Tech Stack

* Microsoft Azure (Virtual Machines)
* Ubuntu 22.04 LTS
* Bash Scripting
* Nginx
* HTML & CSS

---

## ⚙️ Deployment Process

### 1. Provision Infrastructure

* Create Resource Group
* Deploy Ubuntu VM
* Open ports: **22 (SSH)** and **80 (HTTP)**

### 2. Connect to VM

```bash
ssh azureuser@<PublicIP>
nano deploy.sh
```

### 3. Deploy Application

```bash
cd scripts
chmod +x deploy.sh
./deploy.sh
```

### 4. Access Application

```
http://<PublicIP>
```

---

## 📂 Project Structure

```
zenith-karate-dojo/
├── README.md
├── scripts/
│   └── deploy.sh
├── website/
│   └── index.html
└── docs/
```

---

## 📸 Screenshots

*Add screenshots of your deployed website here*

---
<img width="1331" height="623" alt="vm web server frontend" src="https://github.com/user-attachments/assets/23715bd8-8301-462e-aab6-6a9dc8da1b97" /><img width="1366" height="745" alt="Screenshot 2026-04-02 020625" src="https://github.com/user-attachments/assets/9df752e4-7c25-4821-9f74-33a8f2934806" />


## 💼 Skills Demonstrated

* Cloud Infrastructure Deployment (Azure)
* Linux Server Administration
* Infrastructure Automation (Bash)
* Web Server Configuration (Nginx)
* Application Deployment Workflow

---

## ⚡ Challenges & Solutions

**Challenge:** Deploying a website efficiently on a cloud VM
**Solution:** Automated installation and deployment using a Bash script

**Challenge:** Organizing project files for maintainability
**Solution:** Implemented a clean folder structure separating scripts and web assets

---

## 🚀 Future Improvements

* HTTPS configuration using SSL (Let’s Encrypt)
* Custom domain integration
* CI/CD pipeline (GitHub Actions)
* Monitoring and logging

---

## 🧹 Cleanup

Delete the Azure resource group after use to avoid unnecessary costs.

---

## 👤 Author

Your Name
Cloud Engineer (Aspiring)
