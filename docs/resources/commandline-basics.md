---
layout: page
title: Command-line Basics
permalink: /resources/commandline-basics/
nav_order: 2
parent: Resources
---

# Command-line basics <!-- omit from toc -->
## Table of Contents <!-- omit from toc -->
- [How to open a terminal](#how-to-open-a-terminal)
- [How to run a command](#how-to-run-a-command)
- [How to change the working directory](#how-to-change-the-working-directory)

## How to open a terminal

**On macOS:**
When we say "open a terminal," what we mean is to start the Terminal application. Here is one way to do that:

- Click the Launchpad icon in the Dock.
- Type "Terminal" in the search field.
- Click Terminal.

See documentation on [Open Terminal](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac) for more information. Note that it is often helpful to have more than one terminal window open at the same time (or more than one tab in the same window).

**On Windows:**
When we say "open an anaconda powershell," what we mean is to start the Anaconda Powershell Prompt (Miniconda) application. Here is one way to do that:

- Click the Windows search bar near the bottom-left corner of your desktop.
- Type "anaconda" into the search field.
- Click Anaconda Powershell Prompt (Miniconda).

Note that this application will only exist after you follow the instructions to Install conda.

## How to run a command

When we say "run a command," what we mean is to type something into the terminal window and press return/enter. For example, suppose we said:

> run the command `pwd` to find your current working directory

**On macOS:**
You would type `pwd` into the terminal window and press return, with the result being something like this:

```bash
(base) username@computer ~ % pwd
/Users/username
```

**On Windows:**
You would type the command into the anaconda powershell window and press enter. See [this beginners guide](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/) to [Windows Commands](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands).

## How to change the working directory

All the files on your computer are organized in folders, which are commonly referred to as "directories." When you are working on the command line in a terminal, you are working in one of these directories. Commands you run can find files in that directory, but cannot (by default) find files in other directories.

When we say "change the working directory," we mean exactly that — telling the terminal the directory in which you want to work.

**On macOS:**
To do this, we run the command:

```bash
cd path/to/directory
```

where "`path/to/directory`" is replaced by the location of the directory in which you want to work. One easy way to find this location (i.e., the "path" to your directory) is by dragging its folder from the Finder into your terminal window (see documentation on [Drag items into a Terminal window on Mac](https://support.apple.com/guide/terminal/drag-items-into-a-terminal-window-trml106/mac)). In particular, I would first type "`cd `" (note the single trailing space):

```bash
(base) username@computer ~ % cd 
```

Then, I would drag a folder into the terminal window and press return. For instance, suppose I had created a folder called `my-project` somewhere on my computer and dragged it in, then pressed return — I would see something like this:

```bash
(base) username@computer ~ % cd /Users/username/Documents/my-project
(base) username@computer my-project %
```

**On Windows:**
To do this, we run the command:

```powershell
cd path\to\directory
```

where "`path\to\directory`" is replaced by the location of the directory in which you want to work. One easy way to find this location (i.e., the "path" to your directory) is by dragging its folder from the File Explorer into your powershell window. In particular, I would first type "`cd `" (note the single trailing space):

```powershell
C:\Users\username>cd 
```

Then, I would drag a folder into the powershell window and press enter. For instance, suppose I had created a folder called `my-project` somewhere on my computer and dragged it in, then pressed enter — I would see something like this:

```powershell
C:\Users\username>cd C:\Users\username\OneDrive\Documents\my-project
C:\Users\username\OneDrive\Documents\my-project>
```