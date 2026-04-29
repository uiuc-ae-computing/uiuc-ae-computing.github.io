---
layout: page
title: Git Basics
permalink: /resources/git/
nav_order: 2
parent: Resources
---

# Git Basics <!-- omit from toc -->

Git is a version control system that helps you track changes to your code and collaborate with others. This tutorial will guide you through the basics of using Git on both Mac and Windows.

## Table of Contents <!-- omit from toc -->
- [What is Git?](#what-is-git)
- [Installing Git](#installing-git)
  - [On macOS](#on-macos)
  - [On Windows](#on-windows)
- [Configuring Git](#configuring-git)
- [Basic Git Workflow](#basic-git-workflow)
  - [Creating a Repository](#creating-a-repository)
  - [Checking Status](#checking-status)
  - [Staging Changes](#staging-changes)
  - [Committing Changes](#committing-changes)
  - [Viewing History](#viewing-history)
- [Working with Remote Repositories](#working-with-remote-repositories)
  - [Cloning a Repository](#cloning-a-repository)
  - [Pushing Changes](#pushing-changes)
  - [Pulling Changes](#pulling-changes)
- [Branching Strategies](#branching-strategies)
  - [Understanding Branches](#understanding-branches)
  - [Basic Branch Commands](#basic-branch-commands)
  - [Merging Branches](#merging-branches)
  - [Branch Workflow for Coursework](#branch-workflow-for-coursework)
  - [Common Branching Strategies](#common-branching-strategies)
    - [Feature Branch Workflow](#feature-branch-workflow)
    - [Gitflow Workflow](#gitflow-workflow)
    - [GitHub Flow (Simplified)](#github-flow-simplified)
  - [Best Practices for Branches](#best-practices-for-branches)
  - [Handling Merge Conflicts](#handling-merge-conflicts)
  - [Visualizing Branches](#visualizing-branches)
- [Common Git Commands](#common-git-commands)
- [Tips for Beginners](#tips-for-beginners)
- [Further Reading: GitHub CLI](#further-reading-github-cli)
  - [What is GitHub CLI?](#what-is-github-cli)
  - [Installing GitHub CLI](#installing-github-cli)
  - [Authenticating with GitHub](#authenticating-with-github)
  - [Common GitHub CLI Commands](#common-github-cli-commands)
  - [Example Workflows](#example-workflows)
  - [Learning More](#learning-more)
  - [When to Use GitHub CLI vs. Regular Git](#when-to-use-github-cli-vs-regular-git)

## What is Git?

Git is a distributed version control system that allows you to:
- Track changes to your files over time
- Revert to previous versions if something goes wrong
- Collaborate with others on the same project
- Work on different features simultaneously using branches
- Keep a complete history of your project

Think of Git as a "save game" feature for your code, but much more powerful!

## Installing Git

### On macOS

Git comes pre-installed on most modern macOS systems. To check if you have Git installed:

1. Open Terminal (see [Command-line Basics](/resources/commandline-basics/) for how to open a terminal)
2. Run the command:
   ```bash
   git --version
   ```

If Git is installed, you'll see output like:
```bash
git version 2.39.2
```

If Git is not installed, macOS will prompt you to install the Command Line Developer Tools. Click "Install" and follow the prompts.

**Alternative: Install via Homebrew**

If you have [Homebrew](https://brew.sh/) installed, you can install the latest version of Git:
```bash
brew install git
```

### On Windows

**Option 1: Git for Windows (Recommended)**

1. Download Git for Windows from [git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer
3. During installation:
   - Keep the default installation path
   - Select "Git from the command line and also from 3rd-party software"
   - Choose your preferred text editor (VS Code is recommended if you have it installed)
   - Keep other defaults unless you have specific preferences
4. Click "Install"

**Option 2: Git with Anaconda**

If you have Anaconda/Miniconda installed, you can install Git using conda:
```powershell
conda install git
```

**Verifying Installation:**

Open Anaconda Powershell Prompt (or Git Bash if you installed Git for Windows) and run:
```powershell
git --version
```

You should see output like:
```
git version 2.39.2.windows.1
```

## Configuring Git

Before you start using Git, you need to configure your name and email. Git uses this information to identify who made each commit.

**On macOS and Windows:**

Open your terminal (macOS) or Anaconda Powershell/Git Bash (Windows) and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

Replace "Your Name" with your actual name and "your.email@example.com" with your email address (preferably the one you use for GitHub).

To verify your configuration:
```bash
git config --global --list
```

## Basic Git Workflow

### Creating a Repository

A Git repository (or "repo") is a project folder that Git tracks. There are two ways to create a repository:

**1. Initialize a new repository in an existing folder:**

Navigate to your project folder and run:
```bash
cd path/to/your/project
git init
```

You'll see:
```
Initialized empty Git repository in /path/to/your/project/.git/
```

**2. Create a new folder and initialize it:**

```bash
mkdir my-new-project
cd my-new-project
git init
```

### Checking Status

To see which files have been modified, added, or deleted:

```bash
git status
```

This is one of the most frequently used Git commands. It shows you:
- Which files are untracked (new files Git doesn't know about)
- Which files have been modified
- Which files are staged for commit

### Staging Changes

Before you commit changes, you need to "stage" them. Staging allows you to choose which changes to include in your next commit.

**Stage a specific file:**
```bash
git add filename.txt
```

**Stage all changes:**
```bash
git add .
```

**Stage multiple specific files:**
```bash
git add file1.txt file2.py file3.md
```

After staging, run `git status` again to see the files ready to be committed (they'll appear in green).

### Committing Changes

A commit is like a snapshot of your project at a specific point in time. Each commit should have a descriptive message explaining what changed.

```bash
git commit -m "Add initial project files"
```

**Tips for good commit messages:**
- Use the present tense ("Add feature" not "Added feature")
- Be descriptive but concise
- Start with a capital letter
- Examples:
  - "Add function to calculate trajectory"
  - "Fix bug in pressure calculation"
  - "Update README with installation instructions"

### Viewing History

To see a list of previous commits:

```bash
git log
```

For a more compact view:
```bash
git log --oneline
```

To see what changed in each commit:
```bash
git log -p
```

Press `q` to exit the log view.

## Working with Remote Repositories

Remote repositories are versions of your project hosted on the internet (like on GitHub, GitLab, or Bitbucket). This allows you to back up your work and collaborate with others.

### Cloning a Repository

To download a copy of an existing repository:

```bash
git clone https://github.com/username/repository-name.git
```

This creates a new folder with the repository name and downloads all the files and history.

**Example:**
```bash
git clone https://github.com/uiuc-ae-computing/example-repo.git
cd example-repo
```

### Pushing Changes

After making commits locally, you can "push" them to the remote repository:

```bash
git push
```

If it's your first time pushing to a new branch:
```bash
git push -u origin main
```

**Note:** You may need to authenticate with GitHub. See the [GitHub CLI](#further-reading-github-cli) section for easier authentication.

### Pulling Changes

To download and merge changes from the remote repository:

```bash
git pull
```

This is important when:
- Working with collaborators who have made changes
- Working on multiple computers
- Before starting new work (to ensure you have the latest version)

## Branching Strategies

Branches are one of Git's most powerful features. They allow you to work on different versions of your project simultaneously without affecting the main codebase.

### Understanding Branches

Think of a branch as a separate timeline for your project. You can:
- Create a new branch to work on a feature
- Make commits on that branch
- Switch back to the main branch (which remains unchanged)
- Merge your feature branch back when you're done

The default branch is typically called `main` (or `master` in older repositories).

### Basic Branch Commands

**List all branches:**
```bash
git branch
```

The current branch will be marked with an asterisk (*).

**Create a new branch:**
```bash
git branch feature-name
```

**Switch to a branch:**
```bash
git checkout feature-name
```

**Create and switch to a new branch (shortcut):**
```bash
git checkout -b feature-name
```

**Or using the newer `switch` command:**
```bash
git switch feature-name           # Switch to existing branch
git switch -c feature-name        # Create and switch to new branch
```

**Delete a branch:**
```bash
git branch -d feature-name        # Safe delete (only if merged)
git branch -D feature-name        # Force delete
```

### Merging Branches

Once you've finished work on a branch, you can merge it back into the main branch:

```bash
# Switch to the branch you want to merge INTO
git checkout main

# Pull latest changes
git pull

# Merge your feature branch
git merge feature-name
```

If there are no conflicts, Git will automatically merge the changes. If there are conflicts, Git will mark them in the files, and you'll need to resolve them manually.

### Branch Workflow for Coursework

Here's a simple workflow recommended for class projects:

**1. Start with the main branch:**
```bash
git checkout main
git pull  # Get latest changes
```

**2. Create a branch for your work:**
```bash
git checkout -b homework-2
```

**3. Make your changes and commit:**
```bash
# Edit your files
git add .
git commit -m "Complete problem 1"
# Continue working...
git commit -m "Complete problem 2"
```

**4. Push your branch to GitHub:**
```bash
git push -u origin homework-2
```

**5. When ready, merge back to main:**
```bash
git checkout main
git merge homework-2
git push
```

### Common Branching Strategies

#### Feature Branch Workflow

This is the simplest strategy and works well for individual projects or small teams:

- `main` - Always stable, working code
- `feature-X` - Separate branch for each feature or homework assignment

**Example for class:**
```bash
# Working on Homework 3
git checkout -b homework-3
# ... make changes ...
git commit -m "Complete drag force calculations"
git push -u origin homework-3

# When done and tested
git checkout main
git merge homework-3
git push
```

#### Gitflow Workflow

Gitflow is a more structured workflow commonly used in larger projects and industry. While it may be more than you need for coursework, it's good to understand:

**Branch types:**
- `main` (or `master`) - Production-ready code
- `develop` - Integration branch for features
- `feature/*` - Individual features (e.g., `feature/add-plot`)
- `hotfix/*` - Quick fixes for production issues
- `release/*` - Preparing for a new release

**Basic Gitflow process:**

1. **Start a feature:**
   ```bash
   git checkout develop
   git checkout -b feature/calculate-lift
   ```

2. **Work on the feature:**
   ```bash
   git add .
   git commit -m "Add lift calculation function"
   ```

3. **Finish the feature:**
   ```bash
   git checkout develop
   git merge feature/calculate-lift
   git branch -d feature/calculate-lift
   git push
   ```

4. **Create a release:**
   ```bash
   git checkout develop
   git checkout -b release/1.0
   # Make final adjustments, update version numbers
   git checkout main
   git merge release/1.0
   git tag -a v1.0 -m "Version 1.0"
   git checkout develop
   git merge release/1.0
   git branch -d release/1.0
   ```

#### GitHub Flow (Simplified)

This is a simpler alternative to Gitflow, popular for web projects:

1. `main` branch is always deployable
2. Create descriptive branches off `main` (e.g., `add-visualization`)
3. Commit to that branch locally and push regularly
4. Open a pull request when ready
5. Merge after review and testing
6. Delete the branch after merging

### Best Practices for Branches

1. **Use descriptive branch names:**
   - Good: `homework-3`, `fix-integration-bug`, `add-plotting-function`
   - Bad: `temp`, `fix`, `branch1`

2. **Keep branches short-lived:** Don't let branches diverge too far from `main`. Merge regularly to avoid complex conflicts.

3. **One purpose per branch:** Each branch should focus on one feature, fix, or task.

4. **Delete merged branches:** Once a branch is merged, delete it to keep your repository clean:
   ```bash
   git branch -d feature-name
   git push origin --delete feature-name  # Delete remote branch
   ```

5. **Pull before creating a new branch:** Always start with the latest code:
   ```bash
   git checkout main
   git pull
   git checkout -b new-feature
   ```

6. **Commit before switching branches:** Either commit or stash your changes before switching to avoid losing work.

### Handling Merge Conflicts

Sometimes Git can't automatically merge changes, and you'll get a conflict:

```bash
git merge feature-branch
# CONFLICT (content): Merge conflict in calculation.py
# Automatic merge failed; fix conflicts and then commit the result.
```

**To resolve:**

1. Open the conflicting file. Git marks conflicts like this:
   ```python
   <<<<<<< HEAD
   # Your current code
   result = x * 2
   =======
   # Incoming changes
   result = x * 3
   >>>>>>> feature-branch
   ```

2. Edit the file to keep what you want:
   ```python
   result = x * 3  # Decided to keep the incoming change
   ```

3. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)

4. Stage and commit the resolved file:
   ```bash
   git add calculation.py
   git commit -m "Resolve merge conflict in calculation"
   ```

### Visualizing Branches

To see your branch structure:

```bash
git log --graph --oneline --all
```

This shows a visual representation of your branches and commits.

## Common Git Commands

Here's a quick reference of essential Git commands:

| Command                   | Description                                       |
| ------------------------- | ------------------------------------------------- |
| `git init`                | Initialize a new Git repository                   |
| `git clone <url>`         | Clone a remote repository                         |
| `git status`              | Check the status of your working directory        |
| `git add <file>`          | Stage a file for commit                           |
| `git add .`               | Stage all changes                                 |
| `git commit -m "message"` | Commit staged changes with a message              |
| `git push`                | Push commits to remote repository                 |
| `git pull`                | Pull changes from remote repository               |
| `git log`                 | View commit history                               |
| `git diff`                | Show changes between commits or working directory |
| `git branch`              | List, create, or delete branches                  |
| `git checkout <branch>`   | Switch to a different branch                      |
| `git merge <branch>`      | Merge another branch into current branch          |

## Tips for Beginners

1. **Commit often**: Make small, frequent commits rather than large, infrequent ones. This makes it easier to track changes and fix problems.

2. **Write meaningful commit messages**: Your future self (and collaborators) will thank you for clear, descriptive messages.

3. **Use `git status` frequently**: Get in the habit of checking status before and after making changes.

4. **Don't commit everything**: Use a `.gitignore` file to exclude files you don't want to track (like compiled code, large data files, or system files).

5. **Pull before you push**: Always pull the latest changes before pushing your own to avoid conflicts.

6. **Create a `.gitignore` file**: Here's a basic example:
   ```
   # Python
   __pycache__/
   *.pyc
   *.pyo
   .ipynb_checkpoints/
   
   # macOS
   .DS_Store
   
   # Windows
   Thumbs.db
   
   # Data files
   *.csv
   *.dat
   data/
   ```

7. **Learn to use branches**: Branches allow you to work on new features without affecting the main codebase. This is an intermediate skill worth learning.

8. **Back up to GitHub**: Even if you're working alone, pushing to GitHub provides a backup and makes your work accessible from anywhere.

## Further Reading: GitHub CLI

The GitHub CLI (`gh`) is a command-line tool that makes it easier to work with GitHub repositories. While not required, it can simplify many common tasks.

### What is GitHub CLI?

GitHub CLI (`gh`) brings GitHub to your terminal. It allows you to:
- Create and clone repositories
- Create and view pull requests and issues
- Authenticate with GitHub easily
- Manage GitHub Actions and other GitHub features
- All without leaving the command line!

### Installing GitHub CLI

**On macOS:**

Using Homebrew:
```bash
brew install gh
```

**On Windows:**

Using the installer:
1. Download from [cli.github.com](https://cli.github.com/)
2. Run the installer
3. Follow the installation prompts

Using conda:
```powershell
conda install gh --channel conda-forge
```

**Verify Installation:**
```bash
gh --version
```

### Authenticating with GitHub

After installation, authenticate with GitHub:

```bash
gh auth login
```

Follow the prompts:
1. Choose "GitHub.com"
2. Choose "HTTPS" (recommended)
3. Choose "Login with a web browser"
4. Copy the one-time code shown
5. Press Enter to open your browser
6. Paste the code and authorize

### Common GitHub CLI Commands

| Command                   | Description                     |
| ------------------------- | ------------------------------- |
| `gh repo create`          | Create a new repository         |
| `gh repo clone <repo>`    | Clone a repository              |
| `gh repo view`            | View repository details         |
| `gh issue list`           | List issues                     |
| `gh issue create`         | Create a new issue              |
| `gh pr list`              | List pull requests              |
| `gh pr create`            | Create a new pull request       |
| `gh pr checkout <number>` | Checkout a pull request locally |

### Example Workflows

**Creating a new repository and pushing code:**

```bash
# Create a new local repository
mkdir my-project
cd my-project
git init

# Create some files
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"

# Create GitHub repository and push
gh repo create my-project --public --source=. --push
```

**Cloning a repository:**

```bash
gh repo clone username/repository-name
```

**Creating an issue:**

```bash
gh issue create --title "Bug: Calculation error" --body "Description of the issue"
```

### Learning More

- Official GitHub CLI documentation: [cli.github.com/manual](https://cli.github.com/manual/)
- GitHub CLI cheatsheet: Run `gh help` in your terminal
- Interactive tutorial: Run `gh help` for available commands

### When to Use GitHub CLI vs. Regular Git

- Use **Git** for: version control operations (commit, push, pull, branch, merge)
- Use **GitHub CLI** for: GitHub-specific operations (issues, pull requests, creating repos)
- They work together! Use both as needed.

---

**Need more help?** 
- [Official Git documentation](https://git-scm.com/doc)
- [GitHub Git Guides](https://github.com/git-guides)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- Ask your instructor or TA!

