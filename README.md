# Hello AWS

A simple cloud deployment project demonstrating how to run a FastAPI application with PostgreSQL on AWS EC2 using Docker, Terraform, and GitHub Actions.

## Architecture

Internet → Nginx :80 → FastAPI :8000 → PostgreSQL


```text
Developer
    ↓
Git Push
    ↓
GitHub Actions
    ↓
EC2 (AWS)
    ↓
Docker Compose
 ├─ FastAPI
 └─ PostgreSQL
```

## Features

* FastAPI backend
* PostgreSQL database
* Docker Compose deployment
* Infrastructure as Code with Terraform
* Elastic IP for stable public access
* Automated deployment with GitHub Actions
* Security Group configuration for SSH and HTTP access

## Tech Stack

### Backend

* FastAPI
* Python 3.13

### Database

* PostgreSQL 16

### Infrastructure

* AWS EC2
* Elastic IP
* Security Groups
* Terraform

### DevOps

* Docker
* Docker Compose
* GitHub Actions

## Local Development

```bash
docker compose up --build
```

Application:

```text
http://localhost:8000
```

## Deployment

Infrastructure is managed using Terraform.

```bash
cd terraform-ec2

terraform init
terraform plan
terraform apply
```

Application deployment is automated through GitHub Actions.

Every push to the `main` branch triggers:

1. SSH connection to EC2
2. Pull latest source code
3. Rebuild Docker containers
4. Restart application

## Terraform Resources

* EC2 Instance
* Security Group
* Elastic IP
* User Data bootstrap script

## Learning Goals

This project was created to practice:

* AWS fundamentals
* Infrastructure as Code
* Containerized deployment
* CI/CD automation
* Cloud networking basics

```
```
