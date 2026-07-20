# 🛠️ Git Undo & Recovery: Ultimate Developer Guide

A comprehensive, visual reference guide for undoing mistakes, modifying history, and recovering lost work in Git. 

---

## 🔄 1. Git Revert: The Safe Undo
**Concept:** `git revert` undoes a previous commit by creating a **brand new commit** that does the exact opposite of the target commit. 
* **Best For:** Shared or public repositories. It keeps your existing commit history intact without altering the past.

### 📸 Visualizing Revert
```text
[Commit A] ---> [Commit B (Mistake)] ---> [Commit C] ---> [Commit D (Revert B)]
                                                                |
                                                      (Undoes changes of B)
```

### 💻 Essential Commands
| Command | What it Does |
| :--- | :--- |
| `git revert HEAD` | Reverts the very last commit. |
| `git revert <commit-hash>` | Reverts a specific older commit. |
| `git revert HEAD~2` | Reverts the commit that is 2 steps back from HEAD. |
| `git revert --no-edit` | Skips opening the text editor for the commit message. |

### 💡 Best Practice
Use `git revert` whenever you have already pushed your changes to GitHub or shared them with a team. It prevents history conflicts for others.

---

## ⏳ 2. Git Reset: Rewinding Time
**Concept:** `git reset` moves your current branch pointer (`HEAD`) backward to a previous commit. 
* **Warning:** It rewrites history! Only use it on **local** branches that haven't been pushed yet.

### 📸 Visualizing Reset Modes
```text
                     💡 [Commit A] <--- [Commit B] <--- [Commit C (HEAD)]
                                           |
                   Moved HEAD here --------+
                   
  • --soft  --> Keeps your work from B and C in the STAGING AREA (ready to commit).
  • --mixed --> Keeps your work from B and C in the WORKING DIRECTORY (unstaged).
  • --hard  --> Completely DELETES all changes from B and C.
```

### 💻 Essential Commands
| Command | Mode | Staged? | Working Dir Changes Kept? |
| :--- | :--- | :--- | :--- |
| `git reset --soft <commit>` | **Soft** | ✅ Yes | ✅ Yes |
| `git reset --mixed <commit>` | **Mixed (Default)** | ❌ No | ✅ Yes |
| `git reset --hard <commit>` | **Hard** | ❌ No | ❌ No (Destructive!) |
| `git reset <file>` | **Unstage** | ❌ No | ✅ Yes (Removes file from staging area) |

---

## ✏️ 3. Git Amend: Fixing the Immediate Past
**Concept:** `git commit --amend` modifies the most recent commit instead of creating a new one. It is perfect for fixing small typos, updating a message, or adding forgotten files.

### 📸 Visualizing Amend
```text
[Commit A] ---> [Commit B (Forgot a file)] + (amend) ---> [Updated Commit B ✨]
```

### 💻 Common Workflows

#### A. Change the Last Commit Message
```bash
git commit --amend -m "Your new corrected commit message"
```

#### B. Add a Forgotten File to the Last Commit
```bash
git add forgotten-file.txt
git commit --amend --no-edit
```

#### C. Remove an Accidental File from the Last Commit
```bash
git reset HEAD^ -- unwanted-file.txt
git commit --amend --no-edit
```

---

## ⛓️ 4. Git Rebase: Cleaning Up History
**Concept:** Rebasing moves or reapplies a sequence of commits onto a new base commit to maintain a clean, linear timeline.

### 📸 Visualizing Rebase
```text
Before Rebase:
main:    [A] ---> [B]
feature:           └───> [C] ---> [D]

After 'git rebase main':
main:    [A] ---> [B] ---> [C'] ---> [D'] (Linear History!)
```

### 💻 Essential Commands
* **Basic Rebase (Bring feature branch up-to-date with main):**
  ```bash
  git checkout feature-branch
  git rebase main
  ```
* **Interactive Rebase (Clean up the last 3 commits before sharing):**
  ```bash
  git rebase -i HEAD~3
  ```

### ⚙️ Interactive Actions
When the text editor opens, you can change the word `pick` to:
* **`pick`**: Keep the commit as is.
* **`reword`**: Keep the commit but change its message.
* **`squash`**: Combine this commit into the previous one (great for merging minor fixes).
* **`drop`**: Completely remove the commit.

### ⚠️ Conflict Handling
If a conflict happens during a rebase:
1. Fix the files manually.
2. Stage them: `git add <fixed-file>`
3. Continue: `git rebase --continue`
* *Need to abort?* Run `git rebase --abort` to return everything exactly to how it was before.

---

## 🛡️ 5. Git Reflog & Recovery: The Ultimate Safety Net
**Concept:** `git reflog` is Git's internal diary. It tracks every single place `HEAD` has pointed, even if you did a `git reset --hard` or deleted a branch. **If it was committed, Reflog can save it.**

### 📸 Visualizing Reflog Recovery
```text
[You ran git reset --hard and lost commits!]
1. Run: git reflog
2. Find the position state before the reset (e.g., HEAD@{2})
3. Run: git reset --hard HEAD@{2} ---> 🚀 Magic! Everything is back.
```

### 💻 Recovery Workflows

#### A. Restore a Deleted Branch
```bash
# 1. Look through the log to find the last commit hash of the deleted branch
git reflog

# 2. Recreate the branch at that exact commit
git checkout -b <branch-name> <commit-hash>
```

#### B. Recover a Deleted or Modified File (Before Commit)
If you made changes to a file or deleted it locally and want to reset it back to the state of the last commit:
```bash
git restore filename.txt
```

---

## 🧠 Quick Decision Cheat Sheet

```text
❓ What do you want to do?
├── I want to undo a commit already pushed to GitHub ──> Use 'git revert'
├── I want to undo a local commit and keep my code   ──> Use 'git reset --soft'
├── I want to fix the commit message I just wrote   ──> Use 'git commit --amend'
├── I completely broke my local files and want out    ──> Use 'git reset --hard'
└── I ran a bad command and lost my work completely  ──> Use 'git reflog'
```

---
*💡 Part of Nora's Development Notes Repository - Keep it clean, keep it structured.*
