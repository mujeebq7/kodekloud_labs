## Set Up Git Repository on Storage Server

### Description

The Nautilus development team has provided requirements to the DevOps team for a new application development project, specifically requesting the establishment of a Git repository. Follow the instructions below to create the Git repository on the Storage server in the Stratos DC:

Utilize yum to install the git package on the Storage Server.
Create a bare repository named /opt/official.git (ensure exact name usage).

---

Step 1: Install Git
On storage server, run:

```bash
yum install git -y
```

Step 2: Create the bare repository
```bash
git init --bare /opt/official.git
```

Step 3: Verify
```bash
ls -ld /opt/official.git
```

A bare Git repository will contain directories/files such as HEAD, config, objects, refs, and hooks.

---
Task Completed
