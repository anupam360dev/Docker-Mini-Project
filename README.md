# 🚀 Mini Project – Dockerized Flask Web Application
**Name:** Anupam Das  
**Date:** November 2025  
**Location:** Hyderabad  
**Docker Hub:** [https://hub.docker.com/repositories/anupam360](https://hub.docker.com/repositories/anupam360)

---

## 🧠 1. Objective
To build, run, and manage a containerized Flask web application using Docker and demonstrate:
- Image creation and container management  
- Data persistence through volumes  
- Container communication using networks  
- Multi-container deployment with Docker Compose  
- Publishing images to Docker Hub  

---

## ⚙️ 2. Tools & Technologies Used
| Tool | Purpose |
|------|----------|
| **Docker Desktop (WSL2 - Ubuntu 24.04)** | Container runtime |
| **Python 3.11 + Flask** | Web application |
| **Nginx** | Web server container |
| **Redis** | Database container for networking |
| **Docker Compose** | Multi-container orchestration |
| **Docker Hub** | Image publishing and hosting |

---

## 🧩 3. Tasks Performed

| Task | Description | Screenshot Proof |
|------|--------------|------------------|
| **1** | Installed Docker and verified setup with `hello-world` | `01_hello_world.png` |
| **2** | Pulled & ran Nginx container | `02_nginx_running.png`, `03_nginx_browser.png` |
| **3** | Built Flask app from Dockerfile & ran it | `04_flask_build.png`, `05_flask_running.png`, `06_flask_browser.png` |
| **4** | Created Docker Volume & verified data persistence | `07_volume_list.png`, `08_volume_data.png` |
| **5** | Created custom network and verified communication (ping between containers) | `09_network_list.png`, `10_network_inspect.png`, `11_ping_test.png` |
| **6** | Used Docker Compose for multi-container deployment (nginx + redis) | `12_compose_up.png`, `13_compose_ps.png`, `14_compose_browser.png`, `15_compose_down.png` |
| **7** | Tagged & pushed image to Docker Hub | `16_flask_image_list.png`, `17_push_success.png`, `18_dockerhub_repo.png` |

---

## 🧮 4. Key Commands Used
```bash
# Verify Docker Installation
docker run hello-world

# Run public image
docker pull nginx
docker run -d -p 8080:80 nginx

# Build & run Flask App
docker build -t flaskapp .
docker run -d -p 5000:5000 flaskapp

# Volumes
docker volume create mydata
docker run -d --name voltest -v mydata:/data nginx
docker exec -it voltest bash
echo "This is persistent data" > /data/test.txt

# Networking
docker network create mynet
docker run -d --name web --network=mynet nginx
docker run -d --name db --network=mynet redis

# Docker Compose
docker compose up -d
docker compose down

# Docker Hub Upload
docker tag flaskapp anupam360/flaskapp:latest
docker login
docker push anupam360/flaskapp:latest
