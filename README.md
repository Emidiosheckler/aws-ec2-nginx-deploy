# AWS WordPress Deployment with Docker

## Overview
This project demonstrates the deployment of a WordPress application using Docker containers on an AWS EC2 instance running Ubuntu 22.04.

## Architecture
Client → Internet → AWS EC2 → Docker Network → WordPress Container → MySQL Container

## Technologies Used
- AWS EC2
- Ubuntu 22.04
- Docker
- MySQL 5.7
- WordPress Latest

## Deployment Steps
1. Launched EC2 instance
2. Installed Docker
3. Created Docker network
4. Deployed MySQL container
5. Deployed WordPress container
6. Configured port 80 access

## Security Configuration
- Configured Security Group to allow HTTP (Port 80)
- Isolated containers using Docker network

## Lessons Learned
- How to manage port conflicts
- How to connect containers using Docker networks
- Basic troubleshooting in cloud environments
