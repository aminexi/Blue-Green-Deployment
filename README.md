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

simple-calcul-jee/
├── Dockerfile
├── docker-compose.yml
├── nginx.conf
├── Calcul-1.0-SNAPSHOT.war
└── src/ (Java source code)
