# Git & GitHub Master Guide: From Scratch to Push

This guide is designed to take you from absolute zero (installation) to confidently managing files, commits, and pushing your MVC projects to GitHub.

---

## 1. System Installation

Before Git can act as your "time machine," you must install it on your Linux Mint system.

* **Install Git via Terminal:**
  ```bash
  sudo apt update
  sudo apt install git -y

---

## 2. Essential Global Configuration

Configure your identity so your contributions on GitHub are properly registered to your name and email.

* **Set your Username:**
```bash
git config --global user.name "Nora Elayane"

```


* **Set your Email:**
```bash
git config --global user.email "noraelayane44@gmail.com"

```


* **Cache Your Credentials (No more typing passwords):**
```bash
git config --global credential.helper store

```


*Saves your Personal Access Token locally on your machine. You will only have to enter it once on your next push, and Git will remember it forever.*

---

## 3. Initializing a Local Repository

To start tracking a folder, you must initialize Git inside it.

* **Navigate to your project directory (in terminal):**
```bash
cd /var/www/html/smart_auto_ecole/

```


*(Note: If you use the terminal inside VS Code, it automatically drops you in this folder!)*
* **Initialize Git:**
```bash
git init

```


*Creates a hidden `.git` folder inside your project. This is the "brain" of Git that watches everything.*

---

## 4. The Three States of Git

Before files reach GitHub, they live in three logical areas locally:

| State / Area | Description |
| --- | --- |
| **Working Directory** | Files you are actively modifying or creating in VS Code. |
| **Staging Area** | The "packing bag." Where files sit once they are prepared for a snapshot. |
| **Local Repository** | The local database where your permanently recorded commits are stored. |

### Core Stage Commands:

* **Check current status:**
```bash
git status

```


*Shows which files are modified, staged, or completely untracked.*
* **Stage all files:**
```bash
git add .

```


*Moves all modifications and new files to the Staging Area. Use `git add <filename>` to stage just one file.*
* **Take a Snapshot (Commit):**
```bash
git commit -m "Create database connection"

```


*Permanently records your staged changes locally with a descriptive message.*

---

## 5. Connecting and Pushing to GitHub

Upload your local commits to the cloud.

* **Link your local project to GitHub:**
```bash
git remote add origin [https://github.com/nora-elayane/auto-ecole-mvc-project.git](https://github.com/nora-elayane/auto-ecole-mvc-project.git)

```


*Creates a shortcut alias named `origin` pointing to your remote GitHub repository.*
* **Change default branch to main:**
```bash
git branch -M main

```


* **Upload (Push) your commits:**
```bash
git push -u origin main

```


*Uploads your local history to GitHub. The `-u` flag configures your branch to track `origin/main` so that you only have to write `git push` in the future.*
* **How to fix typo in GitHub URL:**
```bash
git remote remove origin
git remote add origin <correct-url>

```



---

## 6. Daily CRUD Operations (Modify, Delete, Retrieve)

### Modifying Files

1. Edit files as usual in VS Code.
2. Check changes using `git status`.
3. Run `git add .`.
4. Run `git commit -m "Updated login validation logic"`.
5. Run `git push`.

### Deleting Files

* **Delete and stop tracking a file:**
```bash
git rm filename.txt
git commit -m "Remove obsolete file"
git push

```


*If you delete files manually inside VS Code, running `git add .` followed by `git commit` automatically registers the deletions.*

### Retrieving Files

* **Download a new project from GitHub:**
```bash
git clone <repository-url>

```


* **Pull latest updates (Sync down from cloud):**
```bash
git pull

```



---

## 💡 The Standard Daily Workflow

Make this 5-step loop your daily coding habit:

1. **`git pull`** — Sync any outside changes to your local machine.
2. *Write, build, and edit code inside VS Code.*
3. **`git add .`** — Stage your completed tasks.
4. **`git commit -m "Describe your progress"`** — Lock in your snapshot locally.
5. **`git push`** — Send your progress safely to GitHub.