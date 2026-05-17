# -complete-docker-course
🐳 Complete Docker Tutorial in Bangla — Beginner to Intermediate with hands-on projects, Docker Compose, networking, volumes, CI/CD, and production best practices.

🐳 Docker সম্পূর্ণ কোর্স (বাংলায়)
Beginner থেকে Intermediate — W3Schools স্টাইলে

---

📋 কোর্সের বিষয়বস্তু (Table of Contents)

🟢 Beginner
1. [Docker কী?](#১-docker-কী)
2. [Docker ইনস্টল করা](#২-docker-ইনস্টল-করা)
3. [Docker-এর মূল ধারণাগুলো](#৩-docker-এর-মূল-ধারণাগুলো)
4. [প্রথম Docker Command](#৪-প্রথম-docker-command)
5. [Docker Image](#৫-docker-image)
6. [Docker Container](#৬-docker-container)
7. [Dockerfile](#৭-dockerfile)
8. [Docker Volume](#৮-docker-volume)
9. [Docker Network](#৯-docker-network)
10. [Docker Compose](#১০-docker-compose)
11. [Docker Hub](#১১-docker-hub)
12. [প্র্যাকটিক্যাল প্রজেক্ট](#১২-প্র্যাকটিক্যাল-প্রজেক্ট)
13. [সাধারণ সমস্যা ও সমাধান](#১৩-সাধারণ-সমস্যা-ও-সমাধান)


🔴 Advanced (Production Level)

14. [Multi-stage Builds](#১৪-multi-stage-builds)
15. [Docker Security](#১৫-docker-security)
16. [Resource Limits](#১৬-resource-limits)
17. [Healthcheck](#১৭-healthcheck)
18. [Docker Private Registry](#১৮-docker-private-registry)
19. [Restart Policies](#১৯-docker-restart-policies)
20. [Bind Mount vs Volume বিস্তারিত](#২০-bind-mount-vs-volume-বিস্তারিত)
21. [Environment Variables বিস্তারিত](#২১-environment-variables-বিস্তারিত)
22. [Docker Logs বিস্তারিত](#২২-docker-logs--বিস্তারিত)
23. [Cleanup Best Practices](#২৩-docker-cleanup-best-practices)
24. [Production Best Practices](#২৪-production-best-practices)
25. [Docker + CI/CD](#২৫-docker--cicd-github-actions)
26. [Kubernetes রোডম্যাপ](#২৬-docker--kubernetes-রোডম্যাপ)


🟣 Expert (Deep Dive)


27. [Docker Architecture Internal](#২৭-docker-architecture-internal)
28. [Container Lifecycle](#২৮-container-lifecycle-জীবনচক্র)
29. [CMD vs ENTRYPOINT গভীর ব্যাখ্যা](#২৯-cmd-vs-entrypoint--গভীর-ব্যাখ্যা)
30. [Layer Caching Optimization](#৩০-docker-layer-caching--build-optimize-করো)
31. [Named Container Best Practice](#৩১-named-container-best-practice)
32. [Foreground vs Detached Mode](#৩২-foreground-vs-detached-mode)
33. [Production Stack Architecture](#৩৩-production-stack--real-world-architecture)
34. [Docker Compose Advanced](#৩৪-docker-compose-advanced-best-practices)
35. [Advanced Security](#৩৫-advanced-security)
36. [Container Monitoring](#৩৬-container-monitoring)
37. [Backup & Restore](#৩৭-docker-backup--restore)
38. [VPS Deployment](#৩৮-vps-এ-deployment)
39. [Beginner Common Mistakes](#৩৯-beginner-দের-সাধারণ-ভুল)
40. [Capstone Project](#৪০-final-capstone-project--portfolio-ready)

---

 ১. Docker কী?

Docker হলো একটি **open-source platform** যা application-কে **container** এর মধ্যে চালাতে সাহায্য করে।

সহজ ভাষায় বুঝি 🧠

কল্পনা করো তুমি একটি রান্না করা খাবার ডেলিভারি দিচ্ছো। খাবারটি যাতে নষ্ট না হয়, তুমি সেটিকে একটি **বাক্সে** ভরে পাঠাও — যেখানে খাবার + তার প্রয়োজনীয় সব উপকরণ আছে।

Docker-ও ঠিক তাই করে — তোমার application + সব dependency একটি **container** এ ভরে দেয়।

### Docker কেন দরকার?

| সমস্যা | Docker ছাড়া | Docker দিয়ে |
|--------|------------|------------|
| "আমার PC তে চলে কিন্তু তোমার চলে না" | 😭 বড় সমস্যা | ✅ সমাধান |
| নতুন server এ setup | ঘণ্টার পর ঘণ্টা | মিনিটে হয়ে যায় |
| Multiple app চালানো | Conflict হয় | আলাদা আলাদা চলে |
| Deployment | কঠিন | সহজ |

### Docker vs Virtual Machine

```
Virtual Machine (VM):          Docker Container:
┌─────────────────┐            ┌───────┐ ┌───────┐
│   App A  App B  │            │ App A │ │ App B │
│ ─────────────── │            │───────│ │───────│
│  Guest OS (2GB) │            │  Libs │ │  Libs │
│ ─────────────── │            └───┬───┘ └───┬───┘
│  Hypervisor     │                │         │
│ ─────────────── │            ┌───┴─────────┴───┐
│  Host OS        │            │   Docker Engine  │
└─────────────────┘            │   Host OS        │
                               └──────────────────┘
❌ ভারী, ধীর, বেশি RAM দরকার    ✅ হালকা, দ্রুত, কম RAM
```

---

## ২. Docker ইনস্টল করা

### Windows এ ইনস্টল

1. [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop) এ যাও
2. **"Download for Windows"** বাটনে ক্লিক করো
3. `.exe` ফাইল ডাউনলোড হলে রান করো
4. Installation শেষে PC restart দাও

### Mac এ ইনস্টল

1. উপরের লিংকে গিয়ে **"Download for Mac"** বেছে নাও
2. `.dmg` ফাইল ডাউনলোড করো
3. ইনস্টল করো এবং Docker Desktop চালু করো

### Linux (Ubuntu) এ ইনস্টল

```bash
# পুরনো version সরাও
sudo apt remove docker docker-engine docker.io

# Docker ইনস্টল করো
sudo apt update
sudo apt install docker.io

# Docker চালু করো
sudo systemctl start docker
sudo systemctl enable docker

# Permission দাও (sudo ছাড়া চালাতে)
sudo usermod -aG docker $USER
```

### ইনস্টল সফল কিনা চেক করো

```bash
docker --version
```

**আউটপুট দেখাবে:**
```
Docker version 24.0.5, build ced0996
```

---

## ৩. Docker-এর মূল ধারণাগুলো

Docker বুঝতে হলে এই ৪টি জিনিস জানা দরকার:

### 🖼️ Image
- Application-এর **blueprint** বা ছাঁচ
- Read-only (পরিবর্তন করা যায় না)
- উদাহরণ: `ubuntu`, `nginx`, `python`

### 📦 Container
- Image থেকে তৈরি **চলমান instance**
- Image হলো ক্লাস, Container হলো object
- একটি Image থেকে অনেক Container বানানো যায়

### 📁 Volume
- Container-এর **data সংরক্ষণের** জায়গা
- Container মুছে ফেললেও data থাকে

### 🌐 Network
- Container গুলো একে অপরের সাথে **কথা বলে** যেভাবে

```
Image ──→ Container তৈরি করে
         ├── Volume (data রাখে)
         └── Network (যোগাযোগ করে)
```

---

## ৪. প্রথম Docker Command

### Docker চলছে কিনা দেখো

```bash
docker info
```

### Hello World চালাও

```bash
docker run hello-world
```

**আউটপুট:**
```
Hello from Docker!
This message shows that your installation appears to be working correctly.
...
```

🎉 অভিনন্দন! তুমি প্রথম Docker container চালালে!

### কী হলো পর্দার আড়ালে?

```
তুমি লিখলে: docker run hello-world
                    ↓
Docker খুঁজলো: local এ hello-world image আছে?
                    ↓ (না)
Docker Hub থেকে ডাউনলোড করলো
                    ↓
Image থেকে Container তৈরি করলো
                    ↓
Container চললো এবং message দেখালো
                    ↓
Container বন্ধ হয়ে গেলো
```

---

## ৫. Docker Image

### Image দেখো

```bash
# সব downloaded image দেখো
docker images

# অথবা
docker image ls
```

**আউটপুট:**
```
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
hello-world   latest    9c7a54a9a43c   5 months ago   13.3kB
ubuntu        latest    35a88802559d   2 months ago   78.1MB
```

### Image ডাউনলোড করো (Pull)

```bash
# Ubuntu image নামাও
docker pull ubuntu

# Specific version (tag) দিয়ে
docker pull ubuntu:20.04

# Python নামাও
docker pull python:3.11
```

### Image খোঁজো

```bash
# nginx সম্পর্কিত image খোঁজো
docker search nginx
```

### Image মুছো

```bash
# Image ID দিয়ে মুছো
docker rmi hello-world

# Force করে মুছো
docker rmi -f hello-world

# সব unused image মুছো
docker image prune
```

### Image-এর বিস্তারিত দেখো

```bash
docker inspect ubuntu
```

---

## ৬. Docker Container

### Container চালাও

```bash
# Basic run
docker run ubuntu

# নাম দিয়ে চালাও
docker run --name আমার-container ubuntu

# Interactive mode (bash এ ঢুকতে)
docker run -it ubuntu bash

# Background এ চালাও (detached mode)
docker run -d nginx

# Port mapping সহ
docker run -d -p 8080:80 nginx
```

> **💡 টিপস:** `-it` মানে `-i` (interactive) + `-t` (terminal)

### চলমান Container দেখো

```bash
# শুধু চলমান
docker ps

# সব (বন্ধ সহ)
docker ps -a
```

**আউটপুট:**
```
CONTAINER ID   IMAGE   COMMAND   CREATED   STATUS   PORTS   NAMES
a1b2c3d4e5f6   nginx   ...       ...       Up       ...     my-nginx
```

### Container বন্ধ/চালু করো

```bash
# বন্ধ করো
docker stop container-name

# জোর করে বন্ধ
docker kill container-name

# আবার চালু
docker start container-name

# Restart
docker restart container-name
```

### Container এ ঢুকো

```bash
# চলমান container এ bash চালাও
docker exec -it container-name bash

# বের হতে
exit
```

### Container মুছো

```bash
# একটি মুছো
docker rm container-name

# বন্ধ container সব মুছো
docker container prune

# চলমান container জোর করে মুছো
docker rm -f container-name
```

### Container-এর Log দেখো

```bash
docker logs container-name

# Live log দেখো
docker logs -f container-name
```

### Container-এর তথ্য দেখো

```bash
docker stats container-name
```

---

## ৭. Dockerfile

Dockerfile হলো একটি **text file** যেখানে লেখা থাকে কীভাবে তোমার Image তৈরি হবে।

### সহজ Dockerfile উদাহরণ

```dockerfile
# Base image নাও
FROM ubuntu:20.04

# তৈরিকারকের তথ্য
LABEL maintainer="তোমার নাম"

# Package update করো
RUN apt-get update

# Python ইনস্টল করো
RUN apt-get install -y python3

# কাজের directory সেট করো
WORKDIR /app

# ফাইল কপি করো (local → container)
COPY . .

# Port খোলো
EXPOSE 8000

# Container চালু হলে এই command চলবে
CMD ["python3", "app.py"]
```

### Dockerfile-এর প্রতিটি Command

| Command | কাজ | উদাহরণ |
|---------|-----|---------|
| `FROM` | Base image নির্ধারণ | `FROM python:3.11` |
| `RUN` | Command চালায় | `RUN apt install nginx` |
| `COPY` | ফাইল কপি করে | `COPY app.py /app/` |
| `ADD` | COPY + URL/zip support | `ADD file.tar.gz /app/` |
| `WORKDIR` | Working directory | `WORKDIR /app` |
| `EXPOSE` | Port উন্মুক্ত করে | `EXPOSE 8080` |
| `ENV` | Environment variable | `ENV DB_HOST=localhost` |
| `CMD` | Default command | `CMD ["python", "app.py"]` |
| `ENTRYPOINT` | Container entry point | `ENTRYPOINT ["nginx"]` |
| `ARG` | Build-time variable | `ARG VERSION=1.0` |

### Image Build করো

```bash
# Current directory-র Dockerfile দিয়ে build
docker build -t আমার-app:1.0 .

# নির্দিষ্ট Dockerfile দিয়ে
docker build -f MyDockerfile -t আমার-app .
```

### প্র্যাকটিক্যাল উদাহরণ — Python Flask App

**app.py:**
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "হ্যালো Docker! 🐳"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
```

**requirements.txt:**
```
flask==2.3.0
```

**Dockerfile:**
```dockerfile
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY app.py .

EXPOSE 5000

CMD ["python", "app.py"]
```

**Build ও Run:**
```bash
# Build
docker build -t flask-app .

# Run
docker run -d -p 5000:5000 flask-app

# Browser এ দেখো: http://localhost:5000
```

### .dockerignore ফাইল

Dockerfile-এর মতোই, `.dockerignore` দিয়ে কিছু ফাইল exclude করা যায়:

```
# .dockerignore
__pycache__/
*.pyc
.env
node_modules/
.git/
```

---

## ৮. Docker Volume

Container মুছে গেলে তার data-ও মুছে যায়। **Volume** দিয়ে data টিকিয়ে রাখা যায়।

### Volume তৈরি করো

```bash
# Volume তৈরি
docker volume create আমার-volume

# সব volume দেখো
docker volume ls

# Volume-এর বিস্তারিত
docker volume inspect আমার-volume
```

### Volume ব্যবহার করো

```bash
# Named volume দিয়ে
docker run -d \
  --name my-db \
  -v আমার-volume:/var/lib/mysql \
  mysql:8.0

# Bind Mount (local folder → container)
docker run -d \
  -v /home/user/data:/app/data \
  nginx
```

### Volume মুছো

```bash
# একটি মুছো
docker volume rm আমার-volume

# সব unused volume মুছো
docker volume prune
```

### কখন কী ব্যবহার করবে?

```
Named Volume:     Database data, persistent app data
                  docker run -v mydata:/app/data

Bind Mount:       Development এ code sync করতে
                  docker run -v $(pwd):/app

tmpfs Mount:      Sensitive data (memory তে রাখে)
                  docker run --tmpfs /app/temp
```

---

## ৯. Docker Network

Container গুলো নিজেদের মধ্যে কথা বলতে Network দরকার।

### Network Types

```
bridge:   Default. Container গুলো একই host এ কথা বলে
host:     Container host-এর network ব্যবহার করে
none:     কোনো network নেই
overlay:  Multiple host এ কাজ করে (Swarm এ)
```

### Network তৈরি করো

```bash
# Custom network তৈরি
docker network create আমার-network

# সব network দেখো
docker network ls

# Network-এর বিস্তারিত
docker network inspect আমার-network
```

### Container কে Network এ যোগ করো

```bash
# Run করার সময়
docker run -d \
  --name web \
  --network আমার-network \
  nginx

# পরে যোগ করতে
docker network connect আমার-network container-name
```

### উদাহরণ — Web + Database

```bash
# Network তৈরি
docker network create app-net

# Database চালাও
docker run -d \
  --name db \
  --network app-net \
  -e MYSQL_ROOT_PASSWORD=password \
  mysql:8.0

# Web app চালাও (db নামে database কে চিনবে)
docker run -d \
  --name web \
  --network app-net \
  -p 8080:80 \
  my-web-app
```

---

## ১০. Docker Compose

একাধিক Container একসাথে চালাতে **Docker Compose** ব্যবহার করা হয়।

### docker-compose.yml ফাইল

```yaml
version: '3.8'

services:
  # Web service
  web:
    build: .
    ports:
      - "8080:80"
    depends_on:
      - db
    environment:
      - DB_HOST=db

  # Database service
  db:
    image: mysql:8.0
    volumes:
      - db-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: myapp

  # Redis cache
  redis:
    image: redis:alpine
    ports:
      - "6379:6379"

volumes:
  db-data:
```

### Compose Commands

```bash
# সব service চালু করো
docker compose up

# Background এ চালু
docker compose up -d

# Build করে চালু
docker compose up --build

# বন্ধ করো
docker compose down

# বন্ধ + volume মুছো
docker compose down -v

# Log দেখো
docker compose logs

# Service এর status দেখো
docker compose ps

# একটি নির্দিষ্ট service restart
docker compose restart web
```

### সম্পূর্ণ উদাহরণ — WordPress সাইট

```yaml
version: '3.8'

services:
  wordpress:
    image: wordpress:latest
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: wpuser
      WORDPRESS_DB_PASSWORD: wppassword
      WORDPRESS_DB_NAME: wordpress
    depends_on:
      - db

  db:
    image: mysql:8.0
    volumes:
      - wordpress-db:/var/lib/mysql
    environment:
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wpuser
      MYSQL_PASSWORD: wppassword
      MYSQL_ROOT_PASSWORD: rootpassword

volumes:
  wordpress-db:
```

```bash
# চালাও
docker compose up -d

# Browser এ দেখো: http://localhost:8080
```

---

## ১১. Docker Hub

Docker Hub হলো Docker-এর **official registry** — যেখানে Image রাখা ও শেয়ার করা যায়।

### Account তৈরি করো

[https://hub.docker.com](https://hub.docker.com) এ গিয়ে free account তৈরি করো।

### Login করো

```bash
docker login
# Username ও Password দাও
```

### Image Push করো (আপলোড)

```bash
# Image কে tag করো
docker tag আমার-app username/আমার-app:latest

# Push করো
docker push username/আমার-app:latest
```

### Image Pull করো (ডাউনলোড)

```bash
docker pull username/আমার-app:latest
```

### জনপ্রিয় Official Images

| Image | কাজ |
|-------|-----|
| `ubuntu` | Ubuntu OS |
| `python` | Python runtime |
| `node` | Node.js |
| `nginx` | Web server |
| `mysql` | MySQL database |
| `postgres` | PostgreSQL database |
| `redis` | Cache server |
| `mongo` | MongoDB |

---

## ১২. প্র্যাকটিক্যাল প্রজেক্ট

### প্রজেক্ট ১: Nginx দিয়ে Static Website

**ধাপ ১:** একটি folder তৈরি করো

```bash
mkdir my-website
cd my-website
```

**ধাপ ২:** `index.html` তৈরি করো

```html
<!DOCTYPE html>
<html>
<head><title>আমার Docker সাইট</title></head>
<body>
  <h1>🐳 Docker দিয়ে চলছি!</h1>
  <p>বাংলায় Docker শিখছি।</p>
</body>
</html>
```

**ধাপ ৩:** Run করো

```bash
docker run -d \
  -p 8080:80 \
  -v $(pwd):/usr/share/nginx/html \
  --name my-site \
  nginx
```

**ধাপ ৪:** দেখো `http://localhost:8080`

---

### প্রজেক্ট ২: Python Flask + MySQL

**ফাইল structure:**
```
my-app/
├── app.py
├── requirements.txt
├── Dockerfile
└── docker-compose.yml
```

**app.py:**
```python
from flask import Flask
import mysql.connector
import os

app = Flask(__name__)

@app.route('/')
def home():
    return "Flask + MySQL চলছে! 🎉"

@app.route('/db')
def check_db():
    try:
        conn = mysql.connector.connect(
            host=os.environ.get('DB_HOST', 'db'),
            user='root',
            password='password',
            database='myapp'
        )
        return "Database সংযুক্ত! ✅"
    except:
        return "Database সংযুক্ত হয়নি ❌"

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, debug=True)
```

**requirements.txt:**
```
flask==2.3.0
mysql-connector-python==8.1.0
```

**Dockerfile:**
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY app.py .
EXPOSE 5000
CMD ["python", "app.py"]
```

**docker-compose.yml:**
```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - db
    environment:
      - DB_HOST=db

  db:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: password
      MYSQL_DATABASE: myapp
    volumes:
      - mysql-data:/var/lib/mysql

volumes:
  mysql-data:
```

**চালাও:**
```bash
docker compose up --build
```

---

## ১৩. সাধারণ সমস্যা ও সমাধান

### সমস্যা ১: Port already in use

```bash
# সমস্যা
Error: port is already allocated

# সমাধান: অন্য port ব্যবহার করো
docker run -p 8081:80 nginx
# অথবা পুরনো container বন্ধ করো
docker stop $(docker ps -q)
```

### সমস্যা ২: Permission denied

```bash
# সমস্যা (Linux)
Got permission denied while trying to connect to Docker daemon

# সমাধান
sudo usermod -aG docker $USER
newgrp docker
```

### সমস্যা ৩: Container বন্ধ হয়ে যাচ্ছে

```bash
# Log দেখো কেন বন্ধ হচ্ছে
docker logs container-name

# Exit code দেখো
docker inspect container-name | grep ExitCode
```

### সমস্যা ৪: Image না পাওয়া

```bash
# সমস্যা
Unable to find image 'myimage:latest' locally

# সমাধান: নাম ঠিক আছে কিনা দেখো
docker search myimage
docker pull myimage
```

### সমস্যা ৫: Disk space কম

```bash
# সব unused জিনিস মুছো
docker system prune

# সব মুছো (সাবধানে!)
docker system prune -a --volumes

# কতটুকু জায়গা ব্যবহার হচ্ছে দেখো
docker system df
```

---

## 📌 Quick Reference — সব গুরুত্বপূর্ণ Command

```bash
# === IMAGE ===
docker pull nginx              # Image ডাউনলোড
docker images                  # সব image দেখো
docker rmi nginx               # Image মুছো
docker build -t myapp .        # Image তৈরি করো

# === CONTAINER ===
docker run nginx               # Container চালাও
docker run -d nginx            # Background এ চালাও
docker run -it ubuntu bash     # Interactive mode
docker run -p 8080:80 nginx    # Port map করো
docker ps                      # চলমান container দেখো
docker ps -a                   # সব container দেখো
docker stop mycontainer        # বন্ধ করো
docker start mycontainer       # চালু করো
docker rm mycontainer          # মুছো
docker exec -it mycontainer bash  # ভেতরে ঢুকো
docker logs mycontainer        # Log দেখো

# === VOLUME ===
docker volume create mydata    # Volume তৈরি
docker volume ls               # সব volume দেখো
docker volume rm mydata        # Volume মুছো

# === NETWORK ===
docker network create mynet    # Network তৈরি
docker network ls              # সব network দেখো

# === COMPOSE ===
docker compose up -d           # সব service চালু
docker compose down            # সব বন্ধ
docker compose logs            # Log দেখো
docker compose ps              # Status দেখো

# === SYSTEM ===
docker system prune            # Cleanup
docker system df               # Disk usage
docker info                    # Docker info
```

---

---

# 🚀 Advanced Docker — Production Level

## ১৪. Multi-stage Builds

Production image ছোট ও secure করার জন্য Multi-stage Build ব্যবহার করা হয়।

### ❌ Bad Practice

```dockerfile
FROM golang:1.24
WORKDIR /app
COPY . .
RUN go build -o app .
CMD ["./app"]
```

**সমস্যা:** পুরো Go compiler image production-এ চলে যাচ্ছে → image size বিশাল বড়।

### ✅ Multi-stage Build

```dockerfile
# Build Stage
FROM golang:1.24 AS builder
WORKDIR /app
COPY . .
RUN go build -o app .

# Production Stage (শুধু binary নাও)
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/app .
CMD ["./app"]
```

**সুবিধা:**
- Image অনেক ছোট হয়
- Deployment দ্রুত হয়
- Security ভালো থাকে

---

## ১৫. Docker Security

### Non-root User ব্যবহার করো

```dockerfile
# ❌ Bad — root হিসেবে চলে
FROM ubuntu
CMD ["bash"]

# ✅ Better — আলাদা user তৈরি করো
FROM ubuntu
RUN useradd -m appuser
USER appuser
CMD ["bash"]
```

### Vulnerability Scan করো

```bash
docker scout quickview
```

### Minimal Base Image ব্যবহার করো

| Image | Size | ব্যবহার |
|-------|------|---------|
| `ubuntu` | ~78MB | সাধারণ কাজ |
| `alpine` | ~5MB | Production recommended |
| `distroless` | ~2MB | Maximum security |

> **💡 টিপস:** Production এ সবসময় `alpine` বা `distroless` ব্যবহার করো।

---

## ১৬. Resource Limits

Production-এ Container-কে সীমার মধ্যে রাখা জরুরি — নইলে একটি container সব resource খেয়ে ফেলতে পারে।

```bash
docker run \
  --memory="512m" \
  --cpus="1" \
  nginx
```

Docker Compose এ:

```yaml
services:
  web:
    image: nginx
    deploy:
      resources:
        limits:
          memory: 512m
          cpus: '1.0'
```

---

## ১৭. Healthcheck

Container চলছে মানেই healthy নয়। Healthcheck দিয়ে নিশ্চিত করো সব ঠিকঠাক আছে।

**Dockerfile এ:**
```dockerfile
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
  CMD curl --fail http://localhost:8080/health || exit 1
```

**Status দেখো:**
```bash
docker ps
# STATUS কলামে: healthy / unhealthy / starting
```

**Docker Compose এ:**
```yaml
services:
  web:
    image: nginx
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost"]
      interval: 30s
      timeout: 10s
      retries: 3
```

---

## ১৮. Docker Private Registry

নিজের company বা project-এর জন্য নিজস্ব registry চালানো যায়।

### Local Registry চালাও

```bash
docker run -d -p 5000:5000 --name registry registry:2
```

### Image Push করো Local Registry তে

```bash
# Tag করো
docker tag myapp localhost:5000/myapp

# Push করো
docker push localhost:5000/myapp

# Pull করো
docker pull localhost:5000/myapp
```

---

## ১৯. Docker Restart Policies

Container crash করলে automatically restart করার নিয়ম।

```bash
docker run -d \
  --restart always \
  nginx
```

| Policy | কাজ |
|--------|-----|
| `no` | Restart করবে না (default) |
| `always` | সবসময় restart করবে |
| `unless-stopped` | manually stop না করলে restart করবে |
| `on-failure` | শুধু error এ restart করবে |

---

## ২০. Bind Mount vs Volume (বিস্তারিত)

| Feature | Bind Mount | Volume |
|---------|-----------|--------|
| Host এর উপর নির্ভর | হ্যাঁ | না |
| Backup সহজ | মাঝারি | সহজ |
| Development এ | দারুণ | ভালো |
| Production এ | কম পছন্দনীয় | **Recommended** |

```bash
# Bind Mount — local folder সরাসরি map
docker run -v $(pwd)/code:/app nginx

# Named Volume — Docker নিজে manage করে
docker run -v mydata:/app/data nginx
```

---

## ২১. Environment Variables (বিস্তারিত)

### Run করার সময়

```bash
docker run -e DB_HOST=localhost -e DB_PORT=3306 nginx
```

### .env ফাইল থেকে

```bash
# .env ফাইল
DB_HOST=localhost
DB_PORT=3306

# চালাও
docker run --env-file .env nginx
```

### Dockerfile এ

```dockerfile
ENV APP_ENV=production
ENV PORT=8080
```

### Docker Compose এ

```yaml
services:
  web:
    image: myapp
    environment:
      - DB_HOST=db
      - APP_ENV=production
    env_file:
      - .env
```

---

## ২২. Docker Logs — বিস্তারিত

```bash
# শেষ ৫০ লাইন
docker logs --tail 50 container-name

# Live stream (real-time দেখো)
docker logs -f container-name

# Timestamp সহ
docker logs -t container-name

# নির্দিষ্ট সময়ের পর থেকে
docker logs --since 2024-01-01T00:00:00 container-name

# সব একসাথে
docker logs -f -t --tail 100 container-name
```

---

## ২৩. Docker Cleanup Best Practices

```bash
# বন্ধ container মুছো
docker container prune

# Unused image মুছো
docker image prune -a

# Unused volume মুছো
docker volume prune

# সব একসাথে (সাবধানে!)
docker system prune -a --volumes

# কতটুকু জায়গা ব্যবহার হচ্ছে
docker system df
```

---

## ২৪. Production Best Practices

### ✅ Specific Tag ব্যবহার করো

```dockerfile
# ❌ Bad — কোন version জানা নেই
FROM node:latest

# ✅ Good — নির্দিষ্ট version
FROM node:20-alpine
```

### ✅ .dockerignore অবশ্যই রাখো

```
node_modules/
.git/
.env
*.log
tmp/
__pycache__/
```

### ✅ One Process Per Container

```
✅ ভালো:            ❌ খারাপ:
app container       সব একসাথে
db container        একটি container এ
redis container     সব চালানো
```

### ✅ Layer Cache ব্যবহার করো

```dockerfile
# ✅ Dependency আগে copy করো (cache কাজে লাগবে)
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .   # code পরে copy (বেশি বদলায়)
```

---

## ২৫. Docker + CI/CD (GitHub Actions)

Code push করলে automatically Docker image build হবে।

```yaml
# .github/workflows/docker.yml
name: Docker Build & Deploy

on:
  push:
    branches:
      - main

jobs:
  docker:
    runs-on: ubuntu-latest

    steps:
      - name: Code নামাও
        uses: actions/checkout@v4

      - name: Docker Hub এ Login
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Image Build করো
        run: docker build -t myusername/myapp:latest .

      - name: Test চালাও
        run: docker run myusername/myapp:latest

      - name: Docker Hub এ Push করো
        run: docker push myusername/myapp:latest
```

---

## ২৬. Docker → Kubernetes রোডম্যাপ

Docker শেখার পর Kubernetes শেখাটাই স্বাভাবিক পরবর্তী ধাপ।

```
Docker Basics
    ↓
Docker Compose (multi-container)
    ↓
Kubernetes Pods (container group)
    ↓
Deployments (scaling & updates)
    ↓
Services (networking)
    ↓
Ingress (external traffic)
    ↓
Helm (package manager)
```

---

## 🧠 Interview প্রশ্ন ও উত্তর

### Beginner Level

**প্রশ্ন: Docker কী?**
> Container তৈরি, চালানো ও manage করার একটি open-source platform।

**প্রশ্ন: Image vs Container পার্থক্য কী?**
> Image = blueprint (read-only ছাঁচ), Container = সেই blueprint থেকে তৈরি চলমান instance।

**প্রশ্ন: Volume কেন দরকার?**
> Container মুছে গেলেও data টিকিয়ে রাখতে।

**প্রশ্ন: Port Mapping কী?**
> Host-এর port কে Container-এর port এর সাথে সংযুক্ত করা। যেমন: `-p 8080:80`।

### Intermediate Level

**প্রশ্ন: CMD vs ENTRYPOINT পার্থক্য?**
> `CMD` — default argument দেয়, override করা যায়। `ENTRYPOINT` — fixed executable, সবসময় চলে।

**প্রশ্ন: Multi-stage build কেন ব্যবহার করি?**
> Build tool ছাড়া শুধু compiled output দিয়ে ছোট ও secure production image তৈরি করতে।

**প্রশ্ন: `docker run` vs `docker exec` পার্থক্য?**
> `docker run` — নতুন container তৈরি করে চালায়। `docker exec` — চলমান container এ command চালায়।

---

## 🛠️ Real DevOps Practice Tasks

| Task | কী করতে হবে | কঠিনতা |
|------|------------|--------|
| **Task 1** | Nginx দিয়ে static website deploy করো | ⭐ |
| **Task 2** | Python Flask API containerize করো | ⭐⭐ |
| **Task 3** | Docker Compose দিয়ে Backend + PostgreSQL + Redis চালাও | ⭐⭐⭐ |
| **Task 4** | Multi-stage build দিয়ে Go app optimize করো | ⭐⭐⭐ |
| **Task 5** | GitHub Actions দিয়ে automatic Docker build + push করো | ⭐⭐⭐⭐ |

---

---

# 🏗️ Expert Level — Deep Dive Sections

## ২৭. Docker Architecture (Internal)

Docker কীভাবে কাজ করে তা বুঝলে debug ও optimize করা অনেক সহজ হয়।

```
তুমি টাইপ করলে: docker run nginx
         ↓
┌─────────────────────────────────────┐
│         Docker CLI (Client)         │  ← তুমি এখানে command দাও
└──────────────┬──────────────────────┘
               │ REST API (Unix socket)
               ↓
┌─────────────────────────────────────┐
│       Docker Daemon (dockerd)       │  ← আসল কাজ এখানে হয়
│  - Image manage করে                │
│  - Container তৈরি করে             │
│  - Network/Volume manage করে       │
└──────────────┬──────────────────────┘
               │
       ┌───────┴───────┐
       ↓               ↓
┌──────────┐    ┌──────────────┐
│  Local   │    │  Docker Hub  │
│  Images  │    │  (Registry)  │
└──────────┘    └──────────────┘
```

### মূল Components

| Component | কাজ |
|-----------|-----|
| **Docker Client** | তুমি command দাও এখানে (`docker run`, `docker build`) |
| **Docker Daemon** | Client-এর instruction পালন করে |
| **Docker Engine** | Client + Daemon একসাথে |
| **Registry** | Image storage (Docker Hub, private registry) |
| **containerd** | Low-level container runtime |
| **runc** | সবচেয়ে নিচের layer — OS kernel কে বলে container তৈরি করতে |

---

## ২৮. Container Lifecycle (জীবনচক্র)

```
         docker create
              ↓
        ┌─────────┐
        │ Created │
        └────┬────┘
             │ docker start
             ↓
        ┌─────────┐◄──── docker unpause ────┐
        │ Running │                          │
        └────┬────┘──── docker pause ───►┌──────┐
             │                           │Paused│
             │ docker stop               └──────┘
             ↓
        ┌─────────┐
        │ Stopped │
        └────┬────┘
             │ docker rm
             ↓
        ┌─────────┐
        │ Removed │
        └─────────┘
```

### Commands

```bash
docker create nginx          # তৈরি করো (চালু না)
docker start my-container    # চালু করো
docker pause my-container    # সাময়িক থামাও
docker unpause my-container  # আবার চালু করো
docker stop my-container     # gracefully বন্ধ করো
docker kill my-container     # জোর করে বন্ধ করো
docker rm my-container       # মুছে ফেলো
```

---

## ২৯. CMD vs ENTRYPOINT — গভীর ব্যাখ্যা

এটি interview-এ সবচেয়ে বেশি জিজ্ঞেস করা হয়।

### CMD — Override করা যায়

```dockerfile
FROM python:3.11
CMD ["python", "app.py"]
```

```bash
# Default: python app.py চলবে
docker run myapp

# Override: python test.py চলবে
docker run myapp python test.py
```

### ENTRYPOINT — Fixed থাকে

```dockerfile
FROM python:3.11
ENTRYPOINT ["python"]
CMD ["app.py"]   # default argument
```

```bash
# python app.py চলবে
docker run myapp

# python test.py চলবে (শুধু argument বদলায়)
docker run myapp test.py
```

### তুলনা

| | CMD | ENTRYPOINT |
|-|-----|-----------|
| Override হয়? | সম্পূর্ণ | না (শুধু argument) |
| ব্যবহার | Default command | Fixed executable |
| কখন ব্যবহার | Flexible scripts | Dedicated tools |

---

## ৩০. Docker Layer Caching — Build Optimize করো

প্রতিটি Dockerfile instruction একটি **layer** তৈরি করে। Layer cache হলে build অনেক দ্রুত হয়।

### ❌ Slow Build (Cache কাজে লাগে না)

```dockerfile
FROM python:3.11
COPY . .                          # সব copy হয় আগে
RUN pip install -r requirements.txt  # code বদলালেই এটাও re-run হয়
```

### ✅ Fast Build (Cache কাজে লাগে)

```dockerfile
FROM python:3.11
COPY requirements.txt .           # dependency আগে copy
RUN pip install -r requirements.txt  # cache হয়ে থাকে
COPY . .                          # শুধু code পরে copy
```

**নিয়ম:** যে জিনিস কম বদলায়, সেটি আগে রাখো।

```
Layer 1: FROM python:3.11       ← খুব কম বদলায় → ✅ cache
Layer 2: COPY requirements.txt  ← মাঝেমধ্যে বদলায় → ✅ cache
Layer 3: RUN pip install        ← requirements বদলালে → re-run
Layer 4: COPY . .               ← সবচেয়ে বেশি বদলায় → always re-run
```

---

## ৩১. Named Container Best Practice

```bash
# ❌ Bad — random নাম (debug কঠিন)
docker run nginx
# Container নাম: romantic_einstein 😵

# ✅ Good — নিজে নাম দাও
docker run --name web-server nginx
docker run --name api-backend python-app
docker run --name postgres-db postgres
```

**সুবিধা:**
- `docker logs web-server` — সহজে log দেখা যায়
- `docker stop api-backend` — সহজে বন্ধ করা যায়
- Compose এ service নামে reference করা যায়

---

## ৩২. Foreground vs Detached Mode

```bash
# Foreground — terminal আটকে যায়
docker run nginx
# Ctrl+C দিলে container বন্ধ হয়

# Detached — background এ চলে
docker run -d nginx
# Terminal free থাকে, container চলতে থাকে

# Attach করতে চাইলে
docker attach container-name

# Log দেখতে চাইলে (attach না করে)
docker logs -f container-name
```

---

## ৩৩. Production Stack — Real World Architecture

বাস্তব production এ এভাবে সব চলে:

```
Internet
    ↓
┌─────────────┐
│    NGINX    │  ← Reverse Proxy + SSL
│  (Port 443) │
└──────┬──────┘
       ↓
┌─────────────┐
│ Backend API │  ← Flask/Node/Django
│  (Port 5000)│
└──────┬──────┘
   ┌───┴────┐
   ↓        ↓
┌──────┐ ┌──────────┐
│Redis │ │PostgreSQL│
│Cache │ │Database  │
└──────┘ └──────────┘
```

### সম্পূর্ণ docker-compose.yml

```yaml
version: '3.8'

services:
  nginx:
    image: nginx:alpine
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
      - ./ssl:/etc/ssl
    depends_on:
      - api
    restart: unless-stopped

  api:
    build: ./backend
    environment:
      - DB_HOST=postgres
      - REDIS_HOST=redis
      - APP_ENV=production
    depends_on:
      postgres:
        condition: service_healthy
      redis:
        condition: service_started
    restart: unless-stopped

  postgres:
    image: postgres:16-alpine
    volumes:
      - pg-data:/var/lib/postgresql/data
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user"]
      interval: 10s
      timeout: 5s
      retries: 5
    restart: unless-stopped

  redis:
    image: redis:7-alpine
    volumes:
      - redis-data:/data
    restart: unless-stopped

volumes:
  pg-data:
  redis-data:

networks:
  default:
    name: app-network
```

---

## ৩৪. Docker Compose Advanced Best Practices

### .env ফাইল ব্যবহার করো

```bash
# .env ফাইল
DB_PASSWORD=supersecret123
APP_SECRET=myappsecret
DOMAIN=myapp.com
```

```yaml
# docker-compose.yml এ
environment:
  - DB_PASSWORD=${DB_PASSWORD}
```

### depends_on এর সীমাবদ্ধতা

```yaml
# ❌ এটি শুধু container start হওয়া দেখে, ready কিনা দেখে না
depends_on:
  - db

# ✅ healthcheck দিয়ে নিশ্চিত করো DB ready
depends_on:
  db:
    condition: service_healthy
```

---

## ৩৫. Advanced Security

### Read-only Filesystem

```bash
# Container filesystem read-only করো
docker run --read-only nginx

# নির্দিষ্ট folder লেখার অনুমতি দাও
docker run \
  --read-only \
  --tmpfs /tmp \
  nginx
```

### Capabilities কমাও

```bash
# সব capability বাদ দাও, শুধু দরকারিটা রাখো
docker run \
  --cap-drop ALL \
  --cap-add NET_BIND_SERVICE \
  nginx
```

### Docker Secrets (Compose)

```yaml
services:
  db:
    image: postgres
    secrets:
      - db_password
    environment:
      POSTGRES_PASSWORD_FILE: /run/secrets/db_password

secrets:
  db_password:
    file: ./secrets/db_password.txt
```

---

## ৩৬. Container Monitoring

### Basic Monitoring

```bash
# সব container-এর resource usage
docker stats

# নির্দিষ্ট container
docker stats web-server

# একবার দেখাও (live নয়)
docker stats --no-stream
```

### Advanced Monitoring Stack (Prometheus + Grafana)

```yaml
version: '3.8'

services:
  cadvisor:
    image: gcr.io/cadvisor/cadvisor:latest
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - /sys:/sys
      - /var/lib/docker/:/var/lib/docker/
    ports:
      - "8081:8080"

  prometheus:
    image: prom/prometheus:latest
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"

  grafana:
    image: grafana/grafana:latest
    ports:
      - "3000:3000"
    volumes:
      - grafana-data:/var/lib/grafana

volumes:
  grafana-data:
```

**Access:**
- cAdvisor: `http://localhost:8081`
- Prometheus: `http://localhost:9090`
- Grafana: `http://localhost:3000`

---

## ৩৭. Docker Backup & Restore

### Volume Backup করো

```bash
# Volume backup করো tar ফাইলে
docker run --rm \
  -v myvolume:/data \
  -v $(pwd):/backup \
  ubuntu tar czf /backup/backup.tar.gz /data

# Restore করো
docker run --rm \
  -v myvolume:/data \
  -v $(pwd):/backup \
  ubuntu tar xzf /backup/backup.tar.gz -C /
```

### Database Backup করো

```bash
# PostgreSQL backup
docker exec postgres-container \
  pg_dump -U user mydb > backup.sql

# Restore
docker exec -i postgres-container \
  psql -U user mydb < backup.sql

# MySQL backup
docker exec mysql-container \
  mysqldump -u root -p mydb > backup.sql
```

### Image Export/Import করো

```bash
# Image save করো (offline transfer)
docker save myapp:latest | gzip > myapp.tar.gz

# Load করো
docker load < myapp.tar.gz
```

---

## ৩৮. VPS এ Deployment

### ধাপ ১: VPS তে Docker ইনস্টল করো

```bash
ssh user@your-server-ip
sudo apt update && sudo apt install docker.io docker-compose -y
sudo usermod -aG docker $USER
```

### ধাপ ২: Code পাঠাও

```bash
# Git দিয়ে
git clone https://github.com/yourname/myapp.git
cd myapp

# অথবা scp দিয়ে
scp -r ./myapp user@server-ip:/home/user/
```

### ধাপ ৩: চালাও

```bash
docker compose up -d --build
```

### ধাপ ৪: NGINX দিয়ে Domain Setup

```nginx
# /etc/nginx/sites-available/myapp
server {
    listen 80;
    server_name myapp.com www.myapp.com;

    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

### ধাপ ৫: SSL (HTTPS) যোগ করো

```bash
sudo apt install certbot python3-certbot-nginx
sudo certbot --nginx -d myapp.com
```

---

## ৩৯. Beginner-দের সাধারণ ভুল

### ভুল ১: COPY order ঠিক না রাখা

```dockerfile
# ❌ Bad — সবসময় pip install re-run হবে
COPY . .
RUN pip install -r requirements.txt

# ✅ Good — dependency cache হবে
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
```

### ভুল ২: latest tag ব্যবহার করা

```dockerfile
# ❌ Bad — কোন version জানা নেই, break হতে পারে
FROM node:latest

# ✅ Good — version নির্দিষ্ট
FROM node:20.11-alpine
```

### ভুল ৩: Secret .env কে image এ ঢোকানো

```dockerfile
# ❌ Bad — secret image এ চলে যাবে!
COPY .env .

# ✅ Good — runtime এ environment variable দাও
# docker run -e DB_PASSWORD=xxx myapp
# অথবা docker-compose এ env_file ব্যবহার করো
```

### ভুল ৪: Root user হিসেবে চালানো

```dockerfile
# ❌ Bad
FROM ubuntu
CMD ["myapp"]

# ✅ Good
FROM ubuntu
RUN useradd -m appuser
USER appuser
CMD ["myapp"]
```

### ভুল ৫: .dockerignore না রাখা

```
# ❌ node_modules (1GB+) image এ ঢুকে যায়!

# ✅ .dockerignore ফাইল রাখো:
node_modules/
.git/
.env
*.log
__pycache__/
.pytest_cache/
```

---

## ৪০. Final Capstone Project — Portfolio-Ready

এই project complete করলে তুমি **DevOps Junior** হিসেবে job apply করতে পারবে।

### Stack
- **Frontend:** React (Nginx দিয়ে serve)
- **Backend:** Python FastAPI
- **Database:** PostgreSQL
- **Cache:** Redis
- **Reverse Proxy:** Nginx
- **CI/CD:** GitHub Actions
- **Deployment:** VPS

### Project Structure

```
capstone-project/
├── frontend/
│   ├── src/
│   ├── Dockerfile
│   └── nginx.conf
├── backend/
│   ├── main.py
│   ├── requirements.txt
│   └── Dockerfile
├── nginx/
│   └── nginx.conf
├── .github/
│   └── workflows/
│       └── deploy.yml
├── docker-compose.yml
├── docker-compose.prod.yml
└── .env.example
```

### docker-compose.prod.yml

```yaml
version: '3.8'

services:
  frontend:
    build: ./frontend
    restart: unless-stopped

  backend:
    build: ./backend
    environment:
      - DATABASE_URL=postgresql://user:${DB_PASS}@postgres/myapp
      - REDIS_URL=redis://redis:6379
    depends_on:
      postgres:
        condition: service_healthy
    restart: unless-stopped

  postgres:
    image: postgres:16-alpine
    volumes:
      - pg-data:/var/lib/postgresql/data
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: ${DB_PASS}
      POSTGRES_DB: myapp
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U user"]
      interval: 10s
      retries: 5
    restart: unless-stopped

  redis:
    image: redis:7-alpine
    volumes:
      - redis-data:/data
    restart: unless-stopped

  nginx:
    image: nginx:alpine
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - frontend
      - backend
    restart: unless-stopped

volumes:
  pg-data:
  redis-data:
```

### GitHub Actions Deploy

```yaml
# .github/workflows/deploy.yml
name: Build & Deploy

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Docker Hub Login
        uses: docker/login-action@v3
        with:
          username: ${{ secrets.DOCKERHUB_USER }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}

      - name: Build & Push Images
        run: |
          docker build -t ${{ secrets.DOCKERHUB_USER }}/myapp-backend ./backend
          docker build -t ${{ secrets.DOCKERHUB_USER }}/myapp-frontend ./frontend
          docker push ${{ secrets.DOCKERHUB_USER }}/myapp-backend
          docker push ${{ secrets.DOCKERHUB_USER }}/myapp-frontend

      - name: Deploy to VPS
        uses: appleboy/ssh-action@master
        with:
          host: ${{ secrets.VPS_HOST }}
          username: ${{ secrets.VPS_USER }}
          key: ${{ secrets.VPS_SSH_KEY }}
          script: |
            cd /home/user/myapp
            docker compose -f docker-compose.prod.yml pull
            docker compose -f docker-compose.prod.yml up -d --build
```

---

## 🎯 কোর্স শেষে তুমি পারবে

✅ Production-ready Dockerfile লিখতে  
✅ Multi-container app Docker Compose দিয়ে চালাতে  
✅ Persistent storage সঠিকভাবে manage করতে  
✅ Container debug ও monitor করতে  
✅ CI/CD pipeline এ Docker integrate করতে  
✅ Security best practices follow করতে  
✅ Real VPS এ application deploy করতে  
✅ Container monitoring setup করতে  
✅ Database backup ও restore করতে  
✅ Kubernetes শেখার জন্য সম্পূর্ণ ready হতে  

---

## 📚 Best Learning Resources

- 📖 [Docker Official Docs](https://docs.docker.com)
- 🐳 [Docker Hub](https://hub.docker.com)
- 🧪 [Play With Docker](https://labs.play-with-docker.com) *(Browser এই practice করো!)*
- ⭐ [Awesome Docker GitHub](https://github.com/veggiemonk/awesome-docker)
- ☸️ [Kubernetes Docs](https://kubernetes.io/docs/home)

---

> 🐳 **মনে রেখো:** Docker শেখার সবচেয়ে ভালো উপায় হলো বেশি বেশি practice করা। ভুল হলে ভয় পেও না — container মুছে আবার শুরু করো!

**শুভকামনা! 🚀**
