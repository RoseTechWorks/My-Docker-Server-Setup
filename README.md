# My-Docker-Server-Setup
Terraform project that creates an AWS EC2 instance with Docker preinstalled.   Uses S3 for remote backend storage and DynamoDB for state locking.   Includes a shell script to install Docker automatically during instance launch.


# 🚀 Docker Server Deployment on AWS with Terraform

This project shows how to use Terraform to automatically build an AWS EC2 instance that comes preinstalled with Docker.  
It also uses S3 and DynamoDB for remote backend storage and state locking.

---

## 🧱 Project Overview

The goal is to create a Docker ready EC2 instance on AWS.  
Terraform builds the infrastructure, while a shell script installs Docker automatically.  
S3 stores the Terraform state file, and DynamoDB prevents multiple people from applying changes at the same time.

---

## 🗂 Files

`remote-state.tf`  sets up the S3 backend and DynamoDB for locking  
`docker.tf`  builds the VPC, security group, and EC2 instance  
`docker-install.sh`  installs Docker on the EC2 instance using user data  

---

## ⚙️ How It Works

Terraform initializes and connects to the S3 backend  
DynamoDB locks the state file during execution  
Terraform applies the configuration to create an EC2 instance  
The EC2 instance runs `docker-install.sh` automatically to install Docker  

---

## 🧰 Tools Used

Terraform  
AWS (S3, DynamoDB, EC2)  
Bash script for Docker installation  
