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

