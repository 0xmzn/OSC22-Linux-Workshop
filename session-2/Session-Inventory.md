# Command Line

|Command|Description|
|---|---|
|`whoami`|To print the username|
|`date`|To print the system date and time|
|`echo`|To display a line of text|
|`echo $0`|To determine the current shell|
| `pwd` | Print Working Directory, tells you the directory your terminal is working in.|
|`history`| To see the history of the commands that you previously entered|
|`!!`|To run the previous command without typing it again|
|`clear`| To clear up your display|
|`exit` <br> `logout`|To exit from the shell|


# Shortcuts
|Command|Description|
|---|---|
|`ctrl-R`|start typing parts of the command you want it will show you matches and you can just navigate through them by hitting the ctrl-R key again. Once you found the command you want to use again, just hit the Enter key.|
|`tab`|If you start typing the beginning of a command, file, directory, etc and hit the Tab key, it will autocomplete|
|`Ctrl+L`|Clears the screen|

# Change Directory
|Command|Description|
|---|---|
| `cd .` | Current Directory. This is the directory you are currently in |
| `cd ..` | Parent directory. Takes you to the directory above your current|
| `cd ~  ` <br> ` cd ` |  Home directory. This directory defaults to your **home directory**. Such as /home/salma|
| `cd -` |  Previous directory. This will take you to the previous directory you were just at.|


# List directory contents
|Command|Description|
|---|---|
| `ls` | Lists the content of a directory(folder)|
| `ls /home/` | To list files in a specific directory|
|`ls .` | To list the directory itself|
|`ls ..` | To list the directory before it (parent directory).|
| `ls -a` |  Listing all the Hidden Files |
| `ls -l` | Listing all the Details along with Files|
|`ls -R`| recursively list directory contents|
|`ls -r`| reverse order while sorting|
|`ls -t`| sort by modification time, newest first|


# For Help
|Command|Description|
|---|---|
| `[COMMAND NAME] --help` <br> `help [COMMAND NAME]` <br> `info [COMMAND NAME]` |  To get information about a command |
| `man [COMMAND NAME]` | It will show you the manual of the command name|
| `whatis ls ` or ` man -f ls` | To quickly see what a command does|
| `man -k`  <br> `apropos ` | If you need to do a specific task but don’t know which command can do it|


# Working with Files

|Command|Description|
|---|---|
| `touch file` |  To create a file <br> Change timestamps on existing files and directories|
| `touch file1 file2` |  To create a two files |
|`file`|It will show you a description of the file’s contents |
| `cat <file names>` | Concatenate files and print on the standard output|


# Working with Directories
  
|Command|Description|
|---|---|
| `mkdir` | Create a directory|
| `mkdir -p Directory1/Directory2/Directory3`| To create subdirectories at the same time|

# Copy
  
|Command|Description|
|---|---|
| `cp <source file> <destination file>` | To copy files|
| `cp -r <source directory> <destination directory>` | this will recursively copy the files and directories within a directory.|
| `cp -i`| to prompt you before overwriting a file.|



# Move
  
|Command|Description|
|---|---|
|`mv` | To move (rename) files|
|`mv oldFile newFile`|To rename a file or directory|
|`mv file_1 file_2 /somedirectory`| To move more than one file|
|`mv -b directory1 directory2`| to mv a file to overwrite the previous one and also make a backup of that file and it will just rename the old version with a ~.|


# Remove
|Command|Description|
|---|---|
|`rm filename` | To remove file|
| `rm -i filename` | Delete a file but ask for confirm before.|
| `rm -f filename` | Delete by force and don't prompt the user.|
| `rm -d directory_name` | Delete an empty directory|
| `rm -r directory_name` |  Delete a non empty directory. |
|`rmdir directory_name` |  To remove a directory|



# Find
|Command|Description|
|---|---|
|`find /home fileName`|To search for files in a directory|
|`find /home -type d -name MyFolder`|To find a file by its type and name|

# Alias
|Command|Description|
|---|---|
|`alias lss='ls'`|To create an alias for a command. this command won't save your alias after reboot, so you'll need to add a permanent alias in: `~/.bashrc`|
|`unalias lss`|To remove an aliase|

# Links
|Command|Description|
|---|---|
| `ln` | Make links between files |
|`unlink` | To delete a link|


# SSH 
|Command|Description|
|---|---|
|`ssh user_name@host(IP/Domain_name)` | OpenSSH remote login client|

