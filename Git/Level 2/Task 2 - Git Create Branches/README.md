### Git Create Branches
----

#### Description

Nautilus developers are actively working on one of the project repositories, /usr/src/kodekloudrepos/news. Recently, they decided to implement some new features in the application, and they want to maintain those new changes in a separate branch. Below are the requirements that have been shared with the DevOps team:


On Storage server in Stratos DC create a new branch xfusioncorp_news from master branch in /usr/src/kodekloudrepos/news git repo.


Please do not try to make any changes in the code.

----
Log into the storage server

Step 1: Navigate to the Git repository

```bash
cd /usr/src/kodekloudrepos/news
```

Step 2: Check existing branches

```bash
git branch
```
Verify that the master branch exists.

Step 3: Create the new branch from master

```bash
git branch xfusioncorp_news master
```

Step 4: Verify the new branch

```bash
git branch -a
```
You can also verify that both branches point to the same commit:

```bash
git rev-parse master
git rev-parse xfusioncorp_news
```
----

Task Completed

