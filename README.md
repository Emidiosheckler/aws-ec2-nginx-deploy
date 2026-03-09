# Production-ready WordPress Deployment with Docker on AWS EC2

![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Docker](https://img.shields.io/badge/Docker-Compose-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue)
![WordPress](https://img.shields.io/badge/WordPress-Latest-21759B)

## Overview

This project demonstrates a production-style deployment of a WordPress application on AWS EC2 using Docker Compose and MySQL.

The environment was built on an Ubuntu-based EC2 instance and configured to expose the application publicly through port 80.

This project demonstrates hands-on experience with:

- AWS EC2 provisioning
- Docker containerization
- Docker Compose orchestration
- WordPress deployment
- MySQL database configuration
- Infrastructure troubleshooting in a cloud environment

---

## Architecture

Client → Internet → AWS EC2 → Docker Compose → WordPress Container + MySQL Container

---

## Infrastructure Components

- AWS EC2
- Ubuntu 22.04
- Docker Engine
- Docker Compose
- WordPress Latest
- MySQL 8.0

---

## Deployment Process

The environment was deployed with the following high-level steps:

1. Launch an EC2 instance on AWS
2. Configure the Security Group to allow:
   - Port 22 (SSH)
   - Port 80 (HTTP)
3. Connect to the instance via SSH
4. Install Docker and Docker Compose
5. Create the `docker-compose.yml` file
6. Start the containers with Docker Compose
7. Validate container health and public access

---

## Deployment Commands

```bash
sudo systemctl stop nginx
sudo docker compose up -d
sudo docker ps
curl localhost
````
##Docker Compose Configuration

-This project uses Docker Compose to orchestrate two services:
-wordpress_app
-wordpress_db
-The WordPress container is exposed publicly on port 80, while MySQL runs internally inside the Docker network.

##Security Configuration

-EC2 Security Group configured with:
-SSH (Port 22)
-HTTP (Port 80)
-Containers isolated inside Docker networking
-Public access restricted to the application layer only

##Why Docker?

-Docker was used in this project to provide:
-Environment consistency
-Easier deployment management
-Service isolation
-Faster redeployment
-Better portability across environments

##Manual Deployment vs Docker Compose
Manual setup
-Individual service installation
-Harder maintenance
-More error-prone reconfiguration
-Limited portability

##Docker Compose

-Infrastructure as Code approach
-Easier service orchestration
-Faster redeployment
-Cleaner and more reproducible setup

##Troubleshooting

-During deployment, I solved the following real-world issues:
-Port 80 conflict caused by Nginx running on the host
-Docker Compose YAML syntax errors
-Container naming conflicts from previous test runs
-Docker daemon startup issues
-Service exposure validation using curl localhost
-Validation of running containers with docker ps

##Rollback Procedure

-If deployment fails, the environment can be safely reset using:
````bash
sudo docker compose down -v
sudo docker system prune -a
````
This removes containers, networks, volumes, and unused images to allow a clean redeployment.

Local Testing

Before validating the project on AWS EC2, the service behavior can be tested with Docker locally using:
````bash
sudo docker compose up
````
Then access:

http://localhost

This helps validate container communication and service availability.

##Result

The WordPress application was successfully deployed and made accessible through the EC2 public IP.

Public URL
http://54.210.157.136/
Admin URL
http://[54.210.157.136/]/wp-admin

##Screenshots

WordPress Home
WordPress Dashboard

##Files Included

This repository should contain:

-docker-compose.yml
-README.md
-DiagramaCLOUDAWS.drawio.png
-screenshots/wordpress-home.png
-screenshots/wordpress-dashboard.png

##Lessons Learned

This project helped reinforce practical knowledge in:

-EC2 infrastructure setup
-Docker-based application deployment
-Multi-container environments
-Cloud troubleshooting
-Public service exposure
-Real deployment debugging workflow

##About the Author

AWS-focused Cloud/DevOps beginner with hands-on experience deploying containerized applications on EC2.

This project demonstrates:

-Docker-based application deployment
-MySQL and WordPress container orchestration
-Public web exposure through EC2
-Troubleshooting of real infrastructure issues

Open to remote international opportunities.
