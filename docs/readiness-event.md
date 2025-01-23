---
layout: page
title: Tutorial
permalink: /tutorial/
nav_order: 3
---

# AE Computing Readiness Event

## Table of Contents
1. [Introduction](#introduction)
2. [Set Up a Python Programming Environment](#set-up-a-python-programming-environment)
3. [Install Anaconda and a Python interpreter](#install-anaconda-and-a-python-interpreter)
4. [Install an Integrated Development Environment](#install-an-integrated-development-environment)
5. [Set Up a VS Code Workspace and Conda Environment for this Tutorial](#set-up-a-vs-code-workspace-and-conda-environment-for-this-tutorial)
6. [Complete the Python Refresher Assignment](#complete-the-python-refresher-assignment)

## Introduction

This tutorial aims to:

- help you set up a Python programming environment for completing coding assignments, doing research, or working with with RSOs
- help you use Conda to manage packages in Python
- have you use your programming environment and Conda to complete a Python refresher assignment

Some of steps are based on the [Visual Studio Code Python tutorial](https://code.visualstudio.com/docs/python/python-tutorial).

## Set Up a Python Programming Environment

### Install Anaconda and a Python interpreter

We suggest installing a Python interpreter through Anaconda, since Anaconda includes Conda (which we suggest using for package management) and a Python interpreter.

1. Go to [https://www.anaconda.com/download](https://www.anaconda.com/download) to download and install Anaconda.
1. After installation, test that Anaconda was properly installed.

    1. Open the command prompt (Windows) or terminal (macOS).

        - Windows users: you can open the command prompt by searching for "cmd" in the start menu.

        - macOS users: you can open the terminal by pressing `Command + Space bar` and searching for "terminal" in Spotlight Search.

    1. Type the following in the command prompt (Windows) or terminal (macOS) and hit `Enter`.

            conda -V

    1. You should see something like this:

            conda 25.1.0

1. Test that Python was properly installed.

    1. Windows users: type the following in the command prompt and hit `Enter`.

            py -3 --version

        macOS users: type the following in the command prompt and hit `Enter`.

            python3 --version

    1. You should see something like this:

            Python 3.11.11

### Install an Integrated Development Environment

An integrated development environment (IDE) "is a software application that helps programmers develop software code efficiently. It increases developer productivity by combining capabilities such as software editing, building, testing, and packaging in an easy-to-use application. Just as writers use text editors and accountants use spreadsheets, software developers use IDEs to make their job easier" (from [Amazon AWS](https://aws.amazon.com/what-is/ide/#:~:text=An%20integrated%20development%20environment%20(IDE,programmers%20develop%20software%20code%20efficiently.))).

We suggest installing [Visual Studio Code](https://code.visualstudio.com/) (VS Code) but you are free to use any other IDE. Go to [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download) to download and install VS Code.

Some popular alternatives are:
- [Jupyter Notebook App](https://jupyter.org/). The Jupyter Notebook App is an easy way to work with Python and should already be installed through Anaconda.
- [PyCharm](https://www.jetbrains.com/pycharm/). PyCharm is a popular IDE that is pretty easy to use out of the box. The free version is fine, though student licenses are available for the pro version [here](https://www.jetbrains.com/community/education/#students).
- [Atom](https://atom.io/). Atom is a text editor that is a lightweight alternative to full IDEs with plug-ins available to give more features than simple Jupyter notebooks.

## Set Up a VS Code Workspace and Conda Environment for this Tutorial

1. Create a folder for the files associated with this tutorial.

    For example, you might store files for this tutorial in a `computing-readiness` folder within a `projects` folder (where you store all coursework) within your `Documents` folder (macOS), organized like this:

    ```bash
    ├── Documents
    │   ├── personal
    │   ├── projects
    │       ├── ae202
    │       ├── ae370
    │       ├── computing-readiness
    │          ├── python-refresher.ipynb
    ```

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

        # make a computing-readiness folder and change your working directory to it
        mkdir computing-readiness
        cd computing-readiness

1. Start VS Code in your `computing-readiness` folder. Open VS Code, go to VS Code's File > Open Folder, and select your `computing-readiness` folder.

1. Create a Conda environment for this computing-readiness project.

    VS Code provides a good explanation for why you should use project-specific virtual environments (like Conda environments): "A best practice among Python developers is to use a project-specific virtual environment. Once you activate that environment, any packages you then install are isolated from other environments, including the global interpreter environment, reducing many complications that can arise from conflicting package versions."

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
