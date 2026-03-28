# 🚀 Django + Docker + AWS Deployment

![Django](https://img.shields.io/badge/Django-Framework-green)
![Docker](https://img.shields.io/badge/Docker-Container-blue)
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Python](https://img.shields.io/badge/Python-3.12-blue)
![Status](https://img.shields.io/badge/Status-Live-success)

A complete end-to-end project demonstrating how to build, containerize, and deploy a Django web application on AWS EC2 using Docker, with version control via GitHub.

---

## 🧠 Overview

This project implements a full DevOps workflow:

- Develop a Django web application  
- Containerize using Docker  
- Deploy on AWS EC2  
- Manage code with GitHub  

The system ensures **portability, scalability, and reproducibility**.

---

## 🌍 Live Demo

```
http://43.205.177.247:8000
```

---

## 🏗️ Architecture

```
User (Browser)
     ↓
Public IP (AWS EC2)
     ↓
Docker Container
     ↓
Django Application
     ↓
HTML Templates
```

---


## 📁 Project Structure

```
project/
 ├── core/              # Django project settings
 ├── app/               # Application logic
 ├── templates/         # HTML templates
 │    └── index.html
 ├── Dockerfile         # Container configuration
 ├── requirements.txt   # Dependencies
 ├── manage.py          # Django CLI entry point
 ├── db.sqlite3         # Development database
 └── .gitignore         # Ignored files
```

---

## ⚙️ Local Setup

### 1. Clone Repository

```
git clone https://github.com/<guruansh03>/django-docker-aws-app.git
cd <repo-name>
```

### 2. Create Virtual Environment

```
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### 4. Run Django

```
python manage.py migrate
python manage.py runserver
```

Open:

```
http://127.0.0.1:8000
```

---

## 🐳 Docker Setup

### Build Image

```
docker build -t django-app .
```

### Run Container

```
docker run -d -p 8000:8000 django-app
```

### Run with Auto-Restart (Recommended)

```
docker run -d -p 8000:8000 --restart always django-app
```

---

## ☁️ AWS Deployment

### Steps

1. Launch EC2 instance (Ubuntu)  
2. Configure Security Group:  
   - Port 22 → SSH  
   - Port 8000 → Application  

3. Connect to server:

```
ssh -i your-key.pem ubuntu@<public-ip>
```

4. Install Docker:

```
sudo apt update
sudo apt install docker.io -y
```

5. Run container:

```
docker run -d -p 8000:8000 django-app
```

---

## 🔐 GitHub Authentication Fix

If you face a `403 error` while pushing:

- Generate a **Personal Access Token (PAT)**  
- Use it as password instead of your GitHub password  

---

## 🧹 .gitignore

```
venv/
__pycache__/
*.pyc
db.sqlite3
.env
```

---

## 🧠 Key Concepts

- **Django** → Backend framework  
- **Docker** → Containerization  
- **AWS EC2** → Cloud hosting  
- **Port Mapping** → External access to container  

---

## 🎯 Features

- Dockerized Django application  
- Deployed on AWS EC2  
- Publicly accessible via IP  
- Clean project structure  
- Git-based version control  

---

## 🖥️ Run Using Docker Desktop (Local Testing)

You can also run this project locally using Docker Desktop without manual commands.

### Steps:

1. Install and open Docker Desktop  
2. Ensure Docker Engine is running  

---

### Option 1: Using Docker Hub (Recommended)

Pull the image:

```
docker pull guruansh03/django-app
```

Run the container:

```
docker run -d -p 8000:8000 guruansh03/django-app
```

Open in browser:

```
http://localhost:8000
```

---

### Option 2: Using Docker Desktop UI

1. Open Docker Desktop  
2. Go to **Docker Hub** tab  
3. Search: `guruansh03/django-app`  
4. Click **Run**  

---

### Verify Container

Run:

```
docker ps
```

You should see a running container with port mapping:

```
8000 -> 8000
```

---

### Notes

- If port 8000 is already in use:

```
docker run -d -p 8001:8000 guruansh03/django-app
```

Then open:

```
http://localhost:8001
```

- Make sure Docker Desktop shows **Engine Running**

---

### Why This Matters

This ensures the project is:

- Portable  
- Reproducible  
- Easy to run on any system  

This is how evaluators or recruiters can test the project without setup.

---

## 👨‍💻 Author

**Guruansh Singh**

---


---

## ⭐ Support

If you found this helpful, consider giving a ⭐ to the repository!
