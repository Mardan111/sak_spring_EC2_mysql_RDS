# 🚀 Spring Boot Application Deployment using Jenkins, AWS EC2 & MySQL RDS

## 📌 Project Overview

This project demonstrates a complete **CI/CD pipeline** for deploying a **Spring Boot application** on **AWS EC2** with **Amazon RDS MySQL** as the backend database. The deployment process is fully automated using **Jenkins**, enabling continuous integration and continuous deployment.

The objective of this project is to showcase modern DevOps practices including infrastructure provisioning, application deployment, database integration, and automated build pipelines.

---

## 🏗️ Architecture

```
                 Developer
                      │
                      ▼
                GitHub Repository
                      │
          Webhook / Poll SCM Trigger
                      │
                      ▼
                  Jenkins Server
          (Build • Test • Package)
                      │
             Maven Build (JAR)
                      │
                      ▼
             Deploy to AWS EC2
                      │
          Spring Boot Application
                      │
                      ▼
             Amazon RDS (MySQL)
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| Java 21 | Backend Development |
| Spring Boot | REST API Framework |
| Spring Data JPA | ORM |
| Maven | Build Tool |
| MySQL | Relational Database |
| Amazon RDS | Managed Database |
| AWS EC2 | Application Hosting |
| Jenkins | CI/CD Automation |
| Git | Version Control |
| GitHub | Source Code Repository |
| Linux (Ubuntu) | Deployment Server |

---

## 📂 Project Structure

```
sak_spring_EC2_mysql_RDS/
│
├── src/
│   ├── main/
│   ├── test/
│
├── .mvn/
├── mvnw
├── mvnw.cmd
├── pom.xml
├── Jenkinsfile
├── .gitignore
└── README.md
```

---

# ⚙️ CI/CD Pipeline

The Jenkins pipeline automates the following stages:

### ✅ Stage 1: Checkout Source Code

- Pull latest code from GitHub
- Clean workspace

### ✅ Stage 2: Build

- Compile Java source
- Download dependencies
- Package application using Maven

```bash
mvn clean package
```

---

### ✅ Stage 3: Testing

Execute unit tests

```bash
mvn test
```

---

### ✅ Stage 4: Deployment

Deploy generated JAR file to EC2 instance

```bash
java -jar springboot-app.jar
```

---

### ✅ Stage 5: Verification

Verify application availability

```
http://<EC2-Public-IP>:8080
```

---

# ☁️ AWS Infrastructure

## EC2

- Ubuntu Server
- Java 17 Installed
- Maven Installed
- Git Installed
- Jenkins Agent
- Security Group configured

### Open Ports

| Port | Purpose |
|-------|----------|
|22|SSH|
|8080|Spring Boot|
|8081|Jenkins (Optional)|
|3306|MySQL (RDS)|

---

## Amazon RDS

Database Engine

- MySQL

Configuration

- Public Access Enabled (For Demo)
- Security Group configured
- Database Endpoint used in Spring Boot application

Example:

```properties
spring.datasource.url=jdbc:mysql://<RDS-ENDPOINT>:3306/studentdb
spring.datasource.username=admin
spring.datasource.password=********
```

---

# 🔧 Jenkins Pipeline

The project includes a declarative Jenkins pipeline.

Pipeline responsibilities:

- Checkout source code
- Build Maven project
- Execute tests
- Generate executable JAR
- Deploy application
- Monitor build status

---

# 🚀 Deployment Steps

## Clone Repository

```bash
git clone https://github.com/<username>/sak_spring_EC2_mysql_RDS.git
```

---

## Build Application

```bash
mvn clean package
```

---

## Run Application

```bash
java -jar target/*.jar
```

---

## Access Application

```
http://<EC2-PUBLIC-IP>:8080
```

---

# 📊 DevOps Workflow

```
Developer
    │
    ▼
Git Push
    │
    ▼
GitHub
    │
Webhook
    ▼
Jenkins
    │
Build
    ▼
Test
    │
Package
    ▼
Deploy
    │
EC2
    │
Spring Boot
    │
RDS MySQL
```

---

# 🔐 Security Considerations

- IAM controlled AWS access
- Security Groups configured with least privilege
- Database credentials externalized
- Jenkins credentials stored securely
- Git ignored sensitive files

---

# 📸 Project Screenshots

Recommended screenshots to include:

- GitHub Repository
- Jenkins Dashboard
- Jenkins Pipeline
- Successful Build Console
- AWS EC2 Instance
- Amazon RDS Dashboard
- Running Spring Boot Application
- Application Home Page

Example:

```
images/
├── github.png
├── jenkins-dashboard.png
├── pipeline.png
├── ec2.png
├── rds.png
└── application.png
```

---

# 🎯 Features

- CI/CD Pipeline
- Automated Deployment
- Spring Boot REST API
- AWS EC2 Hosting
- Amazon RDS Integration
- Jenkins Automation
- Maven Build
- GitHub Version Control
- Production-style Deployment

---

# 💡 Future Enhancements

- Docker Containerization
- Kubernetes Deployment (EKS)
- Terraform Infrastructure as Code
- Ansible Configuration Management
- SonarQube Code Quality
- Nexus Artifact Repository
- Prometheus Monitoring
- Grafana Dashboard
- AWS Load Balancer
- Auto Scaling Group
- SSL using Nginx & Let's Encrypt

---

# 🏆 DevOps Skills Demonstrated

- Continuous Integration
- Continuous Deployment
- Jenkins Pipeline Development
- AWS EC2 Administration
- Amazon RDS Configuration
- Linux Server Administration
- Maven Build Automation
- Git & GitHub Workflow
- Spring Boot Deployment
- Database Connectivity
- Infrastructure Troubleshooting
- Application Monitoring

---

# 📈 Learning Outcomes

This project demonstrates practical experience in:

- Building enterprise CI/CD pipelines
- Deploying Java applications to AWS
- Configuring managed databases
- Automating software delivery
- Managing Linux servers
- Production deployment best practices

---

# 👨‍💻 Author

**Mardan**

DevOps Engineer | AWS | Jenkins | Docker | Kubernetes | Terraform | Linux | CI/CD | Spring Boot

---

## ⭐ If you found this project useful, consider giving it a Star!
