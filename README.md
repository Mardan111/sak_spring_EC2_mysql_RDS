# 🚀 Spring Boot Application Deployment using Jenkins, AWS EC2 & MySQL Server (Private Subnet)

## 📌 Project Overview

This project demonstrates the deployment of a **Spring Boot application** using a complete **CI/CD pipeline** powered by **Jenkins** on **AWS**.

The application is deployed on an **Amazon EC2 instance** and securely communicates with a **MySQL Server hosted on a separate EC2 instance inside a Private Subnet** within an AWS VPC. The deployment follows cloud infrastructure best practices by isolating the database from public internet access.

The project showcases end-to-end DevOps implementation, including infrastructure setup, CI/CD automation, application deployment, and secure networking.

---

# 🏗️ Solution Architecture

```text
                        Developer
                            │
                            ▼
                     GitHub Repository
                            │
                     Git Push / Webhook
                            │
                            ▼
                     Jenkins Server
                  (Build • Test • Package)
                            │
                    Maven Build (JAR)
                            │
                            ▼
                 Application EC2 Instance
                   (Public Subnet)
                            │
             Private VPC Communication
                            │
                            ▼
                  MySQL Server EC2
                 (Private Subnet)
```

---

# ☁️ AWS Infrastructure

## AWS Services Used

- Amazon EC2
- Amazon VPC
- Public Subnet
- Private Subnet
- Security Groups
- Internet Gateway
- Route Tables
- Elastic IP
- Jenkins
- GitHub

---

## Infrastructure Design

### Public Subnet

Hosted Services:

- Jenkins Server
- Spring Boot Application
- SSH Access

Public Access:

- Internet Gateway attached
- Elastic IP assigned
- Accessible through Security Groups

---

### Private Subnet

Hosted Services:

- MySQL Server

Security:

- No Public IP
- Internet inaccessible
- Accessible only from Application EC2 through VPC
- Database port restricted using Security Groups

---

# 🔐 Network Security

## Security Group Configuration

### Application Server

Allowed Inbound

| Port | Purpose |
|-------|----------|
|22|SSH|
|8080|Spring Boot Application|
|8081|Jenkins (Optional)|

Outbound

- MySQL Port (3306) to Private Subnet

---

### MySQL Server

Allowed Inbound

| Port | Source |
|-------|---------|
|3306|Application EC2 Security Group|
|22|Bastion Host (Optional)|

No public internet access.

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
|Java 17|Backend|
|Spring Boot|REST API|
|Spring Data JPA|Database Access|
|MySQL Server|Database|
|Apache Maven|Build Tool|
|Jenkins|CI/CD|
|GitHub|Source Control|
|AWS EC2|Hosting|
|AWS VPC|Networking|
|Linux (Ubuntu)|Operating System|

---

# 📂 Project Structure

```text
sak_spring_EC2_mysql/

├── src/
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

The Jenkins pipeline automates the complete deployment lifecycle.

### Stage 1 – Source Code Checkout

- Pull latest source code from GitHub

---

### Stage 2 – Build

```bash
mvn clean package
```

---

### Stage 3 – Unit Testing

```bash
mvn test
```

---

### Stage 4 – Package

Generate executable Spring Boot JAR.

---

### Stage 5 – Deploy

Deploy the application to the EC2 server.

```bash
java -jar target/application.jar
```

---

### Stage 6 – Verification

Access the application:

```
http://<EC2-PUBLIC-IP>:8080
```

---

# 🗄️ MySQL Server Configuration

Database hosted on:

- EC2 Instance
- Ubuntu Linux
- MySQL Server
- Private Subnet

Example Spring configuration:

```properties
spring.datasource.url=jdbc:mysql://<PRIVATE-IP>:3306/studentdb
spring.datasource.username=root
spring.datasource.password=********
```

The application connects to MySQL through the private IP over the AWS VPC network.

---

# 🚀 Deployment Workflow

```text
Developer
    │
    ▼
GitHub
    │
Webhook
    ▼
Jenkins
    │
Checkout
    ▼
Build
    ▼
Test
    ▼
Package
    ▼
Deploy to EC2
    │
Spring Boot
    │
Private VPC Network
    ▼
MySQL Server (Private Subnet)
```

---

# 🔒 Security Best Practices

- Database isolated inside a Private Subnet
- No public access to MySQL Server
- Security Group-based communication
- Private IP database connectivity
- Jenkins automates deployments
- Sensitive files excluded using `.gitignore`
- Principle of least privilege applied to Security Groups

---

# 📊 DevOps Practices Implemented

- Continuous Integration
- Continuous Deployment
- Infrastructure Segmentation
- Secure VPC Networking
- Automated Build Pipeline
- Version Control
- Linux Server Administration
- Spring Boot Deployment
- MySQL Administration
- Secure Database Communication

---

# 📸 Project Screenshots

Include screenshots for:

- GitHub Repository
- Jenkins Dashboard
- Successful Jenkins Pipeline
- AWS VPC
- Public & Private Subnets
- EC2 Instances
- Security Groups
- MySQL Server
- Running Spring Boot Application

Example directory:

```text
images/
├── architecture.png
├── github.png
├── jenkins-dashboard.png
├── pipeline-success.png
├── vpc.png
├── public-subnet.png
├── private-subnet.png
├── ec2-app.png
├── mysql-server.png
└── application-home.png
```

---

# 🎯 Key Features

- CI/CD using Jenkins
- Spring Boot Application Deployment
- MySQL Server on EC2
- Secure VPC Architecture
- Public & Private Subnet Design
- Automated Maven Build
- GitHub Integration
- Linux Server Deployment
- Private Database Communication
- Production-Oriented AWS Architecture

---

# 🚀 Future Enhancements

- Dockerize the Application
- Deploy using Kubernetes (Amazon EKS)
- Infrastructure as Code using Terraform
- Configuration Management with Ansible
- SonarQube Integration
- Nexus Artifact Repository
- NGINX Reverse Proxy
- HTTPS using Let's Encrypt
- CloudWatch Monitoring
- Prometheus & Grafana
- AWS Auto Scaling
- Application Load Balancer (ALB)

---

# 💼 Skills Demonstrated

- AWS EC2 Administration
- AWS VPC Design
- Public & Private Subnet Configuration
- Security Group Management
- Linux Administration
- Jenkins CI/CD Pipeline Development
- Spring Boot Deployment
- Maven Build Automation
- Git & GitHub Workflow
- MySQL Server Administration
- Secure Application Architecture
- Production Deployment Strategy

---

# 👨‍💻 Author

**Mardan**

**DevOps Engineer | AWS | Jenkins | Docker | Kubernetes | Terraform | Linux | CI/CD | Spring Boot**

---

## ⭐ If you found this project useful, consider giving it a Star!
