# Production-ready WordPress Deployment with Docker on AWS EC2 

##
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/Docker-Compose-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue)
![WordPress](https://img.shields.io/badge/Deployment-Production-green)

## Overview

This project demonstrates a production-style deployment of WordPress on AWS EC2 using Docker Compose and MySQL.

The environment includes:
- AWS EC2
- Docker Engine
- Docker Compose
- WordPress container
- MySQL container
- Public HTTP access on port 80
  
# AWS EC2 + Docker WordPress Deployment

Production-ready WordPress deployment using Docker Compose on AWS EC2.

This project demonstrates how to deploy a WordPress application 
using Docker containers on an AWS EC2 instance.

The infrastructure includes:

- Docker containerization
- MySQL database container
- WordPress application container
- AWS EC2 cloud infrastructure
- Port exposure for public access

## Architecture

- AWS EC2 (Ubuntu)
- Docker Engine (official repository)
- Docker Compose v2
- MySQL 8.0 container
- WordPress latest container
- Port 80 exposed via Security Group

Infrastructure Overview

Client → Internet → AWS EC2 → Docker Compose → WordPress Container → MySQL Container

## Troubleshooting

During deployment, I solved the following issues:

- Port 80 conflict caused by Nginx running on the host
- Docker Compose YAML syntax errors
- Container name conflicts from previous test environments
- Docker daemon not running initially

These issues were resolved by stopping conflicting services, fixing the compose file, cleaning old containers, and restarting the environment correctly.

## Result

The WordPress application was successfully deployed and made accessible through the EC2 public IP.

Public URL:
http://54.236.210.172

##  Technologies Used
- AWS EC2
- Ubuntu 22.04
- Docker
- MySQL 5.7
- WordPress Latest

## 🛠 Deployment Step by Step

1. Launch an AWS EC2 Ubuntu 22.04 instance  
2. Install Docker on the instance  
3. Create Docker network
4. Deployed MySQL container
5. Deployed WordPress container
6. Configured port 80 access
   
## Deployment

The application was deployed using Docker Compose on an Ubuntu-based EC2 instance.

Main steps:
1. Launch EC2 instance
2. Configure Security Group
3. Install Docker
4. Create docker-compose.yml
5. Start containers with Docker Compose
6. Access WordPress via public IP

## Manual Deployment vs Docker Compose

Manual setup:
- Individual service installation
- Harder scaling
- Harder maintenance

Docker Compose:
- Infrastructure as Code
- Version-controlled configuration
- Faster redeployment
- Portable environment
   
  
## Rollback Procedure

If deployment fails, the environment can be safely reset using:

```bash
sudo docker compose down -v
sudo docker system prune -a
```
## Local Testing

Before deploying to AWS EC2, the application was tested locally using:

```bash
sudo docker compose up
```

## Deployment Commands Used

```bash
sudo docker network create wp_network

sudo docker run -d --name wp_db --network wp_network \
  -e MYSQL_DATABASE=wordpress \
  -e MYSQL_USER=wp_user \
  -e MYSQL_PASSWORD=wp_password \
  -e MYSQL_ROOT_PASSWORD=root_password \
  mysql:8.0

sudo docker run -d --name wp_app --network wp_network \
  -p 80:80 \
  -e WORDPRESS_DB_HOST=wp_db:3306 \
  -e WORDPRESS_DB_USER=wp_user \
  -e WORDPRESS_DB_PASSWORD=wp_password \
  -e WORDPRESS_DB_NAME=wordpress \
  wordpress

## Live   
## 🔗 Demo
Application deployed at:  
http://IP34.227.75.202

## Security Configuration
- Configured Security Group to allow HTTP (Port 80)
- Isolated containers using Docker network

## Why Docker? 

Docker was used to ensure application portability, environment consistency,
and easier deployment management.

## Challenges Faced

- Port conflict on port 80
- Docker container naming issues
- Network connectivity troubleshooting

## Lessons Learned
- How to manage port conflicts
- How to connect containers using Docker networks
- Basic troubleshooting in cloud environments

## About the Author

AWS-focused Cloud Engineer with hands-on experience deploying containerized applications using Docker on EC2.

This project demonstrates:
- Infrastructure provisioning on AWS
- Container networking
- Service exposure via public IP
- Production-style application deployment

Open to remote international opportunities.


    
    
  
