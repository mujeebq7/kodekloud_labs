## Create a User with Non-interactive Shell

### Description

To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires a creation of the user with a non-interactive shell.
Here's your task:

Create a user named siva with a non-interactive shell on App server 3

---

## Prerequisites

- Linux server
- Root access

---

### Step 1: SSH into App Server 3
```bash
ssh user@stapp03
```
Become root if required:
```bash
sudo su
```
### Step 2: Create the user with non-interactive shell

```bash
useradd -s /sbin/nologin siva
```
Check part:
```bash
id siva
```
----
Why create a User with Non-Interactive Shell

You create a user with non-interactive shell when you want that account to run processes or own files, but not allow login or command execution.
In other words, the user exists for system or service use only.
