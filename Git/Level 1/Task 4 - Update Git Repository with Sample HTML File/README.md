## Update Git Repository with Sample HTML File

### Description

The Nautilus development team has initiated a new project development, establishing various Git repositories to manage each project's source code. Recently, a repository named /opt/news.git was created. The team has provided a sample index.html file located on the jump host under the /tmp directory. This repository has been cloned to /usr/src/kodekloudrepos on the storage server in the Stratos DC.



Copy the sample index.html file from the jump host to the storage server placing it within the cloned repository at /usr/src/kodekloudrepos/news.

Add and commit the file to the repository.

Push the changes to the master branch.

----

Step 1: Copy index.html file to the Storage server

```bash
ls -l /tmp/index.html
sudo scp /tmp/index.html natasha@ststor01:/usr/src/kodekloudrepos/news/
```

step 2: Verify the file has been copied on the storage server

```bash
ls -l /usr/src/kodekloudrepos/news/index.html
```
Go into the repository:
```bash
cd /usr/src/kodekloudrepos/news
```
Check the branch:
```bash
git branch
```

Step 3: Add and Commit

```bash
git add index.html
git commit -m "Add sample index.html"
```

Step 4: Push to master
```bash
git push origin master
```

Step 5: Verify
```bash
git status
git log --oneline -1
```

You want the latest commit to show your Add sample index.html commit and git status to be clean.

---
Task Completed
