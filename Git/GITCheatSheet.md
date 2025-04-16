Sure! Here's a **detailed Git Command Reference (Cheat Sheet)** with **extensive explanations** of key Git commands, grouped by category. This is ideal as a quick yet deep guide for developers, DevOps professionals, or anyone using Git daily.

---

# 📘 **Git Command Reference (with Detailed Descriptions)**

---

## 🧱 **1. Git Configuration**

| Command | Description |
|--------|-------------|
| `git config --global user.name "Your Name"` | Sets your name for all Git commits. |
| `git config --global user.email "you@example.com"` | Sets your email for all Git commits. |
| `git config --list` | Displays all Git configurations in use. |
| `git config --global core.editor "vim"` | Sets the default editor for Git (can be `nano`, `code`, `subl`, etc.). |
| `git config --global alias.st status` | Creates a shortcut alias (`git st` will run `git status`). |

---

## 📁 **2. Repository Setup**

| Command | Description |
|--------|-------------|
| `git init` | Initializes a new Git repository in the current directory. |
| `git clone <url>` | Clones a remote repository (like GitHub) to your local machine. |
| `git clone <url> <directory>` | Clones to a custom directory name. |
| `git remote -v` | Lists all remotes associated with the repository. |

---

## 📂 **3. File States and Changes**

| Command | Description |
|--------|-------------|
| `git status` | Shows the status of working directory and staging area (what’s changed, untracked, staged). |
| `git add <file>` | Stages changes for commit. |
| `git add .` | Stages all changes in the current directory and subdirectories. |
| `git add -p` | Interactively stage changes chunk by chunk. |
| `git rm <file>` | Deletes a file and stages the deletion. |
| `git mv <old> <new>` | Renames or moves a file and stages the change. |

---

## ✅ **4. Committing Changes**

| Command | Description |
|--------|-------------|
| `git commit -m "message"` | Commits staged changes with a message. |
| `git commit` | Opens the default editor to write a commit message. |
| `git commit --amend` | Edits the last commit (message or content). |
| `git reset HEAD <file>` | Unstages a file, keeping local changes. |

---

## 🌳 **5. Branching and Merging**

| Command | Description |
|--------|-------------|
| `git branch` | Lists all local branches. |
| `git branch <name>` | Creates a new branch. |
| `git checkout <branch>` | Switches to another branch. |
| `git checkout -b <name>` | Creates and switches to a new branch. |
| `git merge <branch>` | Merges the specified branch into the current branch. |
| `git branch -d <name>` | Deletes a local branch (safe, only if fully merged). |
| `git branch -D <name>` | Force deletes a branch, even if not merged. |

---

## 🔄 **6. Working with Remotes**

| Command | Description |
|--------|-------------|
| `git remote add origin <url>` | Adds a remote repository under the name `origin`. |
| `git push -u origin main` | Pushes the `main` branch to remote and sets upstream tracking. |
| `git fetch` | Downloads changes from remote but doesn't integrate them. |
| `git pull` | Fetches and merges changes from the remote into the current branch. |
| `git push` | Pushes local commits to remote. |

---

## ♻️ **7. Undoing Changes**

| Command | Description |
|--------|-------------|
| `git checkout -- <file>` | Reverts a file in the working directory to the last committed version. |
| `git reset <file>` | Removes file from staging area but keeps local changes. |
| `git reset --hard` | Resets working directory and staging area to the last commit. **Destructive!** |
| `git revert <commit>` | Creates a new commit that undoes the changes of a specific commit. |
| `git clean -fd` | Deletes untracked files and directories. **Destructive!** |

---

## 🧪 **8. Rebasing and Cherry-Picking**

| Command | Description |
|--------|-------------|
| `git rebase <branch>` | Reapplies commits from current branch on top of another. |
| `git rebase -i <commit>` | Interactive rebase for squashing, reordering, editing commits. |
| `git cherry-pick <commit>` | Applies a specific commit to the current branch. |
| `git cherry-pick -n <commit>` | Cherry-pick without committing immediately (useful for batching). |

---

## 🧰 **9. Stashing Work**

| Command | Description |
|--------|-------------|
| `git stash` | Saves changes not staged for commit for later. |
| `git stash list` | Lists all stashed changes. |
| `git stash apply` | Re-applies the last stash without removing it. |
| `git stash pop` | Re-applies and removes the last stash. |
| `git stash drop` | Removes the latest stash entry. |

---

## 🧩 **10. Tags**

| Command | Description |
|--------|-------------|
| `git tag` | Lists all tags. |
| `git tag <name>` | Creates a lightweight tag. |
| `git tag -a <name> -m "message"` | Creates an annotated tag. |
| `git show <tag>` | Shows tag details and commit. |
| `git push origin <tag>` | Pushes a tag to remote. |

---

## 🕵️‍♂️ **11. Inspecting and Logging**

| Command | Description |
|--------|-------------|
| `git log` | Shows commit history. |
| `git log --oneline` | Condensed view of commit history. |
| `git log --graph --all` | Visual tree of all branches and commits. |
| `git show <commit>` | Shows details and diff of a specific commit. |
| `git diff` | Shows unstaged changes. |
| `git diff --staged` | Shows changes staged for commit. |
| `git blame <file>` | Shows line-by-line commit history for a file. |

---

## 🧠 **12. Recovery and History**

| Command | Description |
|--------|-------------|
| `git reflog` | Shows the history of all HEAD movements. Useful for recovery. |
| `git reset --hard <commit>` | Moves HEAD to a specific commit and discards all changes. |
| `git checkout <commit>` | Checks out a specific commit in detached HEAD state. |

---

## 🔐 **13. Security and SSH**

| Command | Description |
|--------|-------------|
| `ssh-keygen -t rsa -b 4096 -C "you@example.com"` | Generates a new SSH key for authentication. |
| `eval "$(ssh-agent -s)"` | Starts the SSH agent in the background. |
| `ssh-add ~/.ssh/id_rsa` | Adds your SSH key to the agent. |

---

## 🛠 **14. Git Aliases (Custom Shortcuts)**

| Command | Description |
|--------|-------------|
| `git config --global alias.co checkout` | `git co` = `git checkout` |
| `git config --global alias.br branch` | `git br` = `git branch` |
| `git config --global alias.cm commit` | `git cm` = `git commit` |
| `git config --global alias.st status` | `git st` = `git status` |
| `git config --global alias.lg "log --oneline --graph --all"` | `git lg` = neat commit graph |

---

## 📋 **15. .gitignore and File Control**

| Command | Description |
|--------|-------------|
| `.gitignore` | File that lists rules for ignoring files/folders from version control. |
| `git rm -r --cached <folder>` | Remove a folder from repo tracking (e.g., after updating `.gitignore`). |
| `git check-ignore -v <file>` | Shows why a file is being ignored. |

---

Would you like this in a downloadable PDF or printable sheet format? I can also tailor this for **beginners**, **team-based workflows**, or **GUI tools** like SourceTree or GitHub Desktop.
