# Git & GitHub
## What is Git
**Git** is a version control system.
It helps you track changes in your code, go back to previous version, and work on different feature safely.
## What is GitHub
**GitHub** is an online platform that uses git.
It lets you store your code on the internet, share with others, and work together as a team.

--- 


# Steps to create git Reposotory


## Step 1: Prerequisited
- You have created GitHub account.
- You have configure your ssh connection.
- You have installed
  - git
  - VS code (optional but recommended)

## Step 2: Create github reposotory using GitHub UI
 - Go to your profile.
 - Click on repository.
 - Click on New, to create a new repo.

## Step 3: Create a Project Folder
 - Create folder in your local system.
 - Open that folder in vs code or terminal.

### Step 4: git commands

--- 
```bash
touch README.md # To create an empty README.md file. [use nano or vim editor to edit the REAADME.md file.]
git init    # Initialised the git repo.
git status  # To check the status of created repo.
git add .   # Add the file into staging stage.
git status  # Check the status of workingg directory.
git commit -m "Added README.md" # To commit the changes on working directory.
git status
git branch  # list the branch
git remote add origin git@github.com:ramjan-raeen/git-commands.git  # add alias to the github/remote reposittory to push and fetch. [note: replace with your created github repo]
git remote -v   # list the  remote github repo
git push -u origin main # to push the changes to your github repo. [Note: flage -u uses first time]
```

# Create feature branch and contribute/merge to main branch
```bash
git branch  # To list the existing branch.
git checkout -b feature # To create feature branch and switch to feature branch. [note: asterisk denote your active branch]
git add .   # add you changes to working directory
git commit -m "Create feature branch and contribute/merge to main branch"   # commit the changes
git switch main # switch from feature branch to main branch.
git merge feature   # merge feature branch to main branch. [Note: to merge branch b into a. first switch to a branch and merge it.]
git diff origin/main..main  # To see, what changes in your local main branch as compare to remote's main branch or github repo.
git log origin/main..main   # To see the log differences between local main and remote main.
git push origin main    # It'll push local main changes to your remote main or github repo. You can open and see changes.
```
