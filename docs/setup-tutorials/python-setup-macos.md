---
layout: page
title: Python Setup (macOS)
permalink: /python-setup-macos/
nav_order: 1
parent: Setup Tutorials
---

# How to Set Up a Python Programming Environment <!-- omit from toc -->

## Table of Contents <!-- omit from toc -->
- [Introduction](#introduction)
- [Install Miniconda](#install-miniconda)
  - [Install Xcode Command Line Tools](#install-xcode-command-line-tools)
  - [Install Miniconda](#install-miniconda-1)
  - [Verify Installation](#verify-installation)
- [Install VS Code](#install-vs-code)
  - [Install VS Code](#install-vs-code-1)
  - [Install the Python and Jupyter Extensions](#install-the-python-and-jupyter-extensions)
  - [Enable the `code` Command in Terminal (Recommended)](#enable-the-code-command-in-terminal-recommended)
- [Complete the Python Refresher Assignment](#complete-the-python-refresher-assignment)
- [Do this once for every course](#do-this-once-for-every-course)
  - [Create a folder for the course and assignment](#create-a-folder-for-the-course-and-assignment)
  - [Create a conda environment for the course](#create-a-conda-environment-for-the-course)
- [Do this every time you work on a course](#do-this-every-time-you-work-on-a-course)


## Introduction

This tutorial aims to:

- help you set up a Python programming environment for coding assignments, research, or working with RSOs
- have you use your programming environment to complete a Python refresher assignment

Some of the steps are based on the [Visual Studio Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial).

{: .note-title}
> How to open a terminal
>
> When we say "open a terminal," what we mean is to start the **Terminal** application. Here is one way to do that:
> 
> * Click the Launchpad icon in the Dock (or press **Cmd + Space** to open Spotlight).
> * Type "Terminal" in the search field.
> * Click Terminal.
> 
> See documentation on [Open Terminal](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac) for more information. Note that it is often helpful to have more than one terminal window open at the same time (or more than one tab in the same window).

{: .note-title}
> How to run a command
> 
> When we say "run a command," what we mean is to type something into the terminal window and press return. For example, suppose we said:
> 
> > run the command `pwd` to find your current working directory
> 
> You would type `pwd` into the terminal window and press return, with the result being something like this:
> 
> ```
> (base) ➜  ~ pwd
> /Users/username
> ```
> 
> See documentation on [Execute commands and run tools in Terminal on Mac](https://support.apple.com/guide/terminal/execute-commands-and-run-tools-apdb66b5242-0d18-49fc-9c47-a2498b7c91d5/mac) for more information. Also see the [command-line basics](/resources/commandline-basics/) or [Command Line Primer](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/CommandLInePrimer/CommandLine.html) page for a list of frequently used commands.


## Install Miniconda

[Conda](https://docs.conda.io/) is a package management system that includes Python. We suggest you install Miniconda to install conda and Python.

### Install Xcode Command Line Tools

Open a terminal and run the following command, accepting all default options:

```bash
xcode-select --install
```

A pop-up window may appear asking if you want to install the command line developer tools. Click **Install** and agree to the license terms. You may be asked to restart your computer during or after this process. Please do so if prompted.

You may get a message like the following in your terminal. If so, command line tools are already installed, and you can skip to [Install Miniconda](#install-miniconda-1).

```bash
xcode-select: note: Command line tools are already installed. Use "Software Update" in System Settings or the softwareupdate command line interface to install updates
```

### Install Miniconda

1. Check if conda is already installed:

   ```bash
   conda --version
   ```

   If this command prints a conda version number, conda is already installed, and you can skip to [Verify Installation](#verify-installation). If you see `command not found: conda`, continue with the installation below.

2. Go to the [Miniconda installation page](https://docs.anaconda.com/miniconda/) and download the appropriate `.pkg` installer for your Mac architecture:
   - **Apple Silicon (M1/M2/M3/M4)**: download the `arm64` `.pkg` installer.
   - **Intel Mac**: download the `x86_64` `.pkg` installer.

   See Apple's [Mac computers with Apple silicon](https://support.apple.com/en-us/116943) guide if you need help determining which processor your Mac has.

3. Double-click the downloaded `.pkg` file and follow the prompts, accepting all the default options during installation.

4. After installation finishes, restart your terminal (close Terminal and open a new Terminal window).

### Verify Installation

Open a new terminal and run:

```bash
conda --version
```

You should see the conda version number (e.g., `conda 24.x.x`) if the installation was successful.

## Install VS Code

We suggest installing [Visual Studio Code](https://code.visualstudio.com/) (VS Code) to use as your integrated development environment (IDE) for writing Python code.

### Install VS Code

1. Follow the instructions on the [Install VS Code on macOS](https://code.visualstudio.com/docs/setup/mac#_install-vs-code-on-macos) page to download VS Code.
2. Unzip the downloaded file if necessary, and **drag the Visual Studio Code.app file into your Applications folder**.

### Install the Python and Jupyter Extensions

1. Open the VS Code application.
2. Click the **Extensions** icon in the **Activity Bar** on the left-hand side of VS Code (or press **Cmd + Shift + X**).
3. Install the Python extension:
   1. Type "Python" into the search bar.
   2. Click the **Python** extension (by Microsoft) and click the **Install** button.
4. Install the Jupyter extension:
   1. Type "Jupyter" into the search bar.
   2. Click the **Jupyter** extension (by Microsoft) and click the **Install** button.

### Enable the `code` Command in Terminal (Recommended)

To allow opening project folders in VS Code directly from your terminal using the `code .` command:

1. Open VS Code.
2. Open the Command Palette by pressing **Cmd + Shift + P** (or go to **View** > **Command Palette...**).
3. Type `shell command` and select **Shell Command: Install 'code' command in PATH**.
4. Press Enter. You should see a notification confirming the command was successfully installed.

## Complete the Python Refresher Assignment

You can now use your VS Code workspace and Conda environment to complete the `python-refresher.ipynb` file found [here](/assets/files/python-refresher.ipynb).

If clicking the link displays raw JSON data in your browser, right-click the link and select **Save Link As...** to download the `.ipynb` file to your computer.

Follow the steps in the [Do this once for every course](#do-this-once-for-every-course) section to set up an environment for the `python-refresher.ipynb` assignment. Be sure to replace instances of "my-course" with "computing-readiness" and "my-assignment" with "python-refresher."

Follow the steps in the [Do this every time you work on a course](#do-this-every-time-you-work-on-a-course) section to complete the assignment.

## Do this once for every course

You should follow these steps **once** for every course (and assignment).

### Create a folder for the course and assignment

You should organize your code files into folders (or directories) based on courses and assignments. For example, you might store files for this tutorial in a `computing-readiness` folder within a `projects` folder (where you store all coursework) within your `Documents` folder, organized like this:

    ├── Documents
    │   ├── personal
    │   ├── projects
    │       ├── ae202
    │       ├── ae370
    │       ├── computing-readiness
    │           ├── python-refresher
    │               ├── python-refresher.ipynb

{: .note-title}
> How to change the working directory
> 
> All the files on your computer are organized in folders, which are commonly referred to as "directories." When you are working on the command line in a terminal, you are working in one of these directories. Commands you run can find files in that directory, but cannot (by default) find files in other directories.
> 
> When we say "change the working directory," we mean exactly that --- telling the terminal the directory in which you want to work.
> 
> To do this, we run the command
> 
> ```bash
> cd path/to/directory
> ```
> 
> where `path/to/directory` is replaced by the location of the directory in which you want to work. One easy way to find this location (i.e., the "path" to your directory) is by dragging its folder from the Finder into your terminal window (see documentation on [Drag items into a Terminal window on Mac](https://support.apple.com/guide/terminal/drag-items-into-a-terminal-window-trml106/mac)). In particular, I would first type `cd ` (note the single trailing space):
> 
> ```
> (base) ➜  ~ cd 
> ```
> 
> Then, I would drag a folder into the terminal window and press return. For instance, suppose I had created a folder called `computing-readiness` somewhere on my computer and dragged it in, then pressed return --- I would see something like this:
> 
> ```
> (base) ➜  ~ cd /Users/username/Documents/projects/computing-readiness/python-refresher 
> (base) ➜  python-refresher
> ```
> 
> I could then use the `pwd` command to print the working directory, which would show something like this:
> 
> ```bash
> (base) ➜  python-refresher pwd
> /Users/username/Documents/projects/computing-readiness/python-refresher
> ```
> 
> See documentation in the [Specify files and folders in Terminal on Mac](https://support.apple.com/guide/terminal/specify-files-and-folders-apd3cf6fe02-3ec8-48f1-951f-866e52955fc8/mac) page for other ways to specify the path to a directory.

You can create the `computing-readiness` folder and assignment structure shown above by opening a terminal and running the following commands. **Note that lines starting with a "#" symbol are comments, not commands to enter.**

```bash
# change your working directory to your home directory
cd

# show the folders within your home directory (optional)
ls

# change your working directory to the Documents folder
cd Documents

# make a projects folder (if needed)
mkdir -p projects

# change your working directory to your projects folder
cd projects

# make a "my-course" folder (for this tutorial: mkdir computing-readiness)
mkdir my-course

# change your working directory to the "my-course" folder
cd my-course

# make a "my-assignment" folder (for this tutorial: mkdir python-refresher)
mkdir my-assignment

# change your working directory to the "my-assignment" folder
cd my-assignment
```

Remember to move the downloaded `python-refresher.ipynb` file into this assignment directory.

### Create a conda environment for the course

You should create and use a separate conda environment for each course.

VS Code provides a good explanation for why: "A best practice among Python developers is to use a project-specific virtual environment. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions."

Create a conda environment for your course (replacing "my-course" with your course name, e.g., `computing-readiness`) by opening a terminal and doing the following:

1. Create a conda environment named "my-course" with Python 3.11:

    ```bash
    conda create --name my-course python=3.11
    ```

    Your command prompt will show the package plan and ask to proceed:
    
    ```bash
    Proceed ([y]/n)? 
    ```

    Enter `y` to proceed.

2. Activate your `my-course` conda environment. Any packages you install with conda will now be installed in this isolated conda environment:

    ```bash
    conda activate my-course
    ```

3. Install Jupyter and necessary packages in your conda environment:

    ```bash
    conda install jupyter
    ```

    Enter `y` when prompted to proceed.

A Conda cheatsheet of common Conda commands can be found [here](https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf).

## Do this every time you work on a course

You should follow these steps every day before you start to work on a course or assignment.

1. Open a terminal.
2. Change your working directory to your assignment directory. For example, assuming the directory structure shown in [Create a folder for the course and assignment](#create-a-folder-for-the-course-and-assignment), you could run:

    ```bash
    cd ~/Documents/projects/my-course/my-assignment
    ```

    *(For this refresher tutorial, use `cd ~/Documents/projects/computing-readiness/python-refresher`)*

3. Activate your conda environment by running:

    ```bash
    conda activate my-course
    ```

    You should see the prefix to your terminal prompt change from `(base)` to `(my-course)`. This means you are in the conda environment you created for your course.

    As an alternative, you can also select your conda environment to use while working in VS Code:

    1. Open the Command Palette in VS Code (**Cmd + Shift + P** or **View** > **Command Palette...**).
    2. Search for "Python: Select Interpreter" and select the command.
    3. Select the conda environment you created, for example: `Python 3.11.x ('computing-readiness') ... Conda`.

4. Open VS Code to work on your assignment by running:

    ```bash
    code .
    ```

    {: .note-title}
    > Selecting the Jupyter Kernel in VS Code
    >
    > When you open your `.ipynb` notebook file inside VS Code, check the top-right corner of the editor. If it says **Select Kernel**, click it, choose **Python Environments...**, and select your `computing-readiness` (or `my-course`) environment.

    As an alternative to VS Code, you can also work with Jupyter notebooks in a browser by running this command in your active terminal:

    ```bash
    jupyter notebook
    ```

    A browser window will open with the Jupyter notebook interface. You can now navigate to and open any Jupyter notebooks (with extension `.ipynb`).

We strongly recommend you duplicate and work with a copy of any given notebook rather than working with the original. Feel free to ignore this suggestion if you are a `git` expert.
