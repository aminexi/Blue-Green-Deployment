# Simple Calcul Java EE App — Blue-Green Deployment

## Overview

This project demonstrates a **Blue-Green deployment strategy** for a Java EE web application (`Simple Calcul`) using **Docker, Docker Compose, and Nginx**.  
The goal is to deploy new versions of the application safely without downtime, by switching traffic between two versions (Blue and Green).

---

## Technologies Used

- Java EE (WAR application)
- Apache Tomcat 10 (inside Docker)
- Docker & Docker Compose
- Nginx (as reverse proxy)

---

## Project Structure
```bash
simple-calcul-jee/
├── Dockerfile
├── docker-compose.yml
├── nginx.conf
├── Calcul-1.0-SNAPSHOT.war
└── src/ (Java source code)
````
# Deployment Steps — Simple Calcul Java EE App

## 1. Start Containers

```bash
docker-compose up -d --build

Blue accessible at: http://localhost:8888

Green accessible at: http://localhost:8081

Nginx entry point: http://localhost:9080
````
## 2. Verify Nginx Routing 
```bash
docker exec -it todolist_nginx curl http://blue:8080
docker exec -it todolist_nginx curl http://green:8080
````
## 3. Switch Traffic to Green
```bash
Edit nginx.conf:

upstream todolist_app {
    # server blue:8080;
    server green:8080;
}
````
## 4. Reload Nginx:
```bash
docker exec todolist_nginx nginx -s reload
````
https://roadmap.sh/projects/blue-green-deployment
