---
layout: page
title: Git/GitHub Tutorial
permalink: /git-github/
nav_order: 1
parent: Introductory
---

# Git and GitHub Essentials for Students <!-- omit from toc -->

Learn to use Git and GitHub to track your code, collaborate on projects, and build good version control habits from the start.

## Table of Contents <!-- omit from toc -->
- [What is Git?](#what-is-git)
- [Getting Started](#getting-started)
  - [Installing Git](#installing-git)
  - [Configuring Git](#configuring-git)
- [Your First Repository](#your-first-repository)
  - [Creating a Local Repository](#creating-a-local-repository)
  - [Making Your First Commit](#making-your-first-commit)
  - [Viewing Your History](#viewing-your-history)
- [Working with GitHub](#working-with-github)
  - [Setting Up a Remote Repository](#setting-up-a-remote-repository)
  - [Pushing Your Code](#pushing-your-code)
  - [Pulling Changes](#pulling-changes)
- [Branching Basics](#branching-basics)
  - [Understanding Branches](#understanding-branches)
  - [Creating and Switching Branches](#creating-and-switching-branches)
  - [Merging Your Work](#merging-your-work)
- [Common Workflows](#common-workflows)
- [Quick Reference](#quick-reference)
- [Troubleshooting Tips](#troubleshooting-tips)

## What is Git?

Git is a **version control system** that helps you:
- **Track changes** to your files over time
- **Undo mistakes** by reverting to previous versions
- **Collaborate** with teammates on the same project
- **Work independently** on different features using branches
- **Keep a complete history** of your project

Think of Git as a super-powered "save" feature for your code. Instead of saving `project_v1.py`, `project_v2.py`, `project_final.py`, `project_FINAL_FINAL.py`, you use Git to track all versions automatically with meaningful descriptions.

**GitHub** is a cloud platform that hosts your Git repositories, making it easy to back up your work, share code, and collaborate.

## Getting Started

### Installing Git

**On macOS:**

1. Open Terminal (see [Command-line Basics](/resources/commandline-basics/) if you need help)
2. Check if Git is already installed:
   ```bash
   git --version
   ```

If you see a version number, you're good! If not, you have two options:

**Option 1: Use Homebrew (Recommended)**
```bash
brew install git
```

**Option 2: Install Xcode Command Line Tools**
macOS will prompt you to install these when you try to use Git. Just click "Install" and follow the prompts.

**On Windows:**

1. Download Git for Windows from [git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer and keep the default settings
3. Choose "Git from the command line and also from 3rd-party software"
4. Complete the installation
5. Open Anaconda PowerShell Prompt or Git Bash and verify:
   ```powershell
   git --version
   ```

### Configuring Git

Before using Git, tell it who you are. Git uses this info for every commit:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@illinois.edu"
```

Use your actual name and the email you'll use for GitHub.

Verify the configuration:
```bash
git config --global --list
```

## Your First Repository

### Creating a Local Repository

A **repository** (or "repo") is a folder where Git tracks your files.

**Method 1: Start a new project**
```bash
mkdir my-project
cd my-project
git init
```

You'll see:
```
Initialized empty Git repository in /path/to/my-project/.git/
```

**Method 2: Clone an existing repository**
```bash
git clone https://github.com/username/repository-name.git
cd repository-name
```

### Making Your First Commit

A **commit** is a snapshot of your project at a point in time.

**Step 1: Create or modify files**
```bash
echo "# My Project" > README.md
echo "print('Hello World')" > main.py
```

**Step 2: Check what changed**
```bash
git status
```

You'll see your new files listed as "untracked".

**Step 3: Stage your changes**
```bash
git add .
```

This tells Git which changes to include in your commit. (The `.` means "add everything".)

**Step 4: Create the commit**
```bash
git commit -m "Initial project files"
```

Replace the message with something meaningful that describes what changed.

**Good commit messages:**
- "Add function to calculate trajectory"
- "Fix bug in pressure calculation"
- "Update README with setup instructions"

**Avoid:**
- "changes" ❌
- "fix" ❌
- "asdfgh" ❌

### Viewing Your History

See all your commits:
```bash
git log
```

For a compact view:
```bash
git log --oneline
```

Press `q` to exit.

## Working with GitHub

### Setting Up a Remote Repository

A **remote repository** is your project hosted on GitHub (a backup and sharing point).

**Step 1: Create a GitHub account**
Go to [github.com](https://github.com) and sign up if you haven't already.

**Step 2: Create a new repository on GitHub**
- Click the "+" icon in the top right
- Select "New repository"
- Name it (e.g., `my-project`)
- Add a description (optional)
- Choose "Public" or "Private"
- Click "Create repository"

**Step 3: Connect your local repo to GitHub**

GitHub will show you commands to run. For a new project:

```bash
git branch -M main
git remote add origin https://github.com/your-username/my-project.git
git push -u origin main
```

### Pushing Your Code

After making commits locally, upload them to GitHub:

```bash
git push
```

On your first push to a new branch:
```bash
git push -u origin main
```

Now your code is backed up on GitHub! You can see it at `github.com/your-username/my-project`.

### Pulling Changes

If you make changes on GitHub (like editing a file directly on the website) or if you're working on multiple computers:

```bash
git pull
```

This downloads the latest changes and updates your local files.

**Best practice:** Always pull before starting new work:
```bash
git checkout main
git pull
git checkout -b my-feature
```

## Branching Basics

Branches let you work on new features without affecting your main code. Think of it as creating a parallel universe for your project.

### Understanding Branches

- **main** = Your stable, working code
- **feature-X** = A separate branch for new work

When you're done, you merge your branch back into main.

### Creating and Switching Branches

**Create a new branch:**
```bash
git checkout -b homework-2
```

(Or the newer syntax: `git switch -c homework-2`)

**Switch to an existing branch:**
```bash
git checkout main
```

**List all branches:**
```bash
git branch
```

The current branch is marked with an asterisk (*).

**Delete a branch (after merging):**
```bash
git branch -d homework-2
```

### Merging Your Work

When you're done with a feature or assignment:

```bash
git checkout main
git pull
git merge homework-2
git push
```

This brings your branch's changes into main.

**If there are merge conflicts:**
Git will tell you which files have conflicts. Open them, look for `<<<<<<<` markers, and decide which code to keep. Then:
```bash
git add .
git commit -m "Resolve merge conflict"
git push
```

## Common Workflows

### Workflow for Class Projects

```bash
# 1. Start fresh
git checkout main
git pull

# 2. Create a branch for your assignment
git checkout -b homework-3

# 3. Do your work
# ... edit files ...
git add .
git commit -m "Complete problem 1"

# ... more work ...
git commit -m "Complete problem 2"

# 4. Push your branch
git push -u origin homework-3

# 5. When done, merge to main
git checkout main
git merge homework-3
git push

# 6. Clean up
git branch -d homework-3
```

### Workflow for Group Projects

1. **Clone the repository:**
   ```bash
   git clone https://github.com/team/project.git
   cd project
   ```

2. **Create your feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make commits as you work:**
   ```bash
   git add .
   git commit -m "Add visualization function"
   ```

4. **Keep your branch updated:**
   ```bash
   git fetch
   git rebase origin/main
   ```

5. **Push when ready:**
   ```bash
   git push -u origin feature/your-feature-name
   ```

6. **Create a pull request on GitHub** for teammates to review

## Quick Reference

| Command | What it does |
|---------|-------------|
| `git init` | Start tracking a folder with Git |
| `git clone <url>` | Download a repository |
| `git status` | See which files changed |
| `git add <file>` | Stage a file for commit |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Save your changes with a description |
| `git push` | Upload commits to GitHub |
| `git pull` | Download latest changes from GitHub |
| `git log --oneline` | See commit history |
| `git branch` | List branches |
| `git checkout -b <branch>` | Create and switch to a new branch |
| `git checkout <branch>` | Switch to a branch |
| `git merge <branch>` | Combine a branch into the current branch |
| `git diff` | See exactly what changed |

## Troubleshooting Tips

**"I committed to the wrong branch"**
```bash
git reset HEAD~1        # Undo the commit (keep changes)
git checkout correct-branch
git add .
git commit -m "message"
```

**"I need to undo a commit"**
```bash
git revert HEAD         # Creates a new commit that undoes the previous one
git push
```

**"I made changes but forgot to commit"**
```bash
git add .
git commit -m "Your message"
git push
```

**"I want to undo changes to a file"**
```bash
git checkout -- filename.py
```

**"How do I see what changed between commits?"**
```bash
git diff commit1 commit2
git show commit-hash    # See what changed in one specific commit
```

---

## Next Steps

- Read the [detailed Git guide](/resources/git/) for advanced topics
- Learn about [GitHub CLI](#github-cli) for faster workflows
- Practice by creating a test repository and experimenting!

## GitHub CLI (Optional)

**GitHub CLI** (`gh`) lets you do GitHub tasks from the terminal without opening your browser.

### Installing GitHub CLI

**macOS:**
```bash
brew install gh
```

**Windows:**
Download from [cli.github.com](https://cli.github.com/) or use:
```powershell
conda install gh --channel conda-forge
```

### Quick GitHub CLI Commands

```bash
gh auth login              # Set up authentication
gh repo create my-project  # Create a new repository on GitHub
gh issue list              # See issues in the current repo
gh pr list                 # See pull requests
gh pr create               # Create a pull request
```

---

**Want to learn more?**
- [Official Git documentation](https://git-scm.com/doc)
- [GitHub Git Guides](https://github.com/git-guides)
- [Detailed Git Tutorial](/resources/git/)
- Ask your instructor or TA!

