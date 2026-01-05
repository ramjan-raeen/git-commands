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

# Create Pull Request and merge to main branch
## Step 1:
```bash
git branch -d feature   # To delete feature branch. [Note: make sure you're in main branch]
git checkout -b feature/PR  # To create another feature branch called feature/PR fo creating PR.
git brnach
git add .
git commit -m "Create Pull Request and merge to main branch"
git push -u origin feature/PR # push the feature/PR branch to remote github repo.
```
## Step 2:
- Go to your github repo.
- You'll see a message to create pull request for recently pushed branch.
- Click on Compare & pull request button.
- Add title and description.
- Click on Create pull request button.
- Now, you'll see Merge pull request button. Click on it.
- Finally, click on Confirm merge button.
- Now, your feature/PR branch is merged to main branch.
- You can delete the feature/PR branch by clicking on Delete branch button.

## Step 3:
```bash
git switch main  # switch to main branch.
git branch -d feature/PR  # delete the feature/PR branch locally.
git fetch origin mian # fetch the latest changes from remote main branch.
git diff main..origin/main  # see the differences between local main and remote main.
git log main..origin/main   # see the log differences between local main and remote main.
git merge origin/main  # merge the remote main branch to local main branch.
git pull origin main  # [Optional/Alternate of fetch & merge] pull the latest changes from remote main branch to local main branch.
git diff origin/main..main  # To see, what changes in your local main branch as compare to remote's main branch or github repo.
```

# Fork git repository from internet and contribute/merge to main branch of original repo
## Step 1: Fork git repository from internet
- Login through your github account.
- Navigate github repo which you want to fork.
- Click on fork button which will be available on top right corner.
## Step 2: clone and add feature
```bash
git clone git@github.com:raeen-ramjan/git-commands.git  # clone repo, which you just forked. [Note: replace with your forked repo]
cd git-commands # To inside folder
git remote -v # To see alias for remote github which you just forked.
git log --oneline # To logs of commits.
git remote add upstream git@github.com:ramjan-raeen/git-commands.git  # To add alias for original repo. [Note: replace with your original repo]
git remote -v
git checkout -b feature/Fork  # To create feature branch called feature/Fork.
git status
git add .
git commit -m "Fork git reposotory from internet and contribute/merge to main branch of original repo"
git push -u origin feature/Fork # Raise Pull Request.
```
## Step 3: Pull Request and merge to main branch
- Go to your github repo.
- You'll see a message to create pull request for recently pushed branch.
- Add title and description.
- Click on Create pull request button.
- choose, merged where to happen? feature to original repo or feature to forked repo?
- Code reviewer review your code and approved it.
- Now, you'll see Merge pull request button. Click on it.
- Finally, click on Confirm merge button.
- Now, your feature/PR branch is merged to main branch.
- You can delete the feature/PR branch by clicking on Delete branch button.





