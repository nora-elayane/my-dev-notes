# Git & GitHub Workflow Guide: Forking & Pull Requests

This guide covers the essential workflow for contributing to external repositories on GitHub using the `Fork` and `Pull Request` model, based on the W3Schools Git tutorial.

---

## 🚀 1. Introduction to Collaboration
At the heart of Git is collaboration. However, Git does not allow you to add code to someone else's repository without explicit access rights. 

To suggest changes to a public project, you follow a three-step cycle:
1. **Copy** the repository (**Fork**).
2. **Make changes** to it locally (**Clone & Commit**).
3. **Suggest** those changes to the original repository (**Pull Request**).

---

## 🍴 2. Forking a Repository
A **fork** is a personal copy of someone else's repository that lives on your GitHub account. Modifying it won't affect the original project until you explicitly request a merge.

> ℹ️ *Note: `fork` is not a native Git command. It is a feature provided by GitHub and other hosting platforms.*

### Steps to Fork:
1. Navigate to the target public repository: [w3schools-test/w3schools-test.github.io](https://github.com/w3schools-test/w3schools-test.github.io).
2. Click the **Fork** button in the top-right corner of the GitHub interface.

---

## 👥 3. Cloning Your Fork Locally
Once you have your own fork on GitHub, you need to clone it to your local machine to make your development modifications.

1. Go to **your personal fork** on GitHub.
2. Click the green **Code** button and copy the HTTPS/SSH URL.
3. Open your terminal or Git Bash and run:

```bash
git clone [https://github.com/your-username/w3schools-test.github.io.git](https://github.com/your-username/w3schools-test.github.io.git)

```

This downloads a complete copy of the project, including all its version history, into a new local directory.

---

## ⚙️ 4. Configuring Remotes

By default, Git points your local repository back to your fork as `origin`. To stay synchronized with the original project (the upstream source), you need to configure your tracking remotes properly.

Following professional Git naming conventions, your personal fork should be named `origin` and the original project should be named `upstream`.

### Step-by-Step Terminal Setup:

1. Check your existing remote configuration:
```bash
git remote -v

```


2. Rename the default tracking configuration to `upstream`:
```bash
git remote rename origin upstream

```


3. Add your personal GitHub fork URL as the new `origin`:
```bash
git remote add origin [https://github.com/your-username/w3schools-test.github.io.git](https://github.com/your-username/w3schools-test.github.io.git)

```


4. Verify your final setup matches this structure:
```bash
git remote -v
# Updates will show:
# origin   [https://github.com/your-username/w3schools-test.github.io.git](https://github.com/your-username/w3schools-test.github.io.git) (fetch)
# origin   [https://github.com/your-username/w3schools-test.github.io.git](https://github.com/your-username/w3schools-test.github.io.git) (push)
# upstream [https://github.com/w3schools-test/w3schools-test.github.io.git](https://github.com/w3schools-test/w3schools-test.github.io.git) (fetch)
# upstream [https://github.com/w3schools-test/w3schools-test.github.io.git](https://github.com/w3schools-test/w3schools-test.github.io.git) (push)

```



---

## 📤 5. Pushing Changes & Sending a Pull Request

After making visual or codebase updates within your local environment, you need to bundle your code modifications and submit them.

### Step 1: Stage and Commit locally

```bash
git add .
git commit -m "Add custom structured message to guestbook"

```

### Step 2: Push changes to your GitHub Fork

```bash
git push origin master

```

*(Replace `master` with `main` depending on your active primary branch).*

### Step 3: Open the Pull Request (PR)

1. Go back to your repository on GitHub. You will see a yellow banner: **"Compare & pull request"**.
2. Click it, fill out a title, and provide a polite description explaining your adjustments to the project administrators.
3. Click **Create pull request**.

---

## 🏁 6. Approval & Merging

Once sent, your Pull Request becomes visible to the project administrators on the original repository.

* **Conflict Resolution:** GitHub checks automatically if the changes can be cleanly merged (`No conflicts with base branch`).
* **Review:** Maintainers can add review comments or directly approve your code.
* **Merge:** Once approved, your commits are merged into the main `master`/`main` branch, making your contribution live!
"""

file_name = "git_fork_pull_request_guide.md"
with open(file_name, "w", encoding="utf-8") as f:
f.write(markdown_content)

print(f"File {file_name} generated successfully.")


```text?code_stdout&code_event_index=1
File git_fork_pull_request_guide.md generated successfully.




