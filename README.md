# 📘 End-to-End DevOps Cycle: Django Notes App

This repository showcases a **complete End-to-End DevOps Cycle** implementation of the [Django Notes App](https://github.com/LondheShubham153/django-notes-app.git).  
The project demonstrates **CI/CD automation, containerization, deployment on AWS, and monitoring with Prometheus & Grafana.**

## 📂 Source Code Reference
The original source code for the Django Notes App comes from [LondheShubham153/django-notes-app](https://github.com/LondheShubham153/django-notes-app.git).  
I have extended it with:
- **Dockerfile** for containerizing the application.
- **docker-compose.yml** for multi-container orchestration (Django + MySQL + NGINX + Node Exporter).
- **Monitoring setup** (Prometheus & Grafana).
- **End-to-End DevOps workflow** deployed on AWS EC2.


## 📊 Project Flow

![DevOPS Cycle](https://github.com/user-attachments/assets/20963b5a-d53a-4747-aec9-3c23db35734f)


**Flow Explanation:**
1. **Developer pushes code** to GitHub.
2. **GitHub Actions / CodePipeline** triggers CI/CD workflow.
3. **Docker builds images** for Django, MySQL, NGINX, Node Exporter.
4. **docker-compose** deploys containers on EC2.
5. **Prometheus** collects metrics from Node Exporter.
6. **Grafana (running locally)** visualizes metrics dashboards.
7. **NGINX** serves as a reverse proxy for Django.


## 🐳 Docker & Compose Setup

### `Dockerfile`
The `Dockerfile` defines how to:
- Build the Django app image.
- Install dependencies.
- Set up Gunicorn for production-grade serving.

### `docker-compose.yml`
The `docker-compose.yml` orchestrates multiple services:
- **Django App** (backend logic & APIs).
- **MySQL Database** (persistent data store).
- **NGINX** (reverse proxy & load balancing).
- **Node Exporter** (system-level metrics exporter).

This allows the entire stack to be deployed with a single command:

"docker-compose up -d"

## 📈 Monitoring Setup  

### prometheus.yml  
- Defines Prometheus scrape configurations, including:  
  - Node Exporter metrics endpoint.  
  - Integration with the EC2-hosted stack.  

### Prometheus & Grafana  
- **Prometheus & Grafana were run locally** as containers on my system.  
- They scraped metrics from the EC2 instance.  
- Grafana connected to Prometheus as the data source.  

#### Dashboards  
- **CPU, memory, and disk utilization**  
- **Container health metrics**  


## 🔒 Security Considerations  

- AWS Security Groups configured to allow **custom TCP ports** for:  
  - Node Exporter  
  - Prometheus  
  - Grafana  
- Django app, MySQL, and NGINX secured under controlled ports.  


## 🚀 End-to-End Workflow  

1. Clone the repo & extend source code.  
2. Write **Dockerfile** & **docker-compose.yml**.  
3. Push changes to GitHub.  
4. CI/CD pipeline builds & deploys containers on EC2.  
5. Expose Node Exporter metrics to Prometheus (running locally).  
6. Visualize metrics in Grafana dashboards.  


## 📌 Features  

✅ End-to-End DevOps cycle demonstration  
✅ Automated deployment via Docker & GitHub Actions  
✅ AWS EC2 deployment with container orchestration  
✅ Real-time monitoring using Prometheus & Grafana  
✅ Clear project flow with architecture diagram  


## 🙌 Credits  

- **Original Django Notes App:** [LondheShubham153/django-notes-app](https://github.com/LondheShubham153/django-notes-app.git)  
- **Extended, containerized, and monitored version:** Built by me as part of my **DevOps learning journey**.  
