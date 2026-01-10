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

# Revert vs Reset
- **Revert**: It undoes a specific commit by creating a new commit that reverses the changes made in the original commit. It is a safe way to undo changes because it preserves the commit history.
- **Reset**: It moves the current branch pointer to a specific commit, effectively discarding any commits that came after it. It can be used to undo changes, but it can also rewrite history, which can be dangerous if the commits have already been pushed to a shared repository.

Example:
you have three commits: A -> B -> C
- If you want to undo commit B using revert, you would create a new commit D that reverses the changes made in commit B. The commit history would look like this: A -> B -> C -> D
- If you want to undo commit B using reset, you would move the branch pointer back to commit A, effectively discarding commits B and C. The commit history would look like this: A

## Git Revert vs Reset commands
```bash
git revert <commit-hash>  # To revert a specific commit. The purpose of revert is to undo changes without rewriting history.

git reset --soft <commit-hash>  # To reset to a specific commit but keep changes in staging area. The purpose of --soft is the edit the last commit message.

git reset --mixed <commit-hash>  # To reset to a specific commit but keep changes in working directory. This is the default option. The purpose of --mixed is to unstage files and re-edit the files in working directory.

git reset --hard <commit-hash>  # To reset to a specific commit and discard all changes after that commit. The purpose of --hard is to discard all changes in working directory and staging area.
```

#  Fast-forward vs Cherry-pick
**Fast-forward**: A fast-forward happens when Git can move a branch pointer forward without creating a merge commit.
- No new commit is created
- History stays straight (linear)

## When is fast-forward possible?

**Only when:**

- main has no new commits

- feature is ahead of main

- main is an ancestor of feature

**Before Fast-Forward**

```bash 
# A --- B --- C   (main)
#             |
#             D --- E   (feature)
```

**After Fast-Forward**
```bash
# A --- B --- C --- D --- E   (main)
```
```bash
git switch main
git merge feature # git will automatically check fast-forward condition.
git merge --ff-only feature # you said, fast-forwad

```

# Cherry-pick
- Copies commit
- Creates a new commit ID
- History is not linear
“Pick one specific commit from another branch and apply it here.”

**Cherry-Before cherry-pick**

```bash
# A --- B --- C   (main)
#             |
#             D --- E   (feature)
```

 **Cherry-Before cherry-pick**
```bash
# A --- B --- C --- E'  (main)
#             |
#             D --- E   (feature)
```

```bash
git cherry-pick <commit-hash (E)>
```
## Use cherry-pick when:

- You need one fix, not full feature

- Backporting a bug fix

- Hotfix from another branch


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





