# Setting up Visual Studio Code, Node.js, and GIT BASH for WINDOWS

## Lesson Objectives

_After this lesson, you will be able to:_

1. Download and install software necessary
1. Integrate and Open Terminal
1. Describe what a command line interface is
1. Describe the state of the current directory
1. Change Directories
1. Create files and folders
1. Navigate using relative pathing on the command line
1. Navigate using absolute pathing on the command line
1. Run some code

## Download and install software

- For our environment we will be using VSC, NODE, and GIT BASH
    - [Download VSCode](https://code.visualstudio.com/)
    - Download for Windows (Stable Build)
    - VSCode, an integrated development environment (IDE), is a software application that provides comprehensive facilities to computer programmers for software development. An IDE normally consists of at least a source code editor, build automation tools and a debugger.

    - [Download NODE.js](https://nodejs.org/en/)
    - Download for Windows (LTS)
    - Node. js is a platform built on Chrome's JavaScript runtime for easily building fast and scalable network applications. In short, it is what helps you run and control your application.

    - [Download GIT BASH](https://git-scm.com/downloads)
    - Download the newest release for Windows.
    - Git is the most commonly used version control system. Git tracks the changes you make to files, so you have a record of what has been done, and you can revert to specific versions should you ever need to. Git also makes collaboration easier, allowing changes by multiple people to all be merged into one source.


## Integrate and Open Terminal

- Your normal workflow includes working in the IDE(VSCode) and using the GIT terminal. Here we are going to learn how to integrate the GIT terminal into VSC for an easier time.

1. Open VSC
2. Open Visual Studio Code and press and hold `Ctrl` + **`** to open the terminal.

![](https://i.stack.imgur.com/V4hx4.png)

3. Open the command palette using `Ctrl` + `Shift` + `P`.
4. Type "Select Default Shell".
5. Select Git Bash from the options.
6. Click on the + icon in the terminal window.
7. The new terminal now will be a Git Bash terminal. Give it a few seconds to load Git Bash.

![](https://i.stack.imgur.com/5zLAP.png)

8. You can now toggle between the different terminals as well from the dropdown in terminal. *PowerShell* is a more advanced version of cmd. It is not only an interface but also a scripting language that is used to carry out administrative tasks more easily. *GIT* is more commonly used and works well with GitHub.

![](https://i.stack.imgur.com/1AGtr.png)


## Describe what a command line interface is

Terminal provides a Command Line Interface (CLI) to the operating system. With it you can give your computer direct, text-based instructions. It is the most powerful piece of software on your computer! Think of it as the central hub of your development process. For now, we will use it to navigate the files and folders in our computer.

When terminal launches with VSC, it will start in your computer's home directory (whatever you named your computer). Your home directory is denoted by the tilde `~`.

In Terminal-land, **Directories** are the same as **Folders** (we just call them **Directories**).

> NOTE: SUPPORTING IMAGES WILL NOT BE 100% REFLECTIVE OF WHAT YOU SEE ON YOUR SCREEN. FOCUS ON THE SPECIFIC DETAILS SUCH AS THE _NOTATION_ AND THE _TERMINOLOGY_

![](https://i.imgur.com/tTyOkwV.png)

In **Windows Explorer**, we can also navigate our computer's folders and files: folders contain files and more folders.


## Describe the state of the current directory

**WE ARE NOW WORKING IN THE TERMINAL**

The Command Line understands commands written in the `bash scripting language`. The commands are abbreviations of English words, or acronyms.

- `pwd` - will print the current working directory. It shows you a `path`. This `path` shows you where you are currently located in the filesystem. It's like sending up a flare or homing beacon, where you can see how far you have 'traveled' from the root directory.

![](https://i.imgur.com/4aaT88x.png)

- `ls` - Lists the contents of the current directory. You can see
	* the immediate _child_ directories (the directories inside this directory)
	* the files in this directory

![](https://i.imgur.com/H2RTUny.png)

- Bash commands can take `flags` denoted by a dash `-`
	- `ls -a` - list content including hidden files and directories. Hidden files and directories begin with a period, for example, `.git`.
	- `ls -l` - list content and give meta information about each item

Directories (folders) can have directories within them, and there can be directories inside _those_ directories, ad infinitum. This creates a tree structure where directories can have many children with many different branches.

![](http://i.imgur.com/M6OgKZJ.png)


## Change Directories

We can navigate to other directories _relative_ to the current working directory.

- `cd some_directory`
	- navigates into a child directory called `some_directory`. `some_directory` is a child of the current directory.
- `cd ..`
	- navigates into the parent of the current directory
	- `..` is shorthand for parent
- `cd` will take you back home


## Create files and folders

- `mkdir`
	- makes a directory
	- Example:
		- `mkdir directory_name`
			- makes a directory called 'directory_name'`
- `touch`
	- creates an empty file
	- A file typically will have a **file extension** like `.txt` whereas a directory will not.
	- Example:
		- `touch file.txt`
			- makes a .txt file


### Activity (10 min)

**Construct a Labyrinth**

Using what you know about navigating directories and creating files and folders, construct a 'labyrinth' on your desktop.

**Precision** is important. There are a few layers to this exercise. Be patient.

- Make sure you are in the correct directory when you go to create another directory or file.
- Make sure you use `touch` to make files, and `mkdir` to make directories. **files** and **directories** are two different things.

* Navigate to Desktop
* `mkdir Labyrinth`, `cd Labyrinth`
* Make a directory structure like this:

![labyrinth](https://i.imgur.com/pY0MxS8.png)

**parlor** and **stairway** are _child directories_ of the Labyrinth directory.

**sarah_williams.txt** is a _file_ inside the the ballroom directory.

If you make a mistake, don't worry, just keep adding the right stuff to the right place.

## Navigate using relative pathing on the command line

Chain more directories to the current path with the `/` separator

- Go down the chain into child directories
	- `cd parent_directory`
	- `cd parent_directory/child_directory`
	- `cd parent_directory/child_directory/grandchild_directory`

- Go up the chain into parent directories
	- `cd ..`
	- `cd ../..`
	- `cd ../../..`

- Go sideways into a _sibling_ directory by first going up, then down
	- `cd ../sibling_directory`

- Go into an _aunt_ or _uncle_ directory by first going up to the parent, then the grandparent, then down again on another branch:

	- `cd ../../auntie_directory`


### Activity

**Navigate the Labyrinth**

* Navigate to the Labyrinth root directory
* From the Labyrinth root directory, navigate to the `stairway`
* From the `stairway`, navigate to the `parlor`
* From the `parlor`, navigate to the `dining room`
* From the `dining room`, navigate to the `escher room`
* From the `escher room`, navigate to the Labyrinth root


### Activity (10 min)

**Navigate the Labyrinth**

For each of these, write your command on one line, using full paths:

* Navigate to the Labyrinth root directory
* From the Labyrinth root directory, navigate to the `dining_room`
* From the `dining room`, navigate back up the root directory
* From the Labyrinth root directory, navigate to the `stairway`
* From the `stairway`, navigate to the `parlor`
* From the `parlor`, navigate to the `escher_room`
* From the `escher room`, navigate to the `throne_room`
* From the `throne_room`, navigate to the `ball_room`


## Navigate using absolute pathing on the command line

Move anywhere relative to the home directory:

`cd ~/` - the path starts in home directory

Example:

- `cd ~/Desktop/Labyrinth/stairway/escher_room`

Navigates to the escher room _no matter where_ you are currently located in your filesystem

> NOTE: You can combine absolute and relative pathing when copying or moving files from one location to another with `cp` and `mv`.


### Activity (3 min)

**Navigate the Labyrinth**

Using absolute pathing:

* Navigate to the throne_room
* Navigate to the ballroom
* Navigate to the parlor


## Run some code

We are going to:

* make a file
* open it in our text editor
* write some code
* run the code in Terminal