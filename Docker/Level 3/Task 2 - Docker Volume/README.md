## Docker Volume

### Description

The Nautilus DevOps team is testing applications containerization, which is supposed to be migrated on docker container-based environments soon. In today's stand-up meeting one of the team members has been assigned a task to create and test a docker container with certain requirements. Below are more details:

1. On App Server 2 in Stratos DC pull nginx image (preferably latest tag but others should work too).

2. Create a new container with name "media" from the image you just pulled.

3. Map the host volume /opt/devops with container volume /usr/src/. There is an sample.txt file present on same server under /tmp; copy that file to /opt/devops. Also please keep the container in running state.

---

## Prerequisites

- Linux server
- Root access
- Docker installed

---

### Step 1 : SSH into App Server 2
```bash
ssh user@stapp02
```
Become root if required:
```bash
sudo su
```

### Step 2 : Pull the Nginx image
```bash
docker pull nginx:latest
```
Verify
```bash
docker images
```

### Step 3 : Create the host volume directory
```bash
mkdir -p /opt/devops
```

### Step 4 : Copy sample.txt from /tmp to /opt/devops
```bash
cp /tmp/sample.txt /opt/devops/
```
Verify
```bash
ls -l /opt/devops/
```
You should see:
```bash
sample.txt
```
### Step 5 : Create the media container with volume mapping
```bash
sudo docker run -d --name media -v /opt/devops:/usr/src nginx:latest
```
### Step 6 : Verify that the container is running
```bash
docker ps
```
Also verify the volume mapping
```bash
docker inspect media
```
You can also verify sample.txt inside the container
```bash
docker exec media ls -l /usr/src/
```
---
Task Completed
