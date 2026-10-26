### Git Merge Branches
----

#### Description

The Nautilus application development team has been working on a project repository /opt/ecommerce.git. 

This repo is cloned at /usr/src/kodekloudrepos on storage server in Stratos DC. They recently shared the following requirements with DevOps team:


Create a new branch nautilus in /usr/src/kodekloudrepos/ecommerce repo from master and copy the /tmp/index.html file (present on storage server itself) into the repo. 

Further, add/commit this file in the new branch and merge back that branch into master branch. Finally, push the changes to the origin for both of the branches.

----

#### SSH into the storage server


#### Step 1: Navigate to the repository

```bash
cd /usr/src/kodekloudrepos/ecommerce
```
Check the current Git status and branches:

```bash
git status
git branch -a
git remote -v
```

#### Step 2: Create the nautilus branch from master

```bash
git checkout master
```

Create and switch to the new branch:

```bash
git checkout -b nautilus
```
This creates nautilus from master


#### Step 3: Copy index.html into the repository

```bash
cp /tmp/index.html /usr/src/kodekloudrepos/ecommerce/
```

Verify:
```bash
ls -l index.html
git status
```
You should see index.html as an untracked or modified file.


#### Step 4: Add and commit the file

```bash
git add index.html
```

Commit the changes:

```bash
git commit -m "Add index.html to ecommerce repository"
```

Verify:
```bash
git log -1 --oneline
```

#### Step 5: Push the nautilus branch to origin

```bash
git push -u origin nautilus
```
This pushes the new branch and its commit to /opt/ecommerce.git.


#### Step 6 : Merge nautilus into master

```bash
git checkout master
```

Merge the changes:
```bash
git merge nautilus
```

#### Step 7: Push master to origin

```bash
git push origin master
```
This updates the remote master branch with the committed index.html.


#### Step 8: Verify the changes

```bash
git branch -a
```

Check commit history:
```bash
git log --oneline --graph --all --decorate
```

Verify the file:
```bash
ls -l index.html
```

Verify both remote branches point to the same commit:
```bash
git ls-remote origin refs/heads/master refs/heads/nautilus
```
Both branches should have the same commit hash if no other changes were made.

----
Task Completed



