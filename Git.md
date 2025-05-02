# Git Commands for Beginners

Below is a comprehensive list of Git commands with explanations to help you understand their purpose and usage.

## 1. **Setup and Configuration**

### Initialize a Git Repository
```bash
git init
```
- **What it does**: Initializes a new Git repository in your project folder. This is the first step to start tracking your files with Git.

### Set Your Username
```bash
git config --global user.name "Your Name"
```
- **What it does**: Sets your name in Git's configuration. This name will appear in your commit history.

### Set Your Email
```bash
git config --global user.email "your.email@example.com"
```
- **What it does**: Sets your email in Git's configuration. This email will appear in your commit history.

### Check Configuration
```bash
git config --list
```
- **What it does**: Displays the current Git configuration, including username and email.

---

## 2. **Basic Commands**

### Clone a Repository
```bash
git clone <repository-url>
```
- **What it does**: Creates a local copy of a remote repository.

### Check Repository Status
```bash
git status
```
- **What it does**: Shows the current state of the working directory and staging area, including untracked and modified files.

### Add Files to Staging Area
```bash
git add <file-name>
```
- **What it does**: Stages a specific file for the next commit.

```bash
git add .
```
- **What it does**: Stages all changes (new, modified, or deleted files) in the current directory.

### Commit Changes
```bash
git commit -m "Your commit message"
```
- **What it does**: Saves the staged changes to the repository with a descriptive message.

---

## 3. **Branching and Merging**

### Create a New Branch
```bash
git branch <branch-name>
```
- **What it does**: Creates a new branch for development.

### Switch to a Branch
```bash
git checkout <branch-name>
```
- **What it does**: Switches to the specified branch.

### Create and Switch to a New Branch
```bash
git checkout -b <branch-name>
```
- **What it does**: Creates a new branch and switches to it immediately.

### Merge Branches
```bash
git merge <branch-name>
```
- **What it does**: Merges the specified branch into the current branch.

---

## 4. **Working with Remote Repositories**

### Add a Remote Repository
```bash
git remote add origin <repository-url>
```
- **What it does**: Links your local repository to a remote repository.

### Push Changes to Remote
```bash
git push origin <branch-name>
```
- **What it does**: Uploads your local branch changes to the remote repository.

### Pull Changes from Remote
```bash
git pull origin <branch-name>
```
- **What it does**: Fetches and integrates changes from the remote repository into your local branch.

---

## 5. **Undoing Changes**

### Unstage a File
```bash
git reset <file-name>
```
- **What it does**: Removes a file from the staging area without deleting its changes.

### Revert Changes in a File
```bash
git checkout -- <file-name>
```
- **What it does**: Discards changes in a file and restores it to the last committed state.

### Reset to a Previous Commit
```bash
git reset --hard <commit-hash>
```
- **What it does**: Resets the repository to a specific commit, discarding all changes after it.

---

## 6. **Viewing History**

### View Commit History
```bash
git log
```
- **What it does**: Displays the commit history of the repository.

### View Changes in a File
```bash
git diff <file-name>
```
- **What it does**: Shows the differences between the working directory and the staging area for a specific file.

---

## 7. **Tagging**

### Create a Tag
```bash
git tag <tag-name>
```
- **What it does**: Creates a tag for a specific commit, often used for marking releases.

### Push Tags to Remote
```bash
git push origin --tags
```
- **What it does**: Uploads all local tags to the remote repository.

---

## 8. **Advanced Commands**

### Stash Changes
```bash
git stash
```
- **What it does**: Temporarily saves changes that are not ready to be committed.

### Apply Stashed Changes
```bash
git stash apply
```
- **What it does**: Restores the most recently stashed changes.

### Delete a Branch
```bash
git branch -d <branch-name>
```
- **What it does**: Deletes a branch that has been merged.

---

This guide covers the essential Git commands to get you started. Practice these commands to become more comfortable with Git!  