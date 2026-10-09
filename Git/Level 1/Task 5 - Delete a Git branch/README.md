## Delete a Git branch

### Description

The Nautilus developers are engaged in active development on one of the project repositories located at /usr/src/kodekloudrepos/beta. 

During testing, several test branches were created, and now they require cleanup. Here are the requirements provided to the DevOps team:

On the Storage server in Stratos DC, delete a branch named xfusioncorp_beta from the /usr/src/kodekloudrepos/beta Git repository.

---

Step 1: Navigate to the repository

```bash
cd /usr/src/kodekloudrepos/beta
```

Step 2: Verify the branch exists

```bash
git branch
```

Step 3: Switch to another branch
You cannot delete the branch while it is checked out.

```bash
git checkout master
```

Step 4: Delete the branch

```bash
git branch -d xfusioncorp_beta
```

Step 5: Verify deletion

```bash
git branch
```

---
Task Completed
