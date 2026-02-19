Git CheatSheet

Theres a couple of things I learned which I havent time to fully write down now.. to be completed..
git config --global core.editor "code --wait"

Version Control:
A system that tracks changes to files over time, allowing you to recall specific versions later
Enables multiple people to work on the same project without overwriting each other's work.

Git:A distributed version control system created by Linus Torvalds in 2005.

Core concepts:

Repository (Repo)

A folder/directory that Git is tracking
Contains all your project files plus a hidden .git folder with all version history
Can be local (on your computer) or remote (on GitHub, GitLab, etc.)

Commits

A snapshot of your project at a specific point in time
Each commit has a unique ID (SHA hash), author, timestamp, and message
Think of commits as save points in a video game
Best practice: Make small, focused commits with clear messages

Branches

Independent lines of development within the same repository
main (or master) is typically the default/primary branch
Create branches to work on features, fixes, or experiments without affecting the main code
Branches are lightweight and cheap to create in Git

HEAD

A pointer to your current location in the Git history
Usually points to the latest commit on your current branch
When you switch branches, HEAD moves to point to that branch

The Three States of Files
Working Directory

The actual files you see and edit on your computer
Untracked changes live here

Staging Area (Index)

A middle ground where you prepare commits
You choose which changes to include in the next commit
Allows you to commit only specific files or even specific parts of files

Repository

Where committed snapshots are permanently stored
The .git directory contains the complete history

Essential Commands
Setup & Configuration

git config --global user.name "Your Name" - Set your name
git config --global user.email "you@email.com" - Set your email
git init - Create a new Git repository in the current folder
git clone <url> - Download a remote repository to your computer

Basic Workflow

git status - See which files are modified, staged, or untracked
git add <file> - Stage specific files for commit
git add . - Stage all changes in current directory
git commit -m "message" - Create a commit with staged changes
git log - View commit history
git diff - See unstaged changes

Branching & Merging

git branch - List all branches
git branch <name> - Create a new branch
git checkout <branch> - Switch to a different branch
git checkout -b <name> - Create and switch to new branch in one command
git merge <branch> - Merge another branch into your current branch
git branch -d <name> - Delete a branch

Remote Repositories

git remote add origin <url> - Connect your local repo to a remote
git push origin <branch> - Upload your commits to the remote
git pull - Download and merge changes from the remote
git fetch - Download changes without merging them

Undoing Changes

git checkout -- <file> - Discard changes in working directory
git reset HEAD <file> - Unstage a file
git reset --soft HEAD~1 - Undo last commit, keep changes staged
git reset --hard HEAD~1 - Undo last commit, discard all changes (dangerous!)
git revert <commit> - Create a new commit that undoes a previous commit

Common Workflows
Feature Branch Workflow

Create a branch for your feature: git checkout -b feature-name
Make changes and commit: git add . then git commit -m "message"
Push to remote: git push origin feature-name
Create a pull request for review
Merge into main after approval
Delete the feature branch

Fixing Merge Conflicts

Occur when Git can't automatically merge changes
Git marks conflicts in files with <<<<<<<, =======, >>>>>>>
Manually edit files to resolve conflicts
Stage resolved files with git add
Complete the merge with git commit
