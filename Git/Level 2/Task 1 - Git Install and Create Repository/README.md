### Git Install and Create Repository

#### Description

The Nautilus development team shared with the DevOps team requirements for new application development, setting up a Git repository for that project. Create a Git repository on Storage server in Stratos DC as per details given below:


Install git package using yum on Storage server.


After that, create/init a git repository named /opt/ecommerce.git (use the exact name as asked and make sure not to create a bare repository).

----

Step 1: Install Git using yum

```bash
yum install git -y
```

Verify the installation:

```bash
git --version
```

Step 2: Create the repository directory

```bash
mkdir -p /opt/ecommerce.git
```

Step 3: Initialize the Git repository

```bash
sudo git init /opt/ecommerce.git
```

Step 4: Verify the repository

```bash
cd /opt/ecommerce.git
```

Also verify the directory structure:

```bash
ls -la /opt/ecommerce.git
```
You should see a .git directory inside /opt/ecommerce.git.

----
Task Completed
