# Git Cheatsheet

#### Purpose

This is cheatsheet is for the benefit of myself and others. It will list and define the use cases of both simple and advanced git commands.

#### Appendix

[Configuration](#CONFIGURATION)<br/>
[Initializing a Repository](#initializing-a-repository)<br/>
[Checking Repository Status & History](#checking-repository-status--history)<br/>
[Adding Files to Staging](#adding-files-to-staging)<br/>
[Removing Staged Changes (Before Commiting)](#removing-staged-changes-before-commiting)<br/>
[Commiting What's in the Index](#commiting-whats-in-the-index)<br/>
[Removing Commited Changes](#removing-commited-changes)<br/>
[Removing Commits from Branch](#removing-commits-from-branch)<br/>
[Switching to Previous Commits](#switching-to-previous-commits)<br/>
[Creating and Deleting Branches](#creating--deleting-branches)<br/>
[Merging](#merging)<br/>
[Fetching Changes](#fetching-changes)<br/>
[Pushing a Change](#pushing-a-change)<br/>
[Cloning Repositories](#cloning-repositories)<br/>
[Adding a Remote Repository](#adding-a-remote-repository)<br/>
[Github Pages](#github-pages)

### The Cheatsheet

---

### CONFIGURATION

These commands are for configuring git after it's already been setup.

| Command        | Description   | 
| ------------- | ------------- | 
| `git config --global user.name "Your Name"`      | Set global username in git configuration file. |
| `git config --global user.email "your_email@whatever.com"`      | Set global git email in git configuration.  |
| `git config --global -e` | Opens your `.gitconfig` file no matter what directory you're currently in.

### INITIALIZING A REPOSITORY

| Command        | Description   | 
| ------------- | ------------- | 
| `git init`      | Creates a git repository by adding a hidden `.git` file in the current directory. | 

### CHECKING REPOSITORY STATUS & HISTORY

| Command        | Description   | 
| ------------- | ------------- | 
| `git status`      | Lists all modified files since the last commit that havn't been staged in the index for commit, and files currently in the index ready to be commited. |
| `git diff`      | Show detailed readout of what has changed in each file since the last commit. |
| `git log`      | Shows the history of commits in the repository. |

### ADDING FILES TO STAGING

| Command        | Description   | 
| ------------- | ------------- | 
| `git add <file_name>`      | Adds a modified file to the index. | 
| `git add .`      | Adds all modified files in the current directory to the index. | 
| `git add -A` | Adds all modified files _no matter where you are in the repositroy tree_ to the index.     | 

### REMOVING STAGED CHANGES (BEFORE COMMITING)

| Command        | Description   | 
| ------------- | ------------- | 
| `git reset HEAD <file_name>` | Resets the staging area to whatever is in the HEAD (aka the last commit). |


### COMMITING WHAT'S IN THE INDEX 

| Command        | Description   | 
| ------------- | ------------- | 
| `git commit -m "message goes here"` | Commits what's staged in the index to the repository. | 
| `git commit --amend -m "message goes here"` | Amends additional staged changes to the previous commit | 

### REMOVING COMMITED CHANGES

| Command        | Description   | 
| ------------- | ------------- | 
| `git revert HEAD` | Reverts the very last commit made to the repository with the option for a message. |
| `git revert HEAD --no-edit` | Reverts the very last commit made to the repository with no message. |

### REMOVING COMMITS FROM BRANCH

| Command        | Description   | 
| ------------- | ------------- | 
| `git reset --hard <commit_hash>` | Resets the current branch back to the the given commit hash. The --hard parameter indicates that the working directory should be updated to be consistent with the new branch head.|


### SWITCHING TO PREVIOUS COMMITS

| Command        | Description   | 
| ------------- | ------------- | 
| `git checkout <commit_hash>` | Checkouts out a version of the repository at the given commit hash. |
| `git tag <tag_name>` | Adds a tag to the current version of the repository. |
| `git tag` | Shows all the current tags  in the repository. |
| `git tag -d <tag_name>` | Removes the given tag name from it's associated commit hash. |
| `git checkout <tag_name>` | Checkout a version of the repository by the given tag name instead of the commit hash. |

### CREATING & DELETING BRANCHES

| Command        | Description   | 
| ------------- | ------------- | 
| `git branch <branch_name>` | Creates a new branch with the given branch name. | 
| `git checkout -b <branch_name>` | Creates a new branch with the the given branch name and switches to it. | 
| `git branch --track <local_branch> <origin_branch>` | Adds a local branch that tracks a remote branch. | 
| `git branch` | Lists all available branches to checkout. | 
| `git branch -a` | Lists all branches, including remote ones. | 
| `git branch -d <branch_name>` | Deletes the given branch. Make sure you don't run this while in the given branch.  | 

### MERGING

| Command        | Description   | 
| ------------- | ------------- | 
| `git merge <branch_name>` | Merges changes from the specified branch in to the current branch. Running this periodically | 
| `git rebase <branch_name>` | Merges changes and commit history fin the current branch from the specified branch. | 

### FETCHING CHANGES

| Command        | Description   | 
| ------------- | ------------- | 
| `git fetch` | Pulls in changes from a remote repository, but NOT the commit history. In order to merge the changes, must run `git merge origin/master`. | 
| `git pull` | Pulls and merges in changes from a remote repository. | 

### PUSHING A CHANGE


| Command        | Description   | 
| ------------- | ------------- | 
| `git push <repo_name> master` | Pushes the last commit in the local repository to the remote repository. | 

### CLONING REPOSITORIES

| Command        | Description   | 
| ------------- | ------------- | 
| `git clone <repo_to_clone> <new_repo_name>` | Clones (copies) a local or remote repository | 


### ADDING A REMOTE REPOSITORY

| Command        | Description   | 
| ------------- | ------------- | 
| `git remote add <remote_repo>` | Points a local repository at a remote one. | 


### GITHUB PAGES

The following commands should be run in order for a quick push to GitHub pages.

| Order | Command        | Description   | 
|-----| ------------- | ------------- | 
| 1a | `git checkout -b gh-pages` | Creates new `gh-pages` branches and checks it out if the branch isn't already created. | 
| 1b | `git checkout gh-pages` | Switches to `gh-pages` branch | 
| 2 | `git rebase master` | Brings GH Pages up to date with master. | 
| 3 | `git push origin gh-pages` | Pushes commited changes to GitHub Pages. | 
| 4 | `git checkout master` | Switches back to 	`master` | 
