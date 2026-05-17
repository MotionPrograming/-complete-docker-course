# 🐳 Docker সম্পূর্ণ কোর্স (বাংলায়)

**Beginner থেকে Advanced — Production-Ready Skills**

<div align="center">

![Docker Badge](https://img.shields.io/badge/Docker-Complete-2496ED?style=for-the-badge&logo=docker)
![Bengali](https://img.shields.io/badge/Language-Bengali-FF7700?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Comprehensive-success?style=for-the-badge)

</div>

---

## 📚 Table of Contents

### 🟢 **Beginner Level** (ভিত্তি শেখা)

1. [Docker কী এবং কেন?](#-১-docker-কী-এবং-কেন)
2. [Docker ইনস্টল করা](#-২-docker-ইনস্টল-করা)
3. [Docker এর মূল ধারণা](#-৩-docker-এর-মূল-ধারণা)
4. [প্রথম Docker Command](#-৪-প্রথম-docker-command)
5. [Docker Image](#-৫-docker-image)
6. [Docker Container](#-৬-docker-container)
7. [Dockerfile লেখা](#-৭-dockerfile-লেখা)
8. [Docker Volume](#-৮-docker-volume)
9. [Docker Network](#-৯-docker-network)
10. [Docker Compose](#-১০-docker-compose)
11. [Docker Hub](#-११-docker-hub)
12. [প্র্যাকটিক্যাল প্রজেক্ট](#-१२-প্র্যাকটিক্যাল-প্রজেক্ট)
13. [সমস্যা সমাধান](#-१३-সমস্যা-সমাধান)

### 🔴 **Advanced Level** (Production Ready)

14. [Multi-stage Builds](#-१४-multi-stage-builds)
15. [Docker Security](#-१५-docker-security)
16. [Resource Limits](#-१६-resource-limits)
17. [Healthcheck](#-१७-healthcheck)
18. [Private Registry](#-१८-private-registry)
19. [Restart Policies](#-१९-restart-policies)
20. [Bind Mount vs Volume](#-२०-bind-mount-vs-volume)

### 🟣 **Expert Level** (Deep Dive)

21. [Docker Architecture](#-२१-docker-architecture)
22. [Container Lifecycle](#-२२-container-lifecycle)
23. [CMD vs ENTRYPOINT](#-२३-cmd-vs-entrypoint)
24. [Layer Caching](#-२४-layer-caching)
25. [Production Best Practices](#-២५-production-best-practices)

---

# 🟢 **BEGINNER LEVEL**

## 🔹 ১. Docker কী এবং কেন?

### Docker সহজ ভাষায় বুঝি 🧠

কল্পনা করো তুমি একটি **সম্পূর্ণ খাবার ডেলিভারি** দিচ্ছো।

```
❌ Docker ছাড়া:
   ✓ শুধু recipe পাঠাও
   ✓ অন্যজন ঘর খুঁজে তৈরি করে
   ✗ উপকরণ নেই? সমস্যা! 😞

✅ Docker সাথে:
   ✓ খাবার + সব উপকরণ একটি sealed box এ
   ✓ যেকোনো জায়গায় পাঠাও
   ✓ সবসময় একই স্বাদ! ✨
```

**Docker ঠিক তাই করে** — আপনার **app + সব dependency একটি container এ** ভরে দেয়।

---

### Docker কী?

<div style="background: #f5f5f5; padding: 15px; border-radius: 5px; border-left: 4px solid #2496ED;">

**Docker হলো একটি open-source platform যা application কে **containerize** করে।**

এর মানে: আপনার code + সব library + configuration একটি self-contained unit এ packed থাকে, যা যেকোনো জায়গায় একই ভাবে চলে।

</div>

---

### কেন Docker প্রয়োজন?

| সমস্যা | Docker ছাড়া | Docker দিয়ে |
|--------|:----------:|:----------:|
| "আমার PC এ চলে কিন্তু তোমার চলে না" | 😭 বড় সমস্যা | ✅ সমাধান |
| নতুন server setup করা | ⏱️ ঘণ্টার পর ঘণ্টা | ⚡ মিনিটে হয়ে যায় |
| Multiple app চালানো | ⚠️ Conflict হয় | 🎯 আলাদা আলাদা চলে |
| Deployment জটিলতা | 🔧 অনেক সেটআপ | 🚀 সহজ ও দ্রুত |

---

### Docker vs Virtual Machine

```
┌──── VIRTUAL MACHINE ────┐    ┌──── DOCKER CONTAINER ────┐
│                         │    │                          │
│  ┌─────────────────┐   │    │  ┌──────┐  ┌──────┐    │
│  │  App A  App B   │   │    │  │ App A│  │ App B│    │
│  ├─────────────────┤   │    │  └──┬───┘  └──┬───┘    │
│  │  Guest OS       │   │    │     │ Libs    │ Libs    │
│  │  (2-4 GB)       │   │    │     │ Config  │ Config   │
│  ├─────────────────┤   │    │  ┌──┴─────────┴──┐      │
│  │  Hypervisor     │   │    │  │ Docker Engine  │      │
│  ├─────────────────┤   │    │  │ Host OS        │      │
│  │  Host OS        │   │    │  └────────────────┘      │
│  └─────────────────┘   │    │                          │
└────────────────────────┘    └──────────────────────────┘

❌ Heavy (GB)            ✅ Light (MB)
❌ Slow startup          ✅ Instant startup
❌ বেশি RAM             ✅ কম RAM
```

---

## 🔹 ২. Docker ইনস্টল করা

### Windows এ ইনস্টল

<details>
<summary><strong>📌 Windows Installation Steps</strong></summary>

1. [Docker Desktop for Windows](https://www.docker.com/products/docker-desktop) এ যান
2. **"Download for Windows"** বোতাম ক্লিক করুন
3. `.exe` ফাইল ডাউনলোড হবে
4. ফাইলটি open করুন এবং installation process follow করুন
5. Installation complete হলে **PC restart** করুন

</details>

### Mac এ ইনস্টল

<details>
<summary><strong>📌 Mac Installation Steps</strong></summary>

1. [Docker Desktop for Mac](https://www.docker.com/products/docker-desktop) এ যান
2. আপনার Mac architecture select করুন:
   - **Intel Chip** → Intel version
   - **Apple Silicon (M1/M2/M3)** → Apple Silicon version
3. `.dmg` ফাইল ডাউনলোড করুন
4. Applications folder এ drag করুন
5. Docker app launch করুন

</details>

### Linux (Ubuntu) এ ইনস্টল

<details>
<summary><strong>📌 Linux Installation Steps</strong></summary>

```bash
# ধাপ ১: পুরনো version remove করুন
sudo apt remove docker docker-engine docker.io

# ধাপ ২: Package list update করুন
sudo apt update

# ধাপ ৩: Docker install করুন
sudo apt install docker.io

# ধাপ ৪: Docker service চালু করুন
sudo systemctl start docker
sudo systemctl enable docker

# ধাপ ৫: আপনার user কে docker group এ add করুন
# (sudo ছাড়া Docker চালানোর জন্য)
sudo usermod -aG docker $USER

# ধাপ ৬: নতুন group activate করতে logout করুন
newgrp docker
```

</details>

### ✅ Installation যাচাই করুন

```bash
docker --version
```

**Output:**
```
Docker version 24.0.5, build ced0996
```

---

## 🔹 ३. Docker এর মূল ধারণা

Docker বুঝতে এই **৪টি key concept** জানা অপরিহার্য:

### 1️⃣ **Image** — Blueprint (ছাঁচ)

```
Image হলো একটি read-only template যা দিয়ে container তৈরি হয়।

📦 Example:
   - ubuntu:20.04 (OS image)
   - python:3.11 (Programming environment)
   - nginx (Web server)
```

### 2️⃣ **Container** — চলমান Instance

```
Container হলো image থেকে তৈরি একটি running environment।

💡 Analogy:
   Image = Class (blueprint)
   Container = Object (actual instance)

   একটি image থেকে অনেক container তৈরি করা যায়
```

### 3️⃣ **Volume** — Data Storage

```
Volume হলো persistent storage যা container destroyed হলেও data রক্ষা করে।

📁 Use cases:
   - Database data save করা
   - Log files store করা
   - User uploads save করা
```

### 4️⃣ **Network** — Communication

```
Network হলো container গুলোর মধ্যে communication এর মাধ্যম।

🌐 Example:
   Web container ↔ Database container (Network এর মাধ্যমে)
```

### Workflow চিত্র

```
                    ┌─────────────┐
                    │   Image     │
                    └──────┬──────┘
                           │ docker run
                           ↓
                    ┌─────────────┐
                    │  Container  │
                    └──────┬──────┘
                   ┌──────┬──────┐
                   ↓      ↓      ↓
              Volume Network Config
```

---

## 🔹 ४. প্রথম Docker Command

### Docker Information দেখুন

```bash
docker info
```

এই command Docker daemon এর সম্পূর্ণ information দেখায়।

### Hello World চালান

```bash
docker run hello-world
```

**Output:**
```
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
2db29710123e: Pull complete
...
Hello from Docker!
This message shows that your installation appears to be working correctly.
```

🎉 **Congratulations! আপনি প্রথম Docker container চালিয়েছেন!**

### পর্দার আড়ালে কী হয়?

```
Step 1: docker run hello-world command দেন
            ↓
Step 2: Docker check করে: "hello-world image আছে locally?"
            ↓
Step 3: না পেলে Docker Hub থেকে download করে
            ↓
Step 4: Image থেকে container তৈরি করে
            ↓
Step 5: Container চলায় এবং output দেখায়
            ↓
Step 6: Container automatically বন্ধ হয়ে যায়
```

---

## 🔹 ५. Docker Image

### সব Image দেখুন

```bash
docker images
```

**Output:**
```
REPOSITORY    TAG       IMAGE ID        CREATED         SIZE
hello-world   latest    9c7a54a9a43c    5 months ago    13.3kB
ubuntu        latest    35a88802559d    2 months ago    78.1MB
nginx         latest    605c77e624dd    3 weeks ago     142MB
```

### Image Pull করুন (Download)

```bash
# Latest version নামান
docker pull ubuntu

# নির্দিষ্ট version নামান
docker pull ubuntu:20.04

# নির্দিষ্ট version tag নামান
docker pull python:3.11-slim
```

### Image খুঁজুন

```bash
docker search nginx
```

এই command Docker Hub এ nginx এর সব available images দেখায়।

### Image মুছুন

```bash
# Image ID দিয়ে মুছুন
docker rmi 9c7a54a9a43c

# Image name দিয়ে মুছুন
docker rmi hello-world

# Force delete করুন (চলমান containers ছাড়াই)
docker rmi -f hello-world

# সব unused images মুছুন একসাথে
docker image prune
docker image prune -a  # সব unused, tagged সহ
```

### Image Details দেখুন

```bash
docker inspect ubuntu:20.04
```

এই command image এর সম্পূর্ণ metadata দেখায়।

---

## 🔹 ६. Docker Container

### Container চালান

```bash
# সহজ run
docker run ubuntu

# নাম দিয়ে চালান
docker run --name my-container ubuntu

# Interactive mode (shell access)
docker run -it ubuntu bash

# Background এ চালান (detached mode)
docker run -d nginx

# Port mapping সহ চালান
docker run -d -p 8080:80 nginx

# Environment variable সহ চালান
docker run -d -e DB_HOST=localhost mysql
```

> **Tip:** `-it` মানে `-i` (interactive) + `-t` (terminal)

### চলমান Container দেখুন

```bash
# শুধু চলমান container
docker ps

# সব container (চলমান + বন্ধ)
docker ps -a

# Last created container
docker ps -l
```

**Output:**
```
CONTAINER ID   IMAGE   STATUS       PORTS            NAMES
a1b2c3d4e5f6   nginx   Up 2 hours   0.0.0.0:8080->80/tcp   my-web
```

### Container Start/Stop/Restart

```bash
# Gracefully বন্ধ করুন (signal পাঠান)
docker stop container-name

# জোর করে বন্ধ করুন
docker kill container-name

# পুনরায় চালু করুন
docker start container-name

# Restart করুন
docker restart container-name

# Pause করুন
docker pause container-name

# Resume করুন
docker unpause container-name
```

### Container এ Command চালান

```bash
# Interactive bash shell খুলুন
docker exec -it container-name bash

# একটি command চালান
docker exec container-name ls -la

# নির্দিষ্ট user হিসেবে command চালান
docker exec -u root container-name whoami
```

### Container মুছুন

```bash
# একটি container মুছুন
docker rm container-name

# সব বন্ধ container মুছুন
docker container prune

# চলমান container force মুছুন
docker rm -f container-name
```

### Container Logs দেখুন

```bash
# সম্পূর্ণ log দেখুন
docker logs container-name

# Live log stream (real-time)
docker logs -f container-name

# শেষ ৫০ লাইন
docker logs --tail 50 container-name

# Timestamp সহ
docker logs -t container-name
```

### Container Stats দেখুন

```bash
# Container এর CPU, Memory usage দেখুন
docker stats container-name

# সব container এর stats
docker stats

# একবার দেখান (live না)
docker stats --no-stream
```

---

## 🔹 ७. Dockerfile লেখা

Dockerfile হলো একটি **text file** যেখানে লেখা থাকে image কীভাবে build হবে।

### সহজ উদাহরণ

```dockerfile
# Base image নির্ধারণ করুন
FROM ubuntu:20.04

# লেবেল যোগ করুন (metadata)
LABEL maintainer="আপনার নাম <email@example.com>"
LABEL version="1.0"

# Package আপডেট করুন
RUN apt-get update

# Python3 ইনস্টল করুন
RUN apt-get install -y python3 python3-pip

# Working directory সেট করুন
WORKDIR /app

# Local files container এ কপি করুন
COPY . .

# Dependencies ইনস্টল করুন
RUN pip install -r requirements.txt

# Port expose করুন
EXPOSE 8000

# Container চালু হলে যে command run হবে
CMD ["python3", "app.py"]
```

### Dockerfile Commands Reference

| Command | কাজ | উদাহরণ |
|---------|-----|---------|
| `FROM` | Base image নির্ধারণ | `FROM python:3.11-slim` |
| `RUN` | Shell command চালান | `RUN apt install nginx` |
| `COPY` | Local file → Container | `COPY app.py /app/` |
| `ADD` | COPY + URL/archive support | `ADD file.tar.gz /app/` |
| `WORKDIR` | Working directory সেট | `WORKDIR /app` |
| `EXPOSE` | Port expose করুন | `EXPOSE 8080` |
| `ENV` | Environment variable | `ENV DEBUG=true` |
| `CMD` | Default command | `CMD ["python", "app.py"]` |
| `ENTRYPOINT` | Entry point executable | `ENTRYPOINT ["nginx"]` |
| `ARG` | Build-time variable | `ARG VERSION=1.0` |

### Python Flask App Example

**app.py:**
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
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

# Dependency files কপি করুন
COPY requirements.txt .

# Dependencies ইনস্টল করুন
RUN pip install --no-cache-dir -r requirements.txt

# Application code কপি করুন
COPY app.py .

# Port expose করুন
EXPOSE 5000

# Application চালান
CMD ["python", "app.py"]
```

**Image Build করুন:**
```bash
docker build -t flask-app:1.0 .
```

**Container চালান:**
```bash
docker run -d -p 5000:5000 flask-app:1.0
```

### .dockerignore ফাইল

Dockerfile এর মতোই, `.dockerignore` কিছু files exclude করে build এ:

```
# .dockerignore
__pycache__/
*.pyc
*.log
.env
.git/
node_modules/
.DS_Store
```

---

## 🔹 ८. Docker Volume

Volume হলো **persistent storage** যা container মুছে গেলেও data রক্ষা করে।

### Volume তৈরি করুন

```bash
# Named volume তৈরি করুন
docker volume create my-database-volume

# সব volume দেখুন
docker volume ls

# Specific volume details দেখুন
docker volume inspect my-database-volume
```

### Volume ব্যবহার করুন

```bash
# Named volume দিয়ে চালান
docker run -d \
  --name my-db \
  -v my-database-volume:/var/lib/mysql \
  mysql:8.0

# Bind mount (local folder → container)
docker run -d \
  -v $(pwd)/data:/app/data \
  nginx

# Read-only mount
docker run -d \
  -v my-volume:/data:ro \
  nginx
```

### Volume মুছুন

```bash
# একটি volume মুছুন
docker volume rm my-database-volume

# সব unused volumes মুছুন
docker volume prune
```

### Named Volume vs Bind Mount

| দিক | Named Volume | Bind Mount |
|-----|:----------:|:----------:|
| Docker manages | ✅ হ্যাঁ | ❌ না |
| Backup সহজ | ✅ সহজ | 🟡 মাঝারি |
| Development | 🟡 ভালো | ✅ দারুণ |
| Production | ✅ Recommended | ❌ কম পছন্দনীয় |

---

## 🔹 ९. Docker Network

Network হলো container গুলোর মধ্যে **communication এর মাধ্যম**।

### Network Types

```
bridge (Default):  Container গুলো একই bridge network এ কথা বলে
host:             Container host এর network ব্যবহার করে
none:             কোনো network নেই
overlay:          Multiple hosts এ (Docker Swarm)
```

### Custom Network তৈরি করুন

```bash
# Bridge network তৈরি করুন
docker network create my-app-network

# সব network দেখুন
docker network ls

# Network details দেখুন
docker network inspect my-app-network
```

### Container কে Network এ যুক্ত করুন

```bash
# Run করার সময় network specify করুন
docker run -d \
  --name web-server \
  --network my-app-network \
  nginx

# পরে network যুক্ত করুন
docker network connect my-app-network existing-container

# Network থেকে disconnect করুন
docker network disconnect my-app-network existing-container
```

### Web + Database Example

```bash
# Network তৈরি করুন
docker network create app-net

# Database চালান
docker run -d \
  --name db \
  --network app-net \
  -e MYSQL_ROOT_PASSWORD=password \
  mysql:8.0

# Web app চালান (db hostname দিয়ে access করতে পারবে)
docker run -d \
  --name web \
  --network app-net \
  -p 8080:80 \
  my-web-app
```

---

## 🔹 १०. Docker Compose

একাধিক container একসাথে manage করার জন্য **Docker Compose** ব্যবহার করুন।

### docker-compose.yml Structure

```yaml
version: '3.8'

services:
  # Service 1: Web Application
  web:
    build: .
    ports:
      - "8080:80"
    depends_on:
      - db
    environment:
      - DB_HOST=db
      - DB_USER=user

  # Service 2: Database
  db:
    image: mysql:8.0
    volumes:
      - db-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: myapp

  # Service 3: Cache
  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  db-data:

networks:
  default:
    name: app-network
```

### Compose Commands

```bash
# সব service চালু করুন
docker compose up

# Background এ চালু করুন
docker compose up -d

# Build করে চালু করুন
docker compose up --build

# সব বন্ধ করুন (volumes রেখে)
docker compose down

# সব বন্ধ এবং volumes মুছুন
docker compose down -v

# Service status দেখুন
docker compose ps

# Logs দেখুন
docker compose logs

# Live logs
docker compose logs -f

# নির্দিষ্ট service restart করুন
docker compose restart web

# নির্দিষ্ট service এ command চালান
docker compose exec web bash
```

### WordPress + MySQL Example

```yaml
version: '3.8'

services:
  wordpress:
    image: wordpress:latest
    ports:
      - "8080:80"
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_NAME: wordpress
      WORDPRESS_DB_USER: wpuser
      WORDPRESS_DB_PASSWORD: wppassword
    depends_on:
      - db

  db:
    image: mysql:8.0
    volumes:
      - db-data:/var/lib/mysql
    environment:
      MYSQL_ROOT_PASSWORD: rootpassword
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wpuser
      MYSQL_PASSWORD: wppassword

volumes:
  db-data:
```

---

## 🔹 ११. Docker Hub

Docker Hub হলো Docker এর **official registry** যেখানে images store করা যায়।

### Account তৈরি করুন

[hub.docker.com](https://hub.docker.com) এ গিয়ে free account তৈরি করুন।

### Image Push করুন (Upload)

```bash
# Login করুন
docker login
# Username এবং password দিন

# Image কে tag করুন
docker tag my-app:1.0 yourusername/my-app:latest

# Push করুন
docker push yourusername/my-app:latest
```

### Image Pull করুন

```bash
docker pull yourusername/my-app:latest
```

### জনপ্রিয় Official Images

```
ubuntu          → Linux OS
python:3.11     → Python environment
node:18         → Node.js
nginx           → Web server
mysql:8.0       → MySQL database
postgres:15     → PostgreSQL
redis:7         → Redis cache
mongodb         → MongoDB database
```

---

## 🔹 १२. প্র্যাকটিক্যাল প্রজেক্ট

### প্রজেক্ট 1: Nginx Static Website

```bash
# Folder তৈরি করুন
mkdir my-website && cd my-website

# HTML ফাইল তৈরি করুন
cat > index.html << 'EOF'
<!DOCTYPE html>
<html>
<head><title>Docker Website</title></head>
<body>
  <h1>🐳 Docker দিয়ে আমার সাইট!</h1>
</body>
</html>
EOF

# Container চালান
docker run -d \
  -p 8080:80 \
  -v $(pwd):/usr/share/nginx/html \
  --name my-site \
  nginx
```

**Browser এ দেখুন:** `http://localhost:8080`

### প্রজেক্ট 2: Python Flask + MySQL

**Folder Structure:**
```
my-app/
├── app.py
├── requirements.txt
├── Dockerfile
└── docker-compose.yml
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

**চালান:**
```bash
docker compose up --build
```

---

## 🔹 १३. সমস্যা সমাধান

### Problem 1: Port already in use

```bash
# Error:
# docker: Error response from daemon: driver failed programming external connectivity on endpoint

# সমাধান:
docker run -p 8081:80 nginx  # অন্য port ব্যবহার করুন
```

### Problem 2: Permission denied (Linux)

```bash
# Error:
# Got permission denied while trying to connect to Docker daemon

# সমাধান:
sudo usermod -aG docker $USER
newgrp docker
```

### Problem 3: Container immediately stops

```bash
# Log দেখুন কেন বন্ধ হয়েছে:
docker logs container-name

# Exit code check করুন:
docker inspect container-name | grep ExitCode
```

### Problem 4: Image not found

```bash
# এটি সমাধান করুন:
docker search image-name
docker pull image-name
```

### Problem 5: Disk space full

```bash
# সব unused resource মুছুন:
docker system prune -a --volumes

# Disk usage দেখুন:
docker system df
```

---

# 🔴 **ADVANCED LEVEL**

## 🔹 १४. Multi-stage Builds

Production image small এবং secure রাখার জন্য multi-stage builds ব্যবহার করুন।

```dockerfile
# Build Stage
FROM golang:1.21 AS builder
WORKDIR /app
COPY . .
RUN go build -o myapp .

# Production Stage (শুধুমাত্র binary)
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/myapp .
CMD ["./myapp"]
```

**সুবিধা:**
- ✅ Image অনেক ছোট
- ✅ Faster deployment
- ✅ Better security

---

## 🔹 १५. Docker Security

### Non-root User ব্যবহার করুন

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

### Minimal Base Image

| Image | Size | ব্যবহার |
|-------|------|---------|
| ubuntu | ~78MB | General purpose |
| alpine | ~5MB | Production ✅ |
| distroless | ~2MB | Maximum security |

---

## 🔹 १६. Resource Limits

```bash
docker run \
  --memory="512m" \
  --cpus="1" \
  nginx
```

**Docker Compose এ:**
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

## 🔹 १७. Healthcheck

```dockerfile
HEALTHCHECK --interval=30s --timeout=10s --retries=3 \
  CMD curl --fail http://localhost:8080/health || exit 1
```

---

## 🔹 १८. Private Registry

```bash
# Local registry চালান
docker run -d -p 5000:5000 registry:2

# Image push করুন
docker tag my-app localhost:5000/my-app
docker push localhost:5000/my-app
```

---

## 🔹 १९. Restart Policies

```bash
docker run -d \
  --restart always \
  nginx
```

**Options:** `no` | `always` | `unless-stopped` | `on-failure`

---

## 🔹 २०. Bind Mount vs Volume

```bash
# Bind Mount (development)
docker run -v $(pwd):/app nginx

# Named Volume (production)
docker run -v my-data:/app/data nginx
```

---

# 🟣 **EXPERT LEVEL**

## 🔹 २१. Docker Architecture

```
User Input (docker run)
    ↓
Docker CLI Client
    ↓
REST API (Unix socket)
    ↓
Docker Daemon (dockerd)
    ↓
├── Image Management
├── Container Runtime
├── Network Management
└── Volume Management
```

---

## 🔹 २२२. Container Lifecycle

```
created → running → paused → stopped → removed
            ↕           ↕        ↕
          start       unpause  start
          pause       stop
          kill
```

---

## 🔹 २३. CMD vs ENTRYPOINT

```dockerfile
# CMD - Override করা যায়
CMD ["python", "app.py"]
docker run myapp python test.py  # test.py চলে

# ENTRYPOINT - Fixed থাকে
ENTRYPOINT ["python"]
docker run myapp test.py  # python test.py চলে
```

---

## 🔹 २४. Layer Caching

```dockerfile
# ❌ Slow
COPY . .
RUN pip install -r requirements.txt

# ✅ Fast
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
```

---

## 🔹 २५. Production Best Practices

✅ **Do:**
- Specific image tags ব্যবহার করুন (`python:3.11-alpine`)
- `.dockerignore` ফাইল রাখুন
- One process per container
- Non-root user হিসেবে চালান
- Healthcheck implement করুন
- Resource limits সেট করুন
- Environment variables ব্যবহার করুন

❌ **Don't:**
- `latest` tag ব্যবহার করবেন না
- Sensitive data image এ build করবেন না
- সব কিছু একটি container এ রাখবেন না
- Root user হিসেবে চালাবেন না

---

# 📌 Quick Reference Commands

```bash
# IMAGE COMMANDS
docker pull nginx
docker build -t myapp:1.0 .
docker images
docker rmi image-name

# CONTAINER COMMANDS
docker run -d -p 8080:80 nginx
docker ps
docker logs container-name
docker exec -it container-name bash
docker stop container-name
docker rm container-name

# VOLUME COMMANDS
docker volume create my-data
docker volume ls
docker volume rm my-data

# NETWORK COMMANDS
docker network create my-net
docker network ls

# COMPOSE COMMANDS
docker compose up -d
docker compose down
docker compose logs
docker compose ps

# SYSTEM COMMANDS
docker system prune
docker system df
docker info
```

---

# 📚 Learning Resources

- 📖 [Docker Official Docs](https://docs.docker.com)
- 🐳 [Docker Hub](https://hub.docker.com)
- 🧪 [Play With Docker](https://labs.play-with-docker.com)
- ⭐ [Awesome Docker](https://github.com/veggiemonk/awesome-docker)

---

<div align="center">

## 🎓 Next Steps

```
Docker Basics ✅
     ↓
Docker Compose ✅
     ↓
Kubernetes 🎯
     ↓
DevOps Expert 🚀
```

**Happy Learning! 🐳**

</div>
