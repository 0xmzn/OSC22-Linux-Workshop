## git

 
  |Installation|Configurations| Git Help |
  | --- | --- |--- |
  |`sudo apt update` <br> `sudo apt install git` | `git config --global user.name "John Doe" `<br> `git config --global user.email johndoe@example.com` <br> `git config --global core.editor nano` <br> `git config --global merge.tool meld` | `git help <command>` <br> `man git <command>` <br> `git <command> -h` |
  
  
  | Command|Description |
  | --- | --- |
  | `git init` | Initialises a Git repository in that directory|
  |`git clone URL`| Makes a clone of the repository at the specified URL|
  |`git rm <file name\| wild card>`| Remove files or directories|
  |`git mv <file directory \| file name \| wild card> <new directory \| new file name>`| Move or rename files or directories|
  |` git status` <br> `git status -s` # Summarized | Checking status of your files|
  |`$ git add <files\|WildCards> `|Stage your files after adding not before |
  | `git diff` |Differences between committed  and modified/untracked |
  |`git diff --staged` |Differences between committed and modified/tracked/staged|
  | `git commit`<br> `git commit -m "short Message" `|Committing Changes|
  |`git commit -am “Your Message”` |Stage all untracked files and commit all files in staged area||
  |`git log` |Commit History| 
  |`git reset <files>`| Undo add (Unstaging a Staged File)|
  |` git commit --amend`| Used to change your latest log message and to make modifications to the most recent commit|
  |`git revert <commit> `|  Merge a previous commit with current commit into a new commit|
  |`git checkout <commit>` | Move the Head to the specified commit and change the working set to match the commit|
  |`git checkout <file> `|Change the file to match the commited version of the file "the Head commit"|
  |`git reset --soft <commit>` | The Head and the branch pointer will move to the specified commit|
  |`git reset <commit> `| The Head and the branch pointer will move to the specified commit and will clear the index|
  |`git reset --hard <commit> `| The Head and the branch pointer will move to the specified commit and will clear the index and reset the working directory to match it|
  |`git remote` <br> `git remote -v`| Showing Your Remotes|
  |`git remote add <Name> <URL>`|Add Remotes|
  |`git fetch <remote>` <br> `git pull <remote> <branch>`|Fetching and Pulling Repositories|
  |`git push <remote> <branch>`|Pushing into Repositories|
  |`git branch` <br> `git branch -a`|List branches|
  |`git branch testing`| Create new branch|
  |`git Checkout <branch name>`|Switching Branch|
  |`git branch -d <branches>`|Delete Branches|
  |`git  config --global alias.<name> ‘commands’`|git aliases|
  
