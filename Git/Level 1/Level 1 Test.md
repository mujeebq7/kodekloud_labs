## Test

### Question 1

A couple of new Git repositories were created recently and this is still in progress. Recently a new requirement has emerged to create a repository on the storage server. Below are the details for this request.

Create and initialize a git repository at /home/sarah/story-blog-t1q4 on Storage server.

Let’s add a file named lion-and-mouse-t1q4.txt to our project inside /home/sarah/story-blog-t1q4, the file content must be A Lion lay asleep in the forest.

Use below credentials to SSH into the storage server and to complete this task.

Username: sarah
Password: S3cure321

### Answer

Step 1: Switch to Storage server

Step 2: Create and initialize the Git repository

```bash
sudo mkdir -p /home/sarah/story-blog-t1q4
sudo chown sarah:sarah /home/sarah/story-blog-t1q4
sudo -u sarah git -C /home/sarah/story-blog-t1q4 init
```

Step 3: Create the file with the required content

```bash
sudo -u sarah bash -c 'echo "A Lion lay asleep in the forest" > /home/sarah/story-blog-t1q4/lion-and-mouse-t1q4.txt'
```

Step 4: Verify the repository and file

```bash
sudo -u sarah git -C /home/sarah/story-blog-t1q4 status
cat /home/sarah/story-blog-t1q4/lion-and-mouse-t1q4.txt
```
Expected file content:
```bash
A Lion lay asleep in the forest
```
---

### Question 2

The Nautilus dev team is currently in the process of creating Git repositories, a new requirement has emerged to create a repository on the storage server. Below are the details for this request.


Create and initialise a git repository at /home/sarah/story-blog-t1q3 on Storage server.

### Answer

Step 1: Create the repository directory

```bash
sudo mkdir -p /home/sarah/story-blog-t1q3
```

Step 2: Set ownership to sarah

```bash
sudo chown sarah:sarah /home/sarah/story-blog-t1q3
```

Step 3: Initialize the Git repository

```bash
sudo -u sarah git -C /home/sarah/story-blog-t1q3 init
```

Step 4: Verify the repository

```bash
sudo -u sarah git -C /home/sarah/story-blog-t1q3 status
```
---

### Question 3

Sarah created a new file named notes-t1q9.txt under /home/sarah/story-blog-t1q9 repository where she plans to write down ideas about the story for personal purposes. She does not want git to track this file or share it with her team mates.

It is good that the file is untracked. But it is still under GIT's radar. If you run the git add . command, accidentally git will start to track this file.


Let's configure git to ignore this file permanently.

### Answer

Step 1: Navigate to the repository

```bash
cd /home/sarah/story-blog-t1q9
```

Step 2: Add the file to .gitignore

```bash
echo "notes-t1q9.txt" >> .gitignore
```

Step 3; Verify the configuration

```bash
cat .gitignore
git status
```
---

### Question 4

The Nautilus application development team was working on a git repository /usr/src/kodekloudrepos/media-t2q4 present on Storage server in Stratos DC. One of the developers mistakenly created a couple of files under this repository, but now they want to clean this repository without adding/pushing any new files. Find below more details:


Clean the /usr/src/kodekloudrepos/media-t2q4 git repository without adding/pushing any new files, make sure git status is clean.

### Answer

Step 1: Navigate to the repository

```bash
cd /usr/src/kodekloudrepos/media-t2q4
```

Step 2: Check the repository status

```bash
git status
```

Step 3: Preview untracked files and directories

```bash
git clean -nd
```

Step 4: Remove untracked files and directories

```bash
git clean -fd
```
-f forces removal
-d includes untracked directories

Step 5: Verify the repository is clean

```bash
git status
```
Expected output:
```bash
nothing to commit, working tree clean
```
---

### Question 5

One of the nautilus developers added some data under /usr/src/kodekloudrepos/media-t2q6 repository, however they later realised that there is a typo in one of the files. Let's fix the typo.


In the lion-and-mouse.txt file, LION is mis-spelt as LIOON. Please fix it and then commit the changes with a commit message: Fix typo in story title

### Answer

Step 1: Navigate to the repository

```bash
cd /usr/src/kodekloudrepos/media-t2q6
```

Step 2: Replace LIOON with LION

```bash
sed -i 's/LIOON/LION/g' lion-and-mouse.txt
```

Step 3: Verify the correction

```bash
grep -n 'LION' lion-and-mouse.txt
git diff
```

Step 4: Commit the change

```bash
git add lion-and-mouse.txt
git commit -m "Fix typo in story title"
```

Step 5: Verify the commit

```bash
git status
git log -1 --oneline
```
Test Ended


