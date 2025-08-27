---
layout: page
title: Python Setup
permalink: /python-setup/
nav_order: 3
---

# How to Set Up a Python Programming Environment <!-- omit from toc -->

## Table of Contents <!-- omit from toc -->
- [Introduction](#introduction)
- [Install Miniconda and a Python interpreter](#install-miniconda-and-a-python-interpreter)
  - [MacOS](#macos)
  - [Windows](#windows)
- [Do this every time](#do-this-every-time)
- [Install VS Code](#install-vs-code)
- [Set Up a Project for this Tutorial](#set-up-a-project-for-this-tutorial)
- [Complete the Python Refresher Assignment](#complete-the-python-refresher-assignment)

## Introduction

This tutorial aims to:

- help you set up a Python programming environment for completing coding assignments, doing research, or working with with RSOs
- help you use Conda to manage packages in Python
- have you use your programming environment and Conda to complete a Python refresher assignment

Some of steps are based on the [Visual Studio Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial).

## Install Miniconda and a Python interpreter

We suggest installing a Python interpreter through Anaconda, since Anaconda includes Conda (which we suggest using for package management) and a Python interpreter.

If you are not familiar with command-line tools, we recommend reviewing the [command-line basics](/resources/commandline-basics/) before proceeding.

### MacOS

**Install Xcode Command Line Tools**

Open a terminal and run this command, accepting all default options:

```bash
xcode-select --install
```

You may be asked to restart your computer during or after this process. Please do so if prompted.

**Install conda**

[Conda](https://docs.conda.io/) is a package manager that you will use to install Python, along with a number of required tools.

1. First, check if conda is already installed by trying to update it:

   ```bash
   conda update -n base conda
   ```

   If this process succeeds, then conda is installed, and you can skip to the next step. If this process does not succeed, continue with the installation below.

2. Go to the [Miniconda installer page](https://www.anaconda.com/download/success) and download the appropriate `.pkg` file for your Mac architecture:
   - For Intel Macs: Download "Miniconda3 macOS Intel x86 64-bit pkg"
   - For Apple Silicon Macs (M1/M2): Download "Miniconda3 macOS Apple M1 64-bit pkg"

3. Double-click the downloaded `.pkg` file and accept all the default options during installation.

4. After installation, restart your terminal (close and open the terminal).

**Create a conda environment**

An "environment" is like a sandbox where you can install software without causing any conflict with other things you might have installed on your computer. To create an environment for your project work, open a terminal and run this command:

```bash
conda create -n my-project
```

You may see something like `WARNING: A conda environment already exists` and be asked if you want to `Remove existing environment`. This means that you already created an environment with that name. Perhaps something went wrong and you are creating it again — in this case, type `y` to remove the existing environment and proceed to recreate it. From then on, accept all default options.

Finally, run the following commands (copy the entire thing, paste it into your terminal, and press return):

```bash
conda activate my-project
conda install -y python=3 numpy scipy matplotlib notebook ipywidgets
```

**Verify Installation**

Open a new terminal and run:

```bash
conda --version
```

You should see the conda version number if the installation was successful.


**Start a jupyter notebook (optional)**

If you want to work with Jupyter notebooks, run this command:

```bash
jupyter notebook
```

A browser window should open with the jupyter notebook interface. You can now navigate to and open any of the notebooks (with extension `.ipynb`).

We strongly recommend you duplicate and work with a copy of any given notebook rather than working with the original. Feel free to ignore this suggestion if you are a `git` expert.

### Windows

**Install conda**

[Conda](https://docs.conda.io/) is a package manager that you will use to install Python, along with a number of required tools.

1. First, check if conda is already installed:
   - Try to open "Anaconda Powershell Prompt (Miniconda)" from the Windows Start menu
   - If you can open it, run the following command to update conda:

     ```powershell
     conda update -n base conda
     ```

   If this process succeeds, then conda is installed properly, and you can skip to the next step. If you cannot open the Anaconda Powershell or the update fails, continue with the installation below.

2. Go to the [Miniconda installer page](https://www.anaconda.com/download/success) and download the "Miniconda3 Windows 64-bit" installer (the `.exe` file).

3. Double-click the downloaded `.exe` file and accept all the default options during installation.

4. After installation, you should be able to find "Anaconda Powershell Prompt (Miniconda)" in your Windows Start menu.

**Create a conda environment**

An "environment" is like a sandbox where you can install software without causing any conflict with other things you might have installed on your computer. To create an environment for your project work, open an anaconda powershell and run this command:

```powershell
conda create -n my-project
```

You may see something like `WARNING: A conda environment already exists` and be asked if you want to `Remove existing environment`. This means that you already created an environment with that name. Perhaps something went wrong and you are creating it again — in this case, type `y` to remove the existing environment and proceed to recreate it. From then on, accept all default options.

Finally, run the following commands (copy the entire thing, paste it into your powershell, and press enter):

```powershell
conda activate my-project
conda install -y python=3 numpy scipy sympy matplotlib notebook ipywidgets
```


**Verify Installation**

1. Open "Anaconda Powershell Prompt (Miniconda)" from the Windows Start menu.

2. Run the following command to verify the installation:

   ```powershell
   conda --version
   ```

   You should see the conda version number if the installation was successful.
## Do this every time

**Change your working directory**

Open a terminal and change your working directory to your project folder, wherever you put this.

**Activate your conda environment**

Run this command:

```bash
conda activate my-project
```

You should see the prefix to your terminal prompt change from `(base)` to `(my-project)`. This means you are in the conda environment you created for your project work.


**Start a jupyter notebook (optional)**

If you want to work with Jupyter notebooks, run this command:

```powershell
jupyter notebook
```

A browser window should open with the jupyter notebook interface. You can now navigate to and open any of the notebooks (with extension `.ipynb`).

We strongly recommend you duplicate and work with a copy of any given notebook rather than working with the original. Feel free to ignore this suggestion if you are a `git` expert.

**Note for Windows Users**: When the instructions refer to opening a "terminal" or "command prompt", you should use the "Anaconda Powershell Prompt (Miniconda)" application instead of the regular Windows Command Prompt or PowerShell.

## Install VS Code

An integrated development environment (IDE) "is a software application that helps programmers develop software code efficiently. It increases developer productivity by combining capabilities such as software editing, building, testing, and packaging in an easy-to-use application. Just as writers use text editors and accountants use spreadsheets, software developers use IDEs to make their job easier" (from [Amazon AWS](https://aws.amazon.com/what-is/ide/#:~:text=An%20integrated%20development%20environment%20(IDE,programmers%20develop%20software%20code%20efficiently.))).

We suggest installing [Visual Studio Code](https://code.visualstudio.com/) (VS Code). Go to [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download) to download and install VS Code.

Some popular alternatives are:
- [Jupyter Notebook App](https://jupyter.org/). The Jupyter Notebook App is an easy way to work with Python and should already be installed through Anaconda.
- [PyCharm](https://www.jetbrains.com/pycharm/). PyCharm is a popular IDE that is pretty easy to use out of the box. The free version is fine, though student licenses are available for the pro version [here](https://www.jetbrains.com/community/education/#students).
- [Atom](https://atom.io/). Atom is a text editor that is a lightweight alternative to full IDEs with plug-ins available to give more features than simple Jupyter notebooks.

## Set Up a Project for this Tutorial

You should organize your code files into directories (or folders) based on projects (or assignments). For example, you might store files for this tutorial in a `computing-readiness` folder within a `projects` folder (where you store all coursework) within your `Documents` folder, organized like this:

    ├── Documents
    │   ├── personal
    │   ├── projects
    │       ├── ae202
    │       ├── ae370
    │       ├── computing-readiness
    │           ├── python-refresher.ipynb

You should then create and use a separate Conda environment for each project. VS Code provides a good explanation for why: "A best practice among Python developers is to use a project-specific virtual environment. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions."

1. Create a folder for the files associated with this tutorial.

    You can create this folder in the command prompt using the following commands (assuming the folder structure shown above):

        # change your working directory to your home directory
        cd

        # show the folders within your home directory (optional)
        ls

        # change your working directory to the Documents folder
        cd Documents

        # make a projects folder (if needed)
        mkdir projects

        # change your working directory to your projects folder
        cd projects

        # make a computing-readiness folder
        mkdir computing-readiness

        # change your working directory to the computing-readiness folder
        cd computing-readiness

1. Start VS Code in your `computing-readiness` folder. Open VS Code, go to VS Code's File > Open Folder, and select your `computing-readiness` folder.

1. Create a Conda environment for this computing-readiness project.

    A Conda cheatsheet of common Conda commands can be found [here](https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf).

    1. Open your command prompt.
    
        You can open a command prompt (the working directory will be your current VS Code workspace folder) within VS Code by:
        
        1. Open the Command Palette by going to VS Code's View > Command Palette
        1. Search for "Create New Terminal With Profile" and select the command. I would suggest selecting "bash" as the shell interpreter.

    1. Create a new Conda environment named "computing-readiness".

            # create the conda environment
            conda create --name computing-readiness

        Your command prompt should show something like the following:
        
            Channels:
            - defaults
            Platform: osx-arm64
            Collecting package metadata (repodata.json): done
            Solving environment: done

            ## Package Plan ##

            environment location: /Users/httran/anaconda3/envs/computing-readiness



            Proceed ([y]/n)? 

        Enter `y` to proceed.

    1. Active your computing-readiness Conda environment. Any packages you install with Conda will now be installed in this Conda environment.

            # activate the conda environment
            conda activate computing-readiness

    1. Install Python 3 and Jupyter in your Conda environment (install Python 3.11 because Jupyter only supports up to 3.11).

            # install python 3.11
            conda install python=3.11

        Enter `y` to proceed.

            # install jupyter
            conda install jupyter

        Enter `y` to proceed.

    1. Select your Conda environment to use for this project workspace in VS Code.

        1. Open the Command Palette by going to VS Code's View > Command Palette
        1. Search for "Python: Select Interpreter" and select the command.
        1. Select the Conda environment you just created and installed Python in "Python 3.13.1 ('computing-readiness') ... Conda".

## Complete the Python Refresher Assignment

You can now use your VS Code workspace and Conda environment to complete the `python-refresher.ipynb` file found [here](/assets/files/python-refresher.ipynb).

You may want to ensure that the correct Conda environment is being used by VS Code. You may need to install the `numpy` and `matplotlib` packages to your Conda environment to complete the assignment.
