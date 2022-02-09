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
