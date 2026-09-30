## Clone Git Repository on Storage Server

### Description

The DevOps team established a new Git repository last week, which remains unused at present. However, the Nautilus application development team now requires a copy of this repository on the Storage Server in the Stratos DC. Follow the provided details to clone the repository:


The repository to be cloned is located at /opt/media.git


Clone this Git repository to the /usr/src/kodekloudrepos directory. Perform this task using the natasha user, and ensure that no modifications are made to the repository or existing directories, such as changing permissions or making unauthorized alterations.

---

Step 1: Clone the repository

On the Storage Server, perform the clone as the natasha user:

```bash
sudo -u natasha git clone /opt/media.git /usr/src/kodekloudrepos/media
```

Step 2: Verify the repository

```bash
sudo -u natasha git -C /usr/src/kodekloudrepos/media status
```
You should see that the repository is clean and on its default branch.

Important: Do not change ownership, permissions, or modify /usr/src/kodekloudrepos beyond cloning the repository.

---
Task Completed
