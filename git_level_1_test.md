**Use below credentials to SSH into the storage server and to complete this task.**

Server Name: `ststor01`  
Username: `sarah`  
Password: `S3cure321`  
\
**Task 1 / 5**  
Sarah created a new file named `notes-t1q9.txt` under `/home/sarah/story-blog-t1q9` repository where she plans to write down ideas about the story for personal purposes. She does not want git to track this file or share it with her team mates.

It is good that the file is untracked. But it is still under GIT's radar. If you run the git add . command, accidentally git will start to track this file.

Let's configure git to ignore this file permanently.

Solution:
```
cd /home/sarah/story-blog-t1q9
echo "notes-t1q9.txt" > .gitignore
git add .
git commit -m "Created a .gitignore file and appended 'notes-t1q9.txt' for Git to ignore the text file"
```
\
**Task 2 / 5**  
A couple of new Git repositories were created recently and this is still in progress. Recently a new requirement has emerged to create a repository on the storage server. Below are the details for this request.

Create and initialize a git repository at `/home/sarah/story-blog-t1q4` on Storage server.

Let’s add a file named `lion-and-mouse-t1q4.txt` to our project inside `/home/sarah/story-blog-t1q4`, the file content must be A Lion lay asleep in the forest.

Solution:
```
mkdir -p /home/sarah/story-blog-t1q4 && cd $_
git init
echo "A Lion lay asleep in the forest" > lion-and-mouse-t1q4.txt
```
\
**Task 3 / 5**  
As developers are currently in the process of creating Git repositories, a new requirement has emerged to create a bare repository on the storage server. Below are the details for this request.

Create a bare repository named `/home/sarah/apps.git` on Storage server.

Solution:
```
mkdir -p /home/sarah/apps.git && cd $_
git init --bare .
```
\
**Task 4 / 5**  
The Nautilus application development team was working on a git repository `/usr/src/kodekloudrepos/apps-t2q4` present on Storage server in Stratos DC. One of the developers mistakenly created a couple of files under this repository, but now they want to clean this repository without adding/pushing any new files. Find below more details:

Clean the `/usr/src/kodekloudrepos/apps-t2q4` git repository without adding/pushing any new files, make sure git status is clean.

Solution:  
Use `git status` command to display the untracked file(s) in the staging area.
```
git status
git clean -d -x -f
git status
```
\
**Task 5 / 5**  
Nautilus developers are actively working on one of the project repositories, /usr/src/kodekloudrepos/apps-t2q1. Recently, they decided to implement some new features in the application, and they want to maintain those new changes in a separate branch. Below are the requirements that have been shared with the DevOps team:

On Storage server in Stratos DC create a new branch xfusioncorp_apps-t2q1 from master branch in /usr/src/kodekloudrepos/apps-t2q1 git repo.

Please do not try to make any changes in the code.

Solution:  
Use `git branch` command to list the branches.
```
cd /usr/src/kodekloudrepos/apps-t2q1
git branch
git checkout -b xfusioncorp_apps-t2q1 master
```
