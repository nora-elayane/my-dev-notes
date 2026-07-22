Here is the markdown formatted version:

# Git Advanced Concepts

---

## 1. Environment Rules (`.gitignore` & `.gitattributes`)
* **`.gitignore`**: Prevents untracked files (logs, dependencies, secrets) from entering history.
* **`.gitattributes`**: Enforces system settings like LF line endings (`*.sh text eol=lf`) and binary tags (`*.png binary`).

![Git Config](https://images.unsplash.com/photo-1555066931-4365d14bab8c?auto=format&fit=crop&w=600&q=80)

---

## 2. Large File Storage (Git LFS)
Replaces huge binary assets with lightweight text pointers inside Git, storing actual files on an external server.

```bash
git lfs install
git lfs track "*.psd"
git lfs ls-files

```

---

## 3. Commit Signing (GPG)

Cryptographically verifies your identity, displaying a **Verified** badge on GitHub/GitLab.

```bash
gpg --full-generate-key
git config --global user.signingkey <KEY_ID>
git commit -S -m "Signed commit"

```

---

## 4. Cherry-picking & Patches

* **Cherry-pick**: Copies specific commits from one branch to another (`git cherry-pick <hash>`).
* **Patch**: Shares changes as portable files (`git format-patch -1 <hash>` / `git am file.patch`).

---

## 5. Conflict Resolution

Occurs when opposing edits hit the same lines. Resolve manual markers (`<<<<<<<`, `=======`, `>>>>>>>`), stage, and commit.

```bash
git merge feature
# Edit conflicts
git add . && git commit

```

---

## 6. Automation & Hooks

Scripts in `.git/hooks/` triggered by lifecycle actions (e.g., `pre-commit` runs linter before committing).

---

## 7. Submodules & Remotes

* **Submodules**: Embed external repos while keeping history separate (`git submodule add <url>`).
* **Remotes**: Link multiple remote targets like forks or backups (`git remote add upstream <url>`).

---

## Quick Reference

| Feature | Primary Command / File | Use Case |
| --- | --- | --- |
| **Ignore** | `.gitignore` | Exclude temporary files. |
| **Attributes** | `.gitattributes` | Normalize line endings. |
| **LFS** | `git lfs track "*.zip"` | Manage large media/data. |
| **Signing** | `git commit -S` | Verify author identity. |
| **Submodules** | `git submodule add` | Embed external projects. |

```

```
