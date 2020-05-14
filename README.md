
# Table of Contents
1. [Linux](##Linux).
2. [Introduction](##Introduction).
3. [Linux Files Types](##Linux_Files_Types).
4. [Terminal](##Terminal)
5. [File Navigation System](##File_Navigation_System).

## Linux
- Simple user: ```$ prompt```.

- Root user/admin: ```# prompt```.

- Switch from simple user to root user: ```sudo -i```.

- Switch from root to simple user:  ```exit```.

## Introduction
- How many users are logged in: ```who```.

- Who is the current user: ```whoami```.

- Print the date: ```date```.

- Show calendar: ```cal```.

- Print working directory: ```pwd```.

- Print files and directory of the current directory: ```ls```.

- Manual help: ```man whoami```.

- Create a new directory: ```mkdir directoryname```.

- Create a new empty file: ```touch filename```.

- Remove a directory: ```rmdir directoryname```.

- Remove a file: ```rm filename```.

- Remove a directory and its content: ```rm -r directoryname```.

- Display list of available commands: ```help```.

- Clear terminal: ```clear```.

- Exit session: ```exit```.

- Display date: ```date```.

- Display time: ```time```.

- Print information: ```hello```.

- Increase the font size: ```Ctrl, shift and +``` .


## Linux Files Types
- Directory file.
- Normal file [binary, text].
- Device file : every device is represented as a file.

- Show type of file: ```file file.txt```.

- Linux read files based on their content and not based on their extensions.


## Terminal
- Open the terminal: ```ctrl+alt+t```.
- Close the terminal: ```ctral+d```.
- Show the file that represent the current terminal: ```ttl``` ---> ```/dev/pts/0```.
- Show files: ```ls -l``` ```-l```  means long listing.


## File Navigation System

- Display hidden files: ```ls -a```  ```-a``` means all.
- Home directory: ```\home\user1```, ```\home``` contains the home users directories.
- Go to the home directory: ``` cd ```.
- Go to the previous directory: ``` cd -```.
- ```/``` is the topmost root.

## Linux sub-directories

- bin directoery: it contains all binary executables related to our linux commands, ```which touch``` will print ```/user/bin/touch```.
- sbin directory: it means system bin, an it contains binary executables related to the super user. 
- etc directory: it contains system configuration informations required by the operationg system, for example the passwords of the users ```/etc/passwd```, groups info ```/etc/group``` and hosts info ```/etc/hosts```(ip addresses and dns names).
- tmp directory: ```tmp``` means temporary, if any file or directory is required temporary, it is created under the tmp folder in the current session. the content of the directory will be deleted automatically after the shutdown.
- dev directory: ```dev``` means device, all the device related files will be stored in this directory, using those files, we can communicate with the device, tty file for terminal related files, hd for harde drive file ...
- mnt directory, media directory(for mounting).
- opt directory: opt means optional, it contains all the 3rd part software installaion files.
- lib directory: lib means libraries, which are required by applications.
- var: var means variable data, variable data will be stored inside this directory, for example the log files. 
- usr: all users related software.
- home: every user has a separate folder to hold his specific data like images, documents and so one.
- root directory: home directory of the super user.
- proc: proc means process, for each process a unique id is allocated, and a separate directory will be created inside the proc folder.
- boot directory: it contains the required files to boot the linux system.

## ls command and its options

- List all files and directories of the directory dir1: ```ls dir1```.
- List all files and directories of the current directory: ```ls```.
- List content in reverse alphabetical order: ```ls -r```.
- List content in a long format(more details on the content): ```ls -l```.
- List content based on creation time: ```ls -t```.
- Possibilioty to combine all the above options: ```ls -ltr```.
- List also the hidden files: ```ls -a```.
- List contents by type: ```ls -F``` (/, *, @).
- List contents recursively: ```ls -R```.
- List contents with total size(1 block = 1024kb): ```ls -s```.
- List contents of the top 10 entries: ```ls -l /dir | head```.
- List contents of the top 5 entries: ```ls -l /dir | head -5```.
- List contents of the bottom 10 entries: ```ls -l /dir | tail```.
- List contents page by page: ```ls -l /dir | more``` or ```ls -l /dir | less```, less is more powerful(forward and backword direction).

## Different linux commands:

- Redirect the documentation content of the ls command to some output file:  ```man ls > newfile.txt```.

