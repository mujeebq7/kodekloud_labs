## Docker Ports

### Description

The Nautilus DevOps team is planning to host an application on a nginx-based container. There are number of tickets already been created for similar tasks. One of the tickets has been assigned to set up a nginx container on Application Server 3 in Stratos Datacenter. 

Please perform the task as per details mentioned below:


1. Pull nginx:alpine docker image on Application Server 3.


2. Create a container named games using the image you pulled.


3. Map host port 3004 to container port 80. Please keep the container in running state.

---

## Prerequisites

- Linux server
- Root access
- Docker installed

---

### Step 1: SSH into App Server 3
```bash
ssh user@stapp03
```
Become root if required:
```bash
sudo su
```

### Step 2 : Pull the Nginx image
```bash
docker pull nginx:alpine
```
Verify
```bash
docker images
```

### Step 3 : Create the container named games with port mapping
```bash
docker run -d --name games -p 3004:80 nginx:alpine
```

### Step 4 : Verify that the container is running
```bash
docker ps
```

### Step 5 : Test Nginx
```bash
curl http://localhost:3004
```
---
Task Completed
