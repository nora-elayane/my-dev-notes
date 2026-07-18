# Git Master Reference Guide

This clear, comprehensive guide covers Git essentials from setup to daily workflow—tailored for structured backend and MVC project development.

---

## 1. Installation & Global Configuration

Set up Git and establish your identity so contributions register properly to your GitHub account.

```bash
# 1. System Installation (Linux Mint / Debian)
sudo apt update && sudo apt install git -y
git --version # Verify installation

# 2. Set Identity Configurations
git config --global user.name "Nora Elayane"
git config --global user.email "noraelayane44@gmail.com"
git config --global init.defaultBranch main

# 3. Credentials & Editor Setup
git config --global credential.helper store          # Caches personal access token locally
git config --global core.editor "code --wait"        # Sets VS Code as default git editor

# 4. View Configuration Settings
git config --list

```

---

## 2. Initializing & Working Local Repositories

Git tracks file modifications through three sequential local zones:

| Zone / State | Command | Description |
| --- | --- | --- |
| **Working Directory** | — | Files you are actively writing or modifying in VS Code. |
| **Staging Area** | `git add` | The preparation zone or "packing bag" before taking a snapshot. |
| **Local Repository** | `git commit` | The permanent local database storing secure historical snapshots. |

### Essential Initialization Commands:

```bash
cd /path/to/your/project/     # Navigate to your development folder
git init                      # Creates a hidden .git tracker directory
git status                    # Checks current status (untracked, modified, staged files)

```

### Staging and Committing Changes:

```bash
git add <filename>            # Stages a single file
git add .                     # Stages all modifications and untracked files
git status                    # Confirms changes are ready to commit

# Take local snapshots
git commit -m "Your descriptive commit message"
git commit --amend --no-edit   # Modifies the last local commit without changing its message

```

### Unstaging Files:

```bash
git rm --cached <file>        # Unstages a file before your first initial commit
git restore --staged <file>   # Unstages a file after your repository has existing commits

```

---

## 3. Remote Synchronization (Pushing to GitHub)

Safely upload your local structural development history to a cloud repository on GitHub.

```bash
# Link local repository to a remote backend server
git remote add origin [https://github.com/nora-elayane/auto-ecole-mvc-project.git](https://github.com/nora-elayane/auto-ecole-mvc-project.git)

# Main Branch Pushing Setup
git branch -M main            # Renames default branch safely to main
git push -u origin main       # Pushes upstream (-u sets tracking forever, then use plain 'git push')

# How to correct a typo in your Remote URL
git remote remove origin
git remote add origin <correct-url>

```

---

## 4. Daily CRUD Operations (Modify, Delete, Sync)

### Modifying and Deleting Files:

```bash
git diff                      # Shows unstaged differences in your working directory
git diff --staged             # Shows changes currently saved inside the Staging Area

# Deleting and tracking removals
git rm filename.txt           # Removes a file from directory and registers deletion
git commit -m "Remove obsolete file"

```

*(Note: If files are manually deleted via VS Code sidebar, running `git add .` and committing will automatically process deletions).*

### Pulling & Cloning:

```bash
git clone <repository-url>    # Clones an entire existing repository from GitHub locally
git pull                      # Downloads and syncs outside remote history directly down to local branch

```

---

## 5. History, Stash & Advanced Quick Reference

### Git Logs (Viewing History):

```bash
git log                       # Full commit history logs
git log --oneline             # Displays a highly compressed single-line execution trace
git log --graph --oneline     # Renders a neat visual branch connection layout line

```

### Git Stash (Temporary Draft Storage):

```bash
git stash -u                  # Saves dirty working changes securely to structural sidebar memory
git stash list                # Displays saved hidden index state items
git stash pop                 # Re-applies changes and immediately wipes last stashed layout item

```

---

## 💡 The Professional Daily Coding Habit

Always follow this structured 5-step engineering loop for your clean workspace commits:

1. **`git pull`** — Sync any outside architectural changes down onto your local engine first.
2. *Write, build, and optimize backend structures inside VS Code.*
3. **`git add .`** — Stage all validated script adjustments.
4. **`git commit -m "Clear action summary"`** — Lock in secure architectural snapshots locally.
5. **`git push`** — Safely dispatch complete developments upstream to GitHub.


