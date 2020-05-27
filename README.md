
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

## Creation of directories

- To create a directory in the same pwd: ```mkdir directoryName```.
- To create multiple directories in the same pwd: ```mkdir dir1 dir2 dir3```.
- To create multiple directories from the same pwd: ```mkdir -p dir1/dir2/dir3```. ```dir1, dir2``` will be created only if they don't exist already.
- To create multiple directories ```mkdir -p dir1/dir2{dir3-1,dir3-2,dir3-3}/dir{1..31}```, every dir3-x will contains 31 directories.
- Show directory content as a tree datastructure:  ```tree```.

## Removing directories, rm and rmdir commands

- To remove directories: ```rmdir dir1 dir2``` (rmdir removes only directories, no file will be deleted, and it will works only if the directories are empty).
- To remove directories: ```rm -r dir1```, or ```rm -R dir1```. For files no need to the ```-r``` option, ```-r``` for recursive operations.
- To get confirmation before deleting the contents: ```rm -r -i dir1```.
- Force removal ```-f```: ```rm -rf dir1```.
- Verbose option ```-v```: ```rm -rv dir1```, to print the flow of the deletion process.

## Copying, moving and renaiming files and directories

- To copy file content from one file to another: ```cp a.txt b.txt```, if ```b.txt``` doesn't exist, a new file will be created, if it already exists, the file will be overwritten. ```cp a.txt home/anotherDirectory/c.txt``` to copy content to another destination.
- To copy files to directories: ```cp a.txt b.txt c.txt home/anotherDirectory/d.txt```, to copy all files ```cp dir1/* dir2```.
- To copy total diretory: ```cp -r dir1 dir2```, the content of ```dir1``` will be copied to ```dir2```.
- Renaiming a file: ```mv a.txt b.txt```, to rename a directory ```mv dir1 dir2```, if ```dir2``` already exists, ```dir1``` wil be moved inside ```dir2```.
- Moving files from one directory to another: ```mv dir1/* dir2```, ```mv a.txt b.txt dir2```.


## Creation of files using cat, touch, gedit and vi

- Using the cat command: ```cat > a.txt```, a possibility to write content on the a.txt file, ctrl+c to save and exit, if the file is already available, the data will be overwritten, to perform append operation, ```cat >> a.txt```.
- Using the touch command: ```touch b.txt```, a new empty file will be created, if the file is already available, the data will be not be overwritten, only the last date of modification will be modified.
- Using the gedit command: ```gedit c.txt```, ctr+s to save, ctrl+q to quit the graphical editor.
- Using vi editor: ```gedit d.txt```, press i to enter the insert mode, press esc key, :wq to save and quit the editor. vim is an advanced version of the vi editor.


## View files contents using cat, tac, rev, head and tail
- View content using cat command:  ```cat < a.txt```, where ```<``` symbol is optional. ```-n``` option to display line numbers, ```-n``` to skip blank lines numbering. ```cat a.txt b.txt``` will print the content of the two passed files.
- Create and add content to a file: ```cat > a.txt```, ```added content```, ```ctrl+d``` to exit the editing section.```>>``` for append operation.
- Copy content from one file to another using cat command: ```cat a.txt >> b.txt```, using ```>``` will overwrite the content of the b.txt file. 
- Copy content from many files to one file: ```cat a.txt b.txt >> c.txt```.
- View content of a file in reversed order: ```tac a.txt```, the order here is the order of the file lines.
- View content of a file in a horizental reversed order: ```rev a.txt```, if the content of ```a.txt``` is ```content```, the result of the previous command will be ```tnetnoc```.
- ```cat``` command is suitable for small ```files```, if the files are huge, ```head``` and ```tail```, ```more``` and ```less``` are the most recommended commands.
- To view specified lines from the top of a file: ```head a.txt```, first 10 lines ```head -n 10 a.txt```, abbreviation: ```head -10 a.txt```.
- To view specified lines except some specified lines: ```head -n -5 a.txt``` will diplay all lines except the last 5 lines.
- To view specified number of character: ```head -c 5 a.txt``` will show the first 5 characters.
- To view specified lines from the bottom of a file: ```tail a.txt``` last 10 lines, last 5 lines ```tail -n 5 a.txt```, abbreviation: ```tail -5 a.txt```, ```tail -c 100 a.txt``` will print the last ```100``` characters.
- To view content from line 3 to line 7 using piping: ```head -7 a.txt | tail -5```.

## Different linux commands:

- Redirect the documentation content of the ls command to some output file:  ```man ls > newfile.txt```.

