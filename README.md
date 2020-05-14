
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
