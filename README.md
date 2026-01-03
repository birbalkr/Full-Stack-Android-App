# **Full-Stack Android App**

<!-- [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) -->
[![Frontend](https://img.shields.io/badge/Frontend-React%20Native-blue)](https://reactnative.dev/)
[![Backend](https://img.shields.io/badge/Backend-Spring%20Boot-orange)](https://spring.io/projects/spring-boot)
[![Database](https://img.shields.io/badge/Database-MySQL-blue)](https://www.mysql.com/)
[![Docker](https://img.shields.io/badge/Docker-Container-blue)](https://www.docker.com/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-Orchestration-blue)](https://kubernetes.io/)

**Contributors:** Birbal Kumar & Parbhakar Kumar

---

## **Table of Contents**

1. [Project Overview](#project-overview)
2. [Tech Stack](#tech-stack)
3. [Workflow](#workflow)
4. [Architecture Diagram](#architecture-diagram)
5. [Installation & Setup](#installation--setup)
6. [Docker Setup](#docker-setup)
7. [Kubernetes Deployment](#kubernetes-deployment)
8. [Usage](#usage)
9. [Contributing](#contributing)
10. [License](#license)

---

## **Project Overview**

This is a **full-stack Android application** demonstrating a modern development workflow:

* **Frontend**: React Native app for Android devices
* **Backend**: RESTful API built with Spring Boot
* **Database**: MySQL for storing user and app data
* **Containerization**: Docker ensures environment consistency
* **Orchestration**: Kubernetes allows scaling and deployment

The app supports **user authentication, CRUD operations**, and **API-based communication** between the mobile app and backend.

---

## **Tech Stack**

| Layer         | Technology                       |
| ------------- | -------------------------------- |
| Frontend      | React Native                     |
| Backend       | Spring Boot                      |
| Database      | MySQL                            |
| Container     | Docker                           |
| Orchestration | Kubernetes                       |
| Tools         | VS Code, Android Studio, Postman |

---

## **Workflow**

The project development follows this step-by-step workflow:

1. **Frontend → Backend**

   * React Native app consumes REST APIs provided by Spring Boot backend.
   * Axios is used for API calls to fetch and update data.

2. **Backend → Docker**

   * Backend Spring Boot app is containerized using Docker.
   * Ensures the same runtime environment across systems.

3. **Docker → Kubernetes**

   * Docker images of backend, frontend (optional), and database are deployed in Kubernetes.
   * Kubernetes manages scaling, networking, and monitoring.

---

## **Architecture Diagram**

```
[React Native App]
        |
        v
[Spring Boot REST API]
        |
        v
[MySQL Database]

       Docker Containerization
            |
            v
       Kubernetes Deployment
```

---

## **Installation & Setup**

### **Frontend Setup**

```bash
# Clone repo
git clone repo link
# Change dir
cd frontend
# Install dependencies
npm install / npm i
# Run on Android emulator/device
npx react-native run-android / npm start
```

### **Backend Setup**

```bash
# Clone repo
git clone link
# Change dir
cd backend
# Configure MySQL in application.properties

# MYSQL DataSource configuration
spring.datasource.url=jdbc:mysql://localhost:3306/yourdb
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update   

# MariaDB DataSource configuration
spring.datasource.url=jdbc:mariadb://localhost:3306/employee
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.datasource.driver-class-name=org.mariadb.jdbc.Driver

# Hibernate/JPA configuration
spring.jpa.hibernate.ddl-auto=update


# Build and run backend
mvn clean install
mvn spring-boot:run
```

### **Database**

* Install MySQL locally or run via Docker.
* Create a database for the app:

```sql
CREATE DATABASE yourdb;
```

---

## **Docker Setup**

### **Build Docker Images**

```bash
docker build -t backend-app ./backend
docker build -t frontend-app ./frontend # optional
docker build -t mysql-db ./mysql # optional if using Docker MySQL
```

### **Run Docker Containers**

```bash
docker run -p 8080:8080 backend-app
docker run -p 3000:3000 frontend-app
docker run -p 3306:3306 mysql-db
```

---

## **Kubernetes Deployment**

### **Apply Kubernetes Files**

```bash
kubectl apply -f k8s/mysql-deployment.yaml
kubectl apply -f k8s/backend-deployment.yaml
kubectl apply -f k8s/frontend-deployment.yaml
```

### **Check Pods and Services**

```bash
kubectl get pods
kubectl get services
```

### **Kubernetes Notes**

* Ensure **Minikube or a Kubernetes cluster** is running.
* MySQL service must be accessible to the backend pod.
* Backend deployment connects to MySQL via Kubernetes service name.

---

## **Usage**

* Run **frontend on Android emulator** or device.
* Backend handles **API requests** for login, signup, and CRUD operations.
* Use **Postman** or the mobile app to test API endpoints.
* Docker & Kubernetes ensure **production-like deployment**.

---
