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
#!/bin/bash
# Update system and install Nginx [cite: 9, 10]
sudo apt-get update -y
sudo apt-get install -y nginx

# Configure Firewall [cite: 11, 12]
sudo ufw allow 'Nginx Full'
sudo ufw --force enable 

# Deploy the Styled Website [cite: 13-68]
sudo tee /var/www/html/index.html > /dev/null <<EOF
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zenith Karate Dojo</title>
    <style>
        * { margin:0; padding:0; box-sizing: border-box; }
        body { font-family: 'Segoe UI', sans-serif; background: #0d0d0d; color: white; }
        nav { background: #000; padding: 15px 40px; display: flex; justify-content: space-between; }
        nav h2 { color: #e63946; }
        nav ul { display: flex; gap: 20px; list-style: none; }
        .hero {
            height: 90vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)),
            url('https://images.unsplash.com/photo-1555597673-b21d5c935865');
            background-size: cover;
        }
        .hero h1 { font-size: 3rem; color: #e63946; }
        section { padding: 60px; text-align: center; }
        .grid { display: flex; flex-wrap: wrap; gap: 20px; justify-content: center; }
        .card { background: #1a1a1a; padding: 20px; border-radius: 10px; width: 260px; }
        footer { background: #000; text-align: center; padding: 20px; }
    </style>
</head>
<body>
    <nav>
        <h2>Zenith Dojo</h2>
        <ul>
            <li>Home</li>
            <li>Classes</li>
            <li>Instructors</li>
            <li>Contact</li>
        </ul>
    </nav>
    <div class="hero">
        <h1>Zenith Karate Dojo</h1>
        <p>Discipline. Strength. Honor.</p>
    </div>
    <section>
        <h2>Classes</h2>
        <div class="grid">
            <div class="card">Beginner Training</div>
            <div class="card">Intermediate Training</div>
            <div class="card">Advanced Training</div>
        </div>
    </section>
    <section>
        <h2>Join Us</h2>
        <p>Start your martial arts journey today.</p>
    </section>
    <footer>
        <p>© 2026 Zenith Karate Dojo</p>
    </footer>
</body>
</html>
EOF

# Enable and Restart Nginx [cite: 70, 71]
sudo systemctl enable nginx
sudo systemctl restart nginx

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
