---
layout: page
title: Python Setup (Windows)
permalink: /python-setup-windows/
nav_order: 2
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
- [Do this every time you work on a course](#do-this-every-time-you-work-on-a-course)


## Introduction

This tutorial aims to:

- help you set up a Python programming environment for coding assignments, research, or working with RSOs
- have you use your programming environment to complete a Python refresher assignment

Some of the steps are based on the [Visual Studio Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial).

{: .note-title}
> How to open a terminal
>
> When we say "open a terminal" on Windows, we recommend starting the **Anaconda Powershell Prompt** (which is installed with Miniconda):
> 
> * Click the Start menu (or press the Windows key).
> * Type "Anaconda Powershell Prompt" in the search field.
> * Click **Anaconda Powershell Prompt**.
>
> Note: Depending on your installation, it may appear as "Anaconda Powershell Prompt (Miniconda3)" or "Anaconda Prompt (Miniconda3)." Either works, but Powershell Prompt is recommended.
> 
> See documentation on [Anaconda Prompt](https://docs.anaconda.com/working-with-conda/reference/glossary/#anaconda-prompt) for more information.

{: .note-title}
> How to run a command
> 
> When we say "run a command," what we mean is to type something into the terminal window and press Enter. For example, suppose we said:
> 
> > run the command `pwd` to find your current working directory
> 
> You would type `pwd` into the Anaconda Powershell Prompt window and press Enter, with the result showing your current location:
> 
> ```powershell
> (base) PS C:\Users\username> pwd
> 
> Path
> ----
> C:\Users\username
> ```
> 
> See documentation on [Windows Commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands). Also see the [command-line basics](/resources/commandline-basics/) or [Command Line Primer](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/CommandLInePrimer/CommandLine.html) page for a list of frequently used commands.


## Install Miniconda

[Conda](https://docs.conda.io/) is a package management system that includes Python. We suggest you install Miniconda to install conda and Python.

### Install Miniconda

1. Check if conda is already installed by searching for "Anaconda Powershell Prompt" in the Start menu.

   If it is found and opens successfully, conda is already installed, and you can skip to [Verify Installation](#verify-installation). If not found, continue with the installation below.

2. Go to the [Miniconda installation page](https://docs.anaconda.com/miniconda/) and download the **Miniconda Windows 64-bit** installer (`.exe`).

3. Double-click the downloaded `.exe` file and follow the setup wizard:
   - Accept the default destination folder and default installation options.
   - Click **Install** and wait for the setup to complete.

4. After installation finishes, open the Start menu, search for **Anaconda Powershell Prompt**, and open it.

### Verify Installation

In your Anaconda Powershell Prompt window, run:

```bash
conda --version
```

You should see the conda version number (e.g., `conda 24.x.x`) if the installation was successful.

## Install VS Code

We suggest installing [Visual Studio Code](https://code.visualstudio.com/) (VS Code) to use as your integrated development environment (IDE) for writing Python code.

### Install VS Code

1. Follow the instructions on the [Install VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page to download the Windows User Installer.
2. Run the downloaded installer (`.exe`).
3. During installation, accept the license agreement and ensure the option **"Add to PATH (requires shell restart)"** remains checked.
4. Complete the installation wizard.

### Install the Python and Jupyter Extensions

1. Open the VS Code application.
2. Click the **Extensions** icon in the **Activity Bar** on the left-hand side of VS Code (or press **Ctrl + Shift + X**).
3. Install the Python extension:
   1. Type "Python" into the search bar.
   2. Click the **Python** extension (by Microsoft) and click the **Install** button.
4. Install the Jupyter extension:
   1. Type "Jupyter" into the search bar.
   2. Click the **Jupyter** extension (by Microsoft) and click the **Install** button.

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
> To do this, we run the command:
> 
> ```powershell
> cd path\to\directory
> ```
> 
> where `path\to\directory` is replaced by the location of the directory in which you want to work. One easy way to find this location (i.e., the "path" to your directory) is by dragging its folder from **File Explorer** into your Anaconda Powershell Prompt window. In particular, I would first type `cd ` (note the single trailing space):
> 
> ```powershell
> (base) PS C:\Users\username> cd 
> ```
> 
> Then, I would drag a folder into the terminal window and press Enter. For instance, suppose I had created a folder called `computing-readiness` somewhere on my computer and dragged it in, then pressed Enter --- I would see something like this:
> 
> ```powershell
> (base) PS C:\Users\username> cd C:\Users\username\Documents\projects\computing-readiness\python-refresher
> (base) PS C:\Users\username\Documents\projects\computing-readiness\python-refresher>
> ```
> 
> See documentation in the [cd](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/cd) page for other ways to specify the path to a directory.

You can create the `computing-readiness` folder and assignment structure shown above by opening Anaconda Powershell Prompt and running the following commands. **Note that lines starting with a "#" symbol are comments, not commands to enter.**

```powershell
# navigate to your Documents folder
cd ~\Documents

# show the folders within your current directory (optional)
dir

# make a projects folder (if needed)
mkdir projects

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

Create a conda environment for your course (replacing "my-course" with your course name, e.g., `computing-readiness`) by opening Anaconda Powershell Prompt and doing the following:

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

1. Open **Anaconda Powershell Prompt**.
2. Change your working directory to your assignment directory. For example, assuming the directory structure shown in [Create a folder for the course and assignment](#create-a-folder-for-the-course-and-assignment), you could run:

    ```powershell
    cd ~\Documents\projects\my-course\my-assignment
    ```

    *(For this refresher tutorial, use `cd ~\Documents\projects\computing-readiness\python-refresher`)*

3. Activate your conda environment by running:

    ```bash
    conda activate my-course
    ```

    You should see the prefix to your terminal prompt change from `(base)` to `(my-course)`. This means you are in the conda environment you created for your course.

    As an alternative, you can also select your conda environment to use while working in VS Code:

    1. Open the Command Palette in VS Code (**Ctrl + Shift + P** or **View** > **Command Palette...**).
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
