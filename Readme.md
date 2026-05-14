# 🚀 Containerized Flask Application using Docker, Amazon ECR & Amazon ECS

## 📌 Overview

This project demonstrates how to containerize a Flask application using Docker and deploy it on AWS ECS (Elastic Container Service) with Amazon ECR (Elastic Container Registry).

The application is packaged into a Docker container, pushed to ECR, and deployed using ECS Fargate behind an Application Load Balancer (ALB).

---

# 🧰 AWS Services Used

* Amazon ECR
* Amazon ECS (Fargate)
* Application Load Balancer (ALB)
* Docker

---

# 🏗️ Architecture

```text
Flask App
    ↓
Docker Container
    ↓
Amazon ECR
    ↓
Amazon ECS (Fargate)
    ↓
Application Load Balancer
    ↓
Public Access
```

---

# ⚙️ Features

✅ Flask application containerization
✅ Docker image creation
✅ Amazon ECR image hosting
✅ ECS Fargate deployment
✅ Public access using ALB
✅ Serverless container orchestration

---

# 💻 Flask Application

## 🟢 app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "🚀 Flask App Running on AWS ECS!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

---

# 🐳 Dockerfile

```dockerfile
FROM python:3.10-slim

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["python", "app.py"]
```

---

# 📦 requirements.txt

```text
flask
```

---

# ⚙️ Deployment Workflow

## 1️⃣ Build Docker Image

```bash
docker build -t flask-app .
```

---

## 2️⃣ Run Container Locally

```bash
docker run -p 5000:5000 flask-app
```

---

## 3️⃣ Push Image to Amazon ECR

```bash
docker tag flask-app:latest <account-id>.dkr.ecr.ap-south-1.amazonaws.com/flask-app-repo:latest

docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/flask-app-repo:latest
```

---

## 4️⃣ Deploy on ECS

* Create ECS Cluster
* Create Task Definition
* Create ECS Service
* Attach Application Load Balancer

---

# 📸 Screenshots

## 🔹 Flask App Running Locally

![Local Flask App](Screenshots/Screenshot%202026-04-27%20112657.png)

---

## 🔹 Docker Container Running

![Docker Running](Screenshots/Screenshot%202026-04-30%20002310.png)

---

## 🔹 Flask App Running on AWS ECS

![ECS Deployment](Screenshots/Screenshot%202026-04-30%20021631.png)

---

# 📊 Results

✅ Successfully containerized Flask application
✅ Docker image pushed to Amazon ECR
✅ ECS deployment completed successfully
✅ Application accessible publicly using ALB
✅ Implemented cloud-native container workflow

---

# 💡 Key Learnings

* Docker containerization
* ECS Fargate deployment
* Amazon ECR usage
* Container orchestration basics
* Load balancing using ALB

---

# 🚀 Future Improvements

* Add CI/CD pipeline
* Add HTTPS using ACM
* Add ECS Auto Scaling
* Add custom domain
* Infrastructure automation using Terraform

---

# 📂 Project Structure

```text
flask-docker-app/
│── app.py
│── Dockerfile
│── requirements.txt
│── README.md
│── screenshots/
│     ├── Screenshot 2026-04-27 112657.png
│     ├── Screenshot 2026-04-30 002310.png
│     └── Screenshot 2026-04-30 021631.png
```

---

# 🔗 GitHub Commands

```bash
git add .
git commit -m "Containerized Flask Application using Docker and AWS ECS"
git push
```

---

# 🎯 Interview Summary

> Built and deployed a containerized Flask application using Docker, Amazon ECR, and ECS Fargate. Implemented cloud-native deployment with load balancing and container orchestration principles.

---
