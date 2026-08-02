## Docker Network

### Description

The Nautilus DevOps team needs to set up several docker environments for different applications. One of the team members has been assigned a ticket where he has been asked to create some docker networks to be used later. Complete the task based on the following ticket description:

1. Create a docker network named as beta on App Server 3 in Stratos DC.

2. Configure it to use bridge drivers.

3. Set it to use subnet 172.168.0.0/24 and iprange 172.168.0.0/24.

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
### Step 2: Check the current networks in Docker setup

```bash
docker network ls
```
<img width="403" height="105" alt="image" src="https://github.com/user-attachments/assets/a337b513-8590-45ea-b02b-7976e8aa81ce" />

### Step 3: Add the beta network as per the task

```bash
docker network create beta --driver=bridge --subnet=172.168.0.0/24 --ip-range=172.168.0.0/24
```
### Step 4: Verify if the beta network is added in Docker
```bash
docker network ls
```
<img width="409" height="125" alt="image" src="https://github.com/user-attachments/assets/51c1cfad-e283-4d4f-9c10-06bb9946d8ba" />

---
Task Completed
