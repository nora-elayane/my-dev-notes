## 🛠️ Git Cheat Sheet: Quick Reference

### 1. Installation & Setup

* **Install (Ubuntu/Debian):** `sudo apt-get install git`
* **Check Version:** `git --version`
* **Set Default Editor:** `git config --global core.editor "code --wait"`

### 2. Configuration

* **Set Identity:**
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

```


* **List Configs:** `git config --list`
* **Unset Config:** `git config --global --unset <setting>`

### 3. Initialize & Status

* **Initialize Project:** `git init`
* **Set Default Branch:** `git config --global init.defaultBranch main`
* **Check Status:** `git status`

### 4. Staging & Committing

* **Stage a File:** `git add <file>`
* **Stage All Changes:** `git add -A`
* **Unstage File (Before 1st Commit):** `git rm --cached <file>`
* **Unstage File (After 1st Commit):** `git restore --staged <file>`
* **Commit with Message:** `git commit -m "Your message"`
* **Amend Last Commit:** `git commit --amend --no-edit`

### 5. Git History & Logs

* **Short Log:** `git log --oneline`
* **Graph Log:** `git log --graph --oneline`
* **Show Unstaged Changes:** `git diff`
* **Show Staged Changes:** `git diff --staged`

### 6. Git Tagging (Releases)

* **Create Tag:** `git tag -a v1.0 -m "Version 1.0"`
* **Push Tags:** `git push origin --tags`
* **Delete Local Tag:** `git tag -d v1.0`

### 7. Git Stash (Temporary Storage)

* **Stash Changes:** `git stash -u`
* **List Stashes:** `git stash list`
* **Apply & Delete Last Stash:** `git stash pop`

### 8. Branching & Merging

* **Create Branch:** `git branch <branch-name>`
* **Switch Branch:** `git checkout <branch-name>`
* **Create & Switch Branch:** `git checkout -b <branch-name>`
* **Merge Branch:** `git merge <branch-name>`
* **Abort Merge:** `git merge --abort`

### 9. Built-in Help

* **Command Manual:** `git help <command>`
* **Quick Summary:** `git <command> -h`
