# 🚀 Cloud + Docker + NGINX | Static Website Hosting

A hands-on DevOps beginner project to host a **static website** on a **cloud virtual machine** using **Docker** and **NGINX**.

---

## 📌 Project Overview

This project demonstrates how to deploy a static website using Docker containers on a cloud VM (AWS / GCP / Azure).

---

## 🛠️ Tech Stack

- Cloud: AWS / GCP / Azure
- OS: Ubuntu 24.04 LTS
- Container: Docker
- Web Server: NGINX
- Website: Static HTML/CSS

---

## 🧱 Architecture


---

## 🔹 Step 1: Create Cloud VM

- Create free-tier account (AWS / GCP / Azure)
- Launch Ubuntu 24.04 VM
- Configure:
  - 1–2 vCPU
  - 2–4 GB RAM
  - Allow ports:
    - SSH (22)
    - HTTP (80)

---

## 🔹 Step 2: Connect to VM

```bash
ssh username@<PUBLIC_IP>
sudo apt update && sudo apt upgrade -y

##🔹 Step 3: Install Docker
sudo apt install docker.io -y
sudo systemctl start docker
sudo systemctl enable docker
docker --version
🔹 Step 4: Download Website Template
Template used:

2153_fireworks_composer

Source: https://lnkd.in/dDbT3HPK
unzip 2153_fireworks_composer.zip
mkdir website
mv 2153_fireworks_composer/* website/
🔹 Step 5: Run NGINX Container
docker run -d \
  --name nginx-website \
  -p 80:80 \
  -v $(pwd)/website:/usr/share/nginx/html \
  nginx

docker ps
🔹 Step 6: Verify Website
Open browser:
http://<VM_PUBLIC_IP>:80
✅ Website successfully live using Docker + NGINX
