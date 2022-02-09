# Session 2

## The Shell

### What is a Shell?
Look at the following diagram:

![os layers](../imgs/layers.jpg)

**The GUI:** Graphical User Interface, used to allow the user to interact with the system by using a graphical interface.

**The Shell:** Allows the user to use the OS by typing commands.

**The Kernel:** The core of the OS, responsible for memory management, and communication with the hardware.

The shell is the first user-friendly layer that a user can use to interact with the operating system.

**Examples:** sh, bash, zsh, csh and fish.

## Terminal vs Shell vs Prompt

### Terminal
In the early days of computing, terminals where physical devices connected to a central computer in Universities and Research facilities. 

Here's an sample "dumb" terminal. Internally it does not have a microprocessor, it's connected to a master computer.

<img src="../imgs/terminal.jpg" width="500" height="500">

Nowadays, personal computers and laptops are cheap and accessible. The lead to the extinction of Terminals. Instead, the Terminal Emulators gave rose and replaced the functionalities of the old physical terminals. 

A terminal emulators is a program that emulates a real terminal connected to your machine. In other words, it provides you with the Shell.

In your Linux machine, search for "Terminal" and open it to view a terminal.

It should look something like this:

<img src="../imgs/terminal-emulator.png">


### Shell
We have already discussed what a shell is. Shells run inside terminal emulators which means that the terminal won't be useful without a shell running in it.
The terminal sample showen above is running the *bash* shell.

It looks something like this:

![TTY](../imgs/Linux_shell.jpg)

**Note:** you can run Bash without opening up a terminal emulator. More on that later.

### Prompt
When you open the terminal you’ll see something like this:

![prompt1](../imgs/command_line_prompt.jpg) 
![prompt2](../imgs/command_line_prompt-2.jpg)

It is prompting you to enter a command, let’s break it down:

```osc/root``` : The username of the current logged in user.

```@```: Defines that you are connected to the machine that has the name after it

```mint```: The name of the computer running (Name of the host)

```~```: The working directory, the directoy that the terminal is working in right now.

```$```: States that you are logged in as a regular user.

```#```: States that you are logged in as the system administrator (root).

So we can basically summarise it to the following:

```USERNAME@HOSTNAME:WORKING_DIRECTORY($/#)```


## The Command Line Syntax
When ordering the computer to do something, **i.e giving it a command**, you have to take care of the syntax.

Just like programming languages, the Linux shell has specific syntax that you have to use. Just so that it could be understood by the shell.

The syntax goes as follows:
![command-line-syntax](../imgs/command_line_syntax.jpg)

**The Command:** Intuitively, this is the command that you give to the system, i.e.
delete, move, copy, list, etc..

**The Option:** Modifies the action of the command.

**Example:** List “ALL” files, delete “recursively”, show the first “40” lines of a file, delete the file “by force”

**The Arguments:** What you’re going to apply the command to. i.e. Delete (command) a certain file (argument). We can say in short that the options modify the command’s effect on the argument.

#### Let’s take the ls command as an example:
```ls``` – lists the content of a directory(folder).

Running the command ls does the following:
![](../imgs/ls_command.jpg)

But that format isn’t really good if you want a detailed view, so we add the ```-l``` option which makes it list the content but in a “long” form:

![](../imgs/ls-l_command.jpg)

Much better! Everything is clealer and organised in a list.

How about we take a look at the hidden files too?

The ```-a``` option lists “all files”, this command can be shortened down to ```ls -la``` or ```ls -al```

**Note: Hidden files and directories in Linux start their name with a dot”.”.**
![](../imgs/ls-l-a.jpg)

# Filesystems
## What is a filesystem?
A filesystem is the way that the files are stored on a storage device (i.e. Hard Drive, USB Flash Drive, etc..).

Each operating system uses a certain filesystem:
![](./Images/Session%202/filesystem.png)

**Note: Linux supports NTFS and FAT32, but Windows doesn’t support EXT4 or XFS, that’s why you can’t see the Linux partitions on Windows.**

## Windows Directory Structure
A directory structure is the way an operating system's files are arranged displayed to the user.
![](./Images/Session%202/windows_directory_structure.png)

Windows, like every operating system, has a specific directory structure for its **NTFS** file system. Each disk is assigned a letter, and you browse your files based on that. 

**Note: C:\ and D:\ could be 2 seperate physical hard drives.**


Linux also has a directory structure, called **“Filesystem Hierarchy Standard”** or **“The Linux Filesystem Hierarchy”**.


# Linux Filesystem Hierarchy
### The root ‘/’ directory
The ‘/’ directory or the “root” directory is where everything begins on Linux.

No matter what you want to access, where it is, it will somehow connect to the
root directory.

#### Here’s a demonstration of the Linux Filesystem Hierarchy:

![](../imgs/linux_filesystem.png)

From the previous, we can see that: “Everything in Linux is a file”. 
Even devices and processes, everything is a file under the ‘/’ directory somehow.

**Note: C:\ and D:\ here are not accessed as C:\ or D:\\, but instead as directories under ‘/’.**

**Let’s test it out!**
![](../imgs/ls_root.jpg)
If we list the content of the root directory using the ```ls``` command, we will find the directories in the previous diagram.

Now we know what a filesystem, directory, and file are. Let’s talk about how we can access them.

## Navigating through the filesystem

You opened a terminal, now what?
The first thing you want to do is to know where the terminal is working:

![](../imgs/pwd.jpg)

```pwd```: Print Working Directory, tells you the directory your terminal is working in.

![](../imgs/ls.jpg)

Now that you know where you are in the system, you should see the content of
the directory using the ```ls``` command.

What if we wanted to enter the Pictures directory?

![](../imgs/cd.jpg)

```cd```: Change Directory, changes the working directory to the specified argument.

Now the working directory is Pictures, notice how the text before **$** also changed to **~/Pictures** which is the same as **/home/osc/Pictures**, which is the working directory.

What if I wanted to go back to the home directory?
There are 4 ways:
* ```cd ~```: This basically means cd /home/osc since ~ means the home directory of the current user.
* ```cd /home/osc```: Tells the shell to change the working directory to /home/osc.
* ```cd```: Running the cd command without an argument takes you to the home directory by default.
* ```cd ..```: .. refers to the parent directory, continue reading:

### The ```.``` and ```..``` Links
Each directory has 2 hidden files (links) in it, ```.``` and ```..```.

The ```.``` link refers to the directory itself.

The ```..``` link refers to the directory before it (parent directory).

Example: If the working directory is /home/osc/Pictures/, then:

```‘.’ = /home/osc/Pictures/``` and ```‘..’ = /home/osc/``` which is the directory before it.

To verify:

![](../imgs/verify_'.'_and_'..'.jpg)

This can be a little confusing at first, so practice with yourself and maybe try drawing it on a piece of paper to visualise how things really work.

### Relative and absolute paths

Let’s simplify this by taking a guy called “Jack” as an example, Jack goes to FCIS ASU every day, this is the path he takes daily:
![](../imgs/relative_and_absolute_path.png)

Jack’s route to college daily is **Home->Bus Stop->Abbassia->FCIS ASU.**

If he met someone at Abbassia and asked him: “Where are you going?”, Jack’s response will be **“FCIS ASU”** only, because that’s the next step.
If someone asked Jack “What’s your full route to college?”, Jack’s response would be **“ Home->Bus Stop->Abbassia->FCIS ASU”.**

**Note that his route from Abbassia is shorter because it is relative to Abbassia.**

The same thing applies in Linux for directories and files.

**Absolute Path:** The total path leading to the directory.

**Relative Path:** The path relative to the working directory.

**Example:**
In the diagram, let the working directory be /home/User1

![](../imgs/example_absolute_and_relative_path.png)

The relative path for “Videos” would be: Videos

The absolute path would be: /home/User1/Videos

##### Test yourself(Solution at the end):
In the same diagram, let the working directory be /home/User1 and the user you’re logged in as called User1.

* Which directory does ‘.’ refer to?
* Which directory does ‘..’ refer to?
* What would be the working directory if you run ```cd ..```?
* What would be the working directory if you run ```cd .```?
* What would be the working directory if you run ```cd``` Videos?
* What would happen if you run ```cd ../User2/```?
* What would happen if you run ```cd```?
* What would happen if you run ```cd User2```?
* What would happen if you run ```cd /home/User2```?

#
#
#
#
#
##### Solution:
* The directory itself (User1).
* The parent directory (the directory before it: home).
* The working directory would be home.
* The shell will change the directory to the current working directory so nothing will change.
* The shell will change the working directory to /home/User1/Videos.
* The shell will change the working directory to /home/User2 (This is the relative path)
* The shell will change the working directory to /home/User1 as you are logged in as User1, so nothing will change because the working directory is already /home/User1
* Error, there isn’t a directory called “User2” under the directory “User1”.
* The shell will change the working directory to /home/User2 (This is the absolute path)
