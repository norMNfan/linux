# Linux Commands

[Basic Commands](#basic-commands)

[Navigation Commands](#navigation-commands)

[Bash Scripting Cheatsheet](#https://devhints.io/bash)

[Source](#https://dev.to/awwsmm/101-bash-commands-and-tips-for-beginners-to-experts-30je#basic-bash-scripting)

## Intro

## Basic Commands

- ```date``` : Wed Oct 30 16:10:54 JST 2019
- ```cal``` : Prints current month's calendar
- ```man``` : Get man page info about a command

## Navigation Commands

- ```pwd``` : Prints current directory
- ```cd``` : Changes the current directory
- ```ls``` : Prints contents of current directory
  - ```ls -l``` : ls with long information
- ```tree``` : Prints tree of directory structure
  - ```tree -L 2``` : Restrict number of levels

## File Commands

- ```head``` : Outputs the first few lines of a file. -n specifies number of lines to show.
  - ```head -n 3 c```
- ```tail``` : Outputs the last few lines of a file.
  - ```tail -n +4 c```
- ```cat``` : Print contents of file   
  - Name comes from concatenate and print
  - ```cat a b```
- ```less``` : Tool for quickly viewing a file
- ```nano``` : Opens up editor

## Creating and Deleting Files and Directories

- ```touch``` : Create an empty file
- ```rm file``` : Deletes the file
- ```mkdir dir``` : Makes a new directory
- ```rmdir dir``` : Removes directory if it is empty, complains otherwise
  - ```rmdir -r dir``` : Remove non-empty directory
- ```cp source target``` : Copy source to target
- ```mv source target``` : Move source to target
- ```ln``` : Creates a hard link to a file
  - ```ln -s a``` : Creates a soft link to a file
- ```diff``` : Lists differences between a and b
  - ```diff a b```

## Disk Commands

- ```ps``` : Report a snapshot of current processes
- ```df``` : Tells you how much of your disk is free
  - ```df -h``` : human-readable
- ```du``` : Shows file space usage for a particular directory and its subdirectories
- ```kill -9 pid``` : Kill process with pid
- ```top``` : Displays all currently-running processes and their owners, memory usage, and more

## Finding Things

- ```whereis``` : Searches for "possibly useful" files related to a particular command. Returns the location of the binary source and the man page for that
- ```which``` : Will only return the location of the binary
- ```whatis``` : Prints out the one-line description of a command from its man page
- ```locate``` : Finds a file anywhere on the system
  - Refers to a semi-regularly-updated cached list of files
- ```find``` : Find iterates through the file system to find the file you're looking for
  - ```find . -name name```
  - ```find``` has more options than ```locate```
- ```grep, egrep, fgrep pattern``` : Print lines that match pattern

## Downloading Things

- ```ping``` : Attempts to open a line of communication with a network host. Mainly used to check whether or not your Internet connection is down
- ```wget ``` : Download a file from the Internet
  - ```wget link```
- ```curl``` : Can be used just like ```wget```
  - Can also send data. ```wget``` cannot send data
- ```apt``` : Used to install, upgrade, or delete software on your machine
  - ```apt install package``` : Install a package
  - ```apt search package``` : Search for a package
- ```gunzip``` : Unzip a ```.tar.gz``` file
  - ```gunzip file.tar.gx```
  - ```tar -xf file.tar.gz```
- ```gzip file.tar.gz``` : Zip a file
  - ```tar -zcf file.tar.gz``` : Zip a file ```(-c)``` create

## Redirecting Input and Output

- ```|``` : The pipe operator redirects the output of the first command to the input of the second command
  - ```echo "example document"``` | wc
- ```>``` : Redirects output from stdout to a particulat location
  - ```echo "test" > file```
- ```printf``` : Improved ```echo```, allowing formatting and escape sequences
- ```<``` : Gets input from a particular location, rather than stdin
- ```&0``` : Alias for stdin
- ```&1``` : Alias for stdout
- ```&2``` : Alias for stderr

## Misc

- ```passwd```: Change your password
- ```logout``` : Exits shell you've logged into
- ```exit``` : Exits any kind of shell
- ```clear``` : Move current terminal line to the top of the screen
- ```printenv``` : See all currently-defined env vars
- ```myvar=hello``` : Set env variables
- ```export myvar="another one"``` : Set env variables
- ```unset myvar``` : Unset env variable
- ```echo $myvar``` : Print specific env var to terminal
- ```alias``` : Replace long commands with short ones
  - ```alias lc="ls -l -a -h -t"```
  - ```lc```
- ```unalias``` : Remove alias
  - ```unalias lc```

## Repl

- ```mongo```
- ```jshell```
- ```python```

## Bash Scripting

Usually end in ```.sh```, allows you to automate complicated processes, packaging them into reusable functions. A ```bash``` script can contain any number of normal shell commands.
- *echo "ls && touch file && ls" > ex.sh*
- *source ex.sh* : Execute shell script
  - *sh ex.sh*
  - *./ex.sh*

The ```~/.bashrc``` file contains your configuration settings

## Other

- Ctrl + D : End session
- Ctrl + C : Kill foreground process
- *;* : Run one command after another
  - The second command will run even if the first one fails
- *&&* : Run one command after another
  - If the first one fails, the second will not execute
- *&* : Run a process in the background
- *\* : Long lines of code can be split
- *-h, --help* : Use after any command to get help
- *-v, --version* : Display version of command

# Advanced

- ```whoami``` : Check what your username is
- ```su``` : Become another user temporarily
- ```exit``` : Switch back
- ```!!``` : Retains the previous command
  - ```apt install ruby``` : Fails because you are not sudo user
  - ```sudo !!```

## File permissions

- ```chmod```
- ```chown```

## Examples

ps -ef | grep mongo
