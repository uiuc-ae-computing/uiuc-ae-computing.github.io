---
layout: page
title: Python Setup (Windows)
permalink: /python-setup-windows/
nav_order: 1
parent: Setup Tutorials
---

# How to Set Up a Python Programming Environment <!-- omit from toc -->

## Table of Contents <!-- omit from toc -->
- [Introduction](#introduction)
- [Install Miniconda](#install-miniconda)
  - [Install Miniconda](#install-miniconda-1)
  - [Verify Installation](#verify-installation)
- [Install VS Code](#install-vs-code)
  - [Install VS Code](#install-vs-code-1)
  - [Install the Python and Jupyter Extensions](#install-the-python-and-jupyter-extensions)
- [Complete the Python Refresher Assignment](#complete-the-python-refresher-assignment)
- [Do this once for every course](#do-this-once-for-every-course)
  - [Create a folder for the course and assignment](#create-a-folder-for-the-course-and-assignment)
  - [Create a conda environment for the course](#create-a-conda-environment-for-the-course)
- [Do this everytime you work on a course](#do-this-everytime-you-work-on-a-course)


## Introduction

This tutorial aims to:

- help you set up a Python programming environment for coding assignments, research, or working with with RSOs
- have you use your programming environment to complete a Python refresher assignment

Some of steps are based on the [Visual Studio Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial).

{: .note-title}
> How to open a terminal
>
> When we say "open a terminal," what we mean is to start the **Terminal** application. Here is one way to do that:
> 
> If Miniconda is installed, then use the Start menu to search for and open an **Anaconda Prompt**.
> * Type "Anaconda Prompt" in the search field.
> * Click Anaconda Prompt.
>
> There may be other words in the titles of these two applications — for example, “Anaconda Prompt” may appear as “Anaconda Prompt (Miniconda3).”
> 
> See documentation on [Anaconda Prompt](https://www.anaconda.com/docs/reference/glossary#anaconda-prompt) for more information. Note that it is often helpful to have more than one terminal window open at the same time (or more than one tab in the same window).

{: .note-title}
> How to run a command
> 
> When we say "run a command," what we mean is to type something into the terminal window and press return. For example, suppose we said:
> 
> > run the command `cd` to find your current working directory
> 
> You would type `cd` into the terminal window and press return, with the result being something like this:
> 
> ```
> (base) C:\Users\YourName> cd
> C:\Users\YourName
> ```
> 
> See documentation on [Windows Commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands). Also see the [command-line basics](/resources/commandline-basics/) or [Command Line Primer](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/CommandLInePrimer/CommandLine.html) page for a list of frequently used commands.


## Install Miniconda

[Conda](https://docs.conda.io/) is a package management system that includes Python. We suggest you install Miniconda to install conda and Python.

### Install Miniconda

1. Check if conda is already installed by searching for "Anaconda Prompt" in the Start menu.

   If this process succeeds, then conda is installed, and you can skip to [Verify Installation](#verify-installation). If this process does not succeed, continue with the installation below.

2. Go to the [Miniconda installer page](https://www.anaconda.com/download/success) and download the appropriate `.exe` file for Windows. Make sure you are running 64-bit Windows.

3. Double-click the downloaded `.exe` file and accept all the default options during installation.

4. After installation, search for "Anaconda Prompt" in the Start menu and open it.

### Verify Installation

Open a new terminal and run:

```bash
conda --version
```

You should see the conda version number if the installation was successful.

## Install VS Code

We suggest installing [Visual Studio Code](https://code.visualstudio.com/) (VS Code) to use as your integrated development environment (IDE) for writing Python code.

### Install VS Code

Follow the instructions in the [Install VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page to download and install VS Code.

Remember to **drag the Visual Studio Code.app file into your Applications folder**.

### Install the Python and Jupyter Extensions

1. Open the VS Code application.
1. Click the **Extensions** icon in the **Activity Bar** in on the left-hand side of VS Code.
1. Install the Python extension.
    1. Type "Python" into the search bar.
    1. Click the **Python** extension and click the **Install** button in the window that appears.
1. Install the Jupyter extension.
    1. Type "Jupyter" into the search bar.
    1. Click the **Jupyter** extension and click the **Install** button in the window that appears.

## Complete the Python Refresher Assignment

You can now use your VS Code workspace and Conda environment to complete the `python-refresher.ipynb` file found [here](/assets/files/python-refresher.ipynb).
If the link shows a raw JSON data, right click the link, and select "Save Link As" to download the file.

Follow the steps in the [Do this once for every course](#do-this-once-for-every-course) section to set up an environment for the `python-refresher.ipynb` assignment. Be sure to replace instances of "my-course" with "computing-readiness" and "my-assignment" with "python-refresher."

Follow the steps in the [Do this every time you work on a course](#do-this-everytime-you-work-on-a-course) section to complete the assignment.

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
    │           ├── python-refresher.ipynb

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
> cd path\to\directory
> ```
> 
> where `path\to\directory` is replaced by the location of the directory in which you want to work. One easy way to find this location (i.e., the "path" to your directory) is by dragging its folder from the Finder into your terminal window (see documentation on [Quickly Copy Files Paths to Your Command Prompt via Drag and Drop](https://lifehacker.com/quickly-copy-file-paths-to-your-command-prompt-via-drag-5382503)). In particular, I would first type `cd ` (note the single trailing space):
> 
> ```
> (base) C:\Users\YourName>cd 
> ```
> 
> Then, I would drag a folder into the terminal window and press return. For instance, suppose I had created a folder called `computing-readiness` somewhere on my computer and dragged it in, then pressed return --- I would see something like this:
> 
> ```
> (base) C:\Users\YourName> cd C:\Users\YourName\Documents\projects\ae-computing\python-refresher
> (base) python-refresher>
> ```
> 
> I could then use the `pwd` command to print the working directory, which would show something like this:
> 
> ```bash
> (base) python-refresher> cd
> C:\Users\YourName\Documents\projects\ae-computing\python-refresher
> ```
> 
> See documentation in the [cd](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/cd) and [dir](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/dir) page for other ways to specify the path to a directory.

You can create the `computing-readiness' folder and structure shown above by opening a terminal and running the following commands. **Note that lines starting with a "#" symbol are comments, not commands to enter.**

```bash
# change your working directory to your home directory
cd

# show the folders within your home directory (optional)
dir

# change your working directory to the Documents folder
cd Documents

# make a projects folder (if needed)
mkdir projects

# change your working directory to your projects folder
cd projects

# make a "my-course" folder
mkdir my-course

# change your working directory to the "my-course" folder
cd my-course

# make a "my-assignment" folder
mkdir my-assignment

# change your working directory to the "my-assignment" folder
cd my-assignment
```

### Create a conda environment for the course

You should create and use a separate conda environment for each course.

VS Code provides a good explanation for why: "A best practice among Python developers is to use a project-specific virtual environment. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions."

Create a conda environment for your course (replacing "my-course" with your course name) by opening a terminal and doing the following:

1. Create a conda environment named "my-course".

    ```bash
    conda create --name my-course
    ```

    Your command prompt should show something like the following:
    
    ```bash
    Channels:
    - defaults
    Platform: win-64
    Collecting package metadata (repodata.json): done
    Solving environment: done

    ## Package Plan ##

    environment location: C:\Users\httran\anaconda3\envs\my-course



    Proceed ([y]/n)? 
    ```

    Enter `y` to proceed.

1. Active your `my-course` conda environment. Any packages you install with conda will now be installed in this conda environment.

    ```bash
    conda activate my-course
    ```

1. Install Python 3 and Jupyter in your conda environment (install Python 3.11 because Jupyter only supports up to 3.11).

    ```bash
    conda install python=3.11
    ```

    Enter `y` to proceed.

    ```bash
    conda install jupyter
    ```

    Enter `y` to proceed.

A Conda cheatsheet of common Conda commands can be found [here](https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf).

## Do this everytime you work on a course

You should follow these steps every day before you start to work on a course or assignment.

1. Open a terminal.
1. Change your working directory to your assignment directory. For example, assuming the directory structure shown in [Create a folder for the course and assignment](#create-a-folder-for-the-course-and-assignment), you could run the following commands:

    ```bash
    cd
    cd C:\Users\YourName\Documents\projects\my-course\my-assignment
    ```

1. Activate your conda environment by running this command:

    ```bash
    conda activate my-course
    ```

    You should see the prefix to your terminal prompt change from `(base)` to `(my-course)`. This means you are in the conda environment you created for your course.

    As an alternative, you can also select your conda environment to use while working in VS Code by doing the following:

    1. Open the Command Palette by going to VS Code's View > Command Palette
    1. Search for "Python: Select Interpreter" and select the command.
    1. Select the conda environment you just created and installed Python in "Python 3.13.1 ('computing-readiness') ... Conda".

1. Open VS Code to work on your assignment by running this command:

    ```bash
    code .
    ```

    As an alternative to VS Code, you can also work with Jupyter notebooks in a browser by running this command:

    ```bash
    jupyter notebook
    ```

    A browser window should open with the Jupyter notebook interface. You can now navigate to and open any Jupyter notebooks (with extension `.ipynb`).

We strongly recommend you duplicate and work with a copy of any given notebook rather than working with the original. Feel free to ignore this suggestion if you are a `git` expert.
