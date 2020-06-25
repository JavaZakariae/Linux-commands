- [Linux](#linux)
- [Introduction](#introduction)
- [Linux Files Types](#linux-files-types)
- [Terminal](#terminal)
- [File Navigation System](#file-navigation-system)
- [Linux sub directories](#linux-sub-directories)
- [ls command and its options](#ls-command-and-its-options)
- [Creation of directories](#creation-of-directories)
- [Removing directories rm and rmdir commands](#removing-directories-rm-and-rmdir-commands)
- [Copying moving and renaiming files and directories](#copying-moving-and-renaiming-files-and-directories)
- [Creation of files using cat touch gedit and vi](#creation-of-files-using-cat-touch-gedit-and-vi)
- [View files contents using cat tac rev head and tail](#view-files-contents-using-cat-tac-rev-head-and-tail)
- [View files content using less and more](#view-files-content-using-less-and-more)
- [Creation of hidden files and directories](#creation-of-hidden-files-and-directories)
- [Copying moving and renaiming files and directories using cp and mv commands (2)](#copying-moving-and-renaiming-files-and-directories-using-cp-and-mv-commands-2)
- [Comparing content of files (diff sdiff...)](#comparing-content-of-files-diff-sdiff)
- [Soft and hard link](#soft-and-hard-link)
- [Sort commands](#sort-commands)
- [Uniq commands](#uniq-commands)
- [Input and Output](#input-and-output)
- [Redirecting stdInput stdOutput and  stdError](#redirecting-stdinput-stdoutput-and-stderror)
- [Piping](#piping)
- [Execute multiple command](#execute-multiple-command)
- [Commands aliasing](#commands-aliasing)
- [Regular expressions](#regular-expressions)
- [locate](#locate)
- [find command](#find-command)
- [Compression and uncompression of files (episode 33)](#compression-and-uncompression-of-files-episode-33)
    - [Creation of archive files](#creation-of-archive-files)
    - [Apply compression algorithm on archive files (gzip bzip2)](#apply-compression-algorithm-on-archive-files-gzip-bzip2)
- [grep command](#grep-command)
- [Regular expressions patterns](#regular-expressions-patterns)
    - [Character Patterns](#character-patterns)
    - [Word Patterns](#word-patterns)
    - [Line Patterns](#line-patterns)
    - [Additional Patterns available only when using the egrep command](#additional-patterns-available-only-when-using-the-egrep-command)
- [The cut command](#the-cut-command)
- [Stackoverflow awnsers](#stackoverflow-awnsers)





## Linux
- Simple user: `$ prompt`
- Root user/admin: `# prompt`
- Switch from simple user to root user: `sudo -i`
- Switch from root to simple user:  `exit`

## Introduction
- How many users are logged in: `who`
- Who is the current user: `whoami`
- Print the date: `date`
- Show calendar: `cal`
- Print working directory: `pwd`
- Print files and directory of the current directory: `ls`
- Manual help: `man whoami`
- Create a new directory: `mkdir directoryname`
- Create a new empty file: `touch filename`
- Remove a directory: `rmdir directoryname`
- Remove a file: `rm filename`
- Remove a directory and its content: `rm -r directoryname`
- Display list of available commands: `help`
- Clear terminal: `clear`, `ctrl+l`
- Exit session: ``exit`
- Display date: `date`
- Display time: `time`
- Print information: `hello`
- Increase the font size: `Ctrl, shift and +`
- Print 5 random numbers between 1 and 100: `shuf -i 1-100 -n 5`
- Creating file using the `shuf` command: `touch dir$(shuf -i 1-10 -n 1)/sunny.txt `

## Linux Files Types
- Directory file.
- Normal file [binary, text].
- Device file : every device is represented as a file.
- Show type of file: ```file file.txt```
- Linux read files based on their content and not based on their extensions.


## Terminal
- Open the terminal: ```ctrl+alt+t```
- Close the terminal: ```ctral+d```
- Show the file that represent the current terminal: ```ttl``` ---> ```/dev/pts/0```
- Show files: ```ls -l``` ```-l```  means long listing.


## File Navigation System

- Display hidden files: ```ls -a```  ```-a``` means all.
- Home directory: ```/home/user1```, ```/home``` contains the home users directories.
- Go directly to the home directory: ```cd ``` or ```cd ~ ```
- Go to the previous directory: ``` cd -```
- ```/``` is the topmost root.

## Linux sub directories

- bin directoery: it contains all binary executables related to our linux commands, ```which touch``` will print ```/user/bin/touch```
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

- List all files and directories of the directory dir1: ```ls dir1```
- List all files and directories of the current directory: ```ls```
- List content in reverse alphabetical order: ```ls -r```
- List content in a long format(more details on the content): ```ls -l```
- List content based on creation time: ```ls -t```.
- Possibilioty to combine all the above options: ```ls -ltr```
- List also the hidden files: ```ls -a```
- List contents by type: ```ls -F``` (/, *, @)
- List contents recursively: ```ls -R```
- List contents with total size(1 block = 1024kb): ```ls -s```
- List contents of the top 10 entries: ```ls -l /dir | head```
- List contents of the top 5 entries: ```ls -l /dir | head -5```
- List contents of the bottom 10 entries: ```ls -l /dir | tail```
- List contents page by page: ```ls -l /dir | more``` or ```ls -l /dir | less```, less is more powerful(forward and backword direction).

## Creation of directories

- To create a directory in the same pwd: ```mkdir directoryName```
- To create multiple directories in the same pwd: ```mkdir dir1 dir2 dir3```
- To create multiple directories from the same pwd: ```mkdir -p dir1/dir2/dir3```. ```dir1, dir2``` will be created only if they don't exist already.
- To create multiple directories ```mkdir -p dir1/dir2{dir3-1,dir3-2,dir3-3}/dir{1..31}```, every dir3-x will contains 31 directories.
- Show directory content as a tree datastructure:  ```tree```

## Removing directories rm and rmdir commands
- To remove directories: ```rmdir dir1 dir2``` (rmdir removes only directories, no file will be deleted, and it will works only if the directories are empty).
- To remove directories: ```rm -r dir1```, or ```rm -R dir1```. For files no need to the ```-r``` option, ```-r``` for recursive operations.
- To get confirmation before deleting the contents: ```rm -r -i dir1```
- Force removal ```-f```: ```rm -rf dir1```
- Verbose option ```-v```: ```rm -rv dir1```, to print the flow of the deletion process.

## Copying moving and renaiming files and directories
- To copy file content from one file to another: ```cp a.txt b.txt```, if ```b.txt``` doesn't exist, a new file will be created, if it already exists, the file will be overwritten. ```cp a.txt home/anotherDirectory/c.txt``` to copy content to another destination.
- To copy files to directories: ```cp a.txt b.txt c.txt home/anotherDirectory/d.txt```, to copy all files ```cp dir1/* dir2```
- To copy total diretory: ```cp -r dir1 dir2```, the content of ```dir1``` will be copied to ```dir2```
- Renaiming a file: ```mv a.txt b.txt```, to rename a directory ```mv dir1 dir2```, if ```dir2``` already exists, ```dir1``` wil be moved inside ```dir2```
- Moving files from one directory to another: ```mv dir1/* dir2```, ```mv a.txt b.txt dir2```

## Creation of files using cat touch gedit and vi
- Using the cat command: ```cat > a.txt```, a possibility to write content on the a.txt file, ctrl+c to save and exit, if the file is already available, the data will be overwritten, to perform append operation, ```cat >> a.txt```
- Using the touch command: ```touch b.txt```, a new empty file will be created, if the file is already available, the data will be not be overwritten, only the last date of modification will be modified.
- Using the gedit command: ```gedit c.txt```, ctr+s to save, ctrl+q to quit the graphical editor.
- Using vi editor: ```gedit d.txt```, press i to enter the insert mode, press esc key, :wq to save and quit the editor. vim is an advanced version of the vi editor.


## View files contents using cat tac rev head and tail
- View content using cat command:  ```cat < a.txt```, where ```<``` symbol is optional. ```-n``` option to display line numbers, ```-n``` to skip blank lines numbering. ```cat a.txt b.txt``` will print the content of the two passed files.
- Create and add content to a file: ```cat > a.txt```, ```added content```, ```ctrl+d``` to exit the editing section.```>>``` for append operation.
- Copy content from one file to another using cat command: ```cat a.txt >> b.txt```, using ```>``` will overwrite the content of the b.txt file. 
- Copy content from many files to one file: ```cat a.txt b.txt >> c.txt```
- View content of a file in reversed order: ```tac a.txt```, the order here is the order of the file lines.
- View content of a file in a horizental reversed order: ```rev a.txt```, if the content of ```a.txt``` is ```content```, the result of the previous command will be ```tnetnoc```
- ```cat``` command is suitable for small ```files```, if the files are huge, ```head``` and ```tail```, ```more``` and ```less``` are the most recommended commands.
- To view specified lines from the top of a file: ```head a.txt```, first 10 lines ```head -n 10 a.txt```, abbreviation: ```head -10 a.txt```
- To view specified lines except some specified lines: ```head -n -5 a.txt``` will diplay all lines except the last 5 lines.
- To view specified number of character: ```head -c 5 a.txt``` will show the first 5 characters.
- To view specified lines from the bottom of a file: ```tail a.txt``` last 10 lines, last 5 lines ```tail -n 5 a.txt```, abbreviation: ```tail -5 a.txt```, ```tail -c 100 a.txt``` will print the last ```100``` characters.
- To view content from line 3 to line 7 using piping: ```head -7 a.txt | tail -5```

## View files content using less and more
- To view file content page per page:  ```more a.txt```, press ```enter``` to diplay next line, press ```space bar``` to diplay the next page, press ```q``` to exit, ```more -d a.txt``` to diplay more info about the file. By using more command, we can view file content page per page only in forward direction.
- To view file content page per page either in forward direction or backward direction: ```less a.txt```, press ```d``` to diplay the next page (d means down),  press ```b``` to diplay the previous page (b means backward).

## Creation of hidden files and directories
- If any file name starts with ```.```, such file is a hidden file.
- Create hiiden files: the name of the file should begin by a ```.```, example: ```touch .a.txt```, ```cat > .b.dat```
- Display hiden files: ```ls -a```
- Create hiiden directories: ```mkdir .dir1```
- Conversion of Normal/hidden files: using renaiming operation, ```mv .a.txt a.txt```

## Copying moving and renaiming files and directories using cp and mv commands (2)
- ```cp a.txt b.txt```, if b.txt exists, its content will be ovewritten directly, to get confirmation message, ```cp -i a.txt b.txt```
- Copy multiple files content to one destination file: ```cat a.txt b.txt > c.txt```
- Moving and renaming files: ```mv oldname.txt newname.txt```
- Moving and renaming directories: ```mv olddirname newdirname```, if olddirname exists already, then olddirname will be moved to newdirname, otherwise the renaming operation will take place.
- Moving selected files to a directory: ```mv a.txt b.txt dir1```
- Moving all files of one directory to another directory: ```mv dir1/* dir2```
- Moving using absolute path:  ```mv ~/dir1/* ~/dir2```, ```~/dir2``` equivalent to ```/home/userName/dir2```


## Comparing content of files (diff sdiff...)
- ```cmp``` command: comparing files byte by byte, ```cmp file1.txt file2.txt```, if the files content are the same, no output, otherwise information about the first found difference, byte number and line number will be shown.
Example:  ```echo "hello" >> file1.txt```, ```echo "hello2" >> file2.txt```, ```cmp file1.txt file2.txt```, output will be ```file1.txt file2.txt differ: char 6, line 1```

- ```diff``` command: it will show all differences, ```diff file1.txt file2.txt```
- ```sdiff``` command: all differences in a parallel comparison.
- ```vimdiff``` command: advanced tool to show the differences, it will highlight all differnces in a vim editor, ```sudo apt-get install vim``` to install the tool, two windows will be shown, ```ctrl+w+w``` to go to the other window, ```:q``` to close current window, ```:qa``` to close all windows, ```:qai``` close and ignore all changes. 

##  Soft and hard link
- In Windows, we have only soft link files (shortcut|raccourci), in linux we have also hard link files.
- Hard link file is just another name of the same file. We can create hard link files using the following command ```ln sourcefile.txt hardlinkfile.txt```
- If we deleted the source file, the hard link file wil still exists. If we modify the content of the (sourcefile|link hard file), the update will be reflected also in the (sourcefile|link hard file).
- Soft link file is just a shortcut of the original file (same as windows). If we delete the original file, the soft link file will be broken. We can create soft link files using the following command ```ln -s sourcefile.txt softlinkfile.txt```
- Change made in the original file will also be reflected to the Soft link file.
- For directories, it is not possible to create hard link. 

## Sort commands 
- Sort command, to sort files content line by line in an alphabetical order: ```sort a.txt``` will only print the sorted order. ```sort a.txt > b.txt``` will redirect the sorted order output to the new file. ```sort a.txt > temp.txt``` and ```mv temp.txt > a.txt``` will make change on the same source file.
- Sort in a reverse alphabetical order: ```sort -r a.txt```
- The spaces in the beginnning of a line are ignored, blank line came first when sorting, Upper case before lowercase, If the file contains numbers, the numbers will come before letters.
- If we want only unique lines, no duplicate, we should use ```-u``` option, ```sort -u a.txt```
- If we want to sort based on numerical values: ```sort -n a.txt```, ```sort -nr a.txt```
- Sort based on the column line number:  ``` ls etc/ -l | head -7 | sort -rk 5``` will show the info of the top 7 files in etc folder and will sort them recursivly based on the fifth column (length of file).
- Sort based on the column lines in a file composed by lines in the following format ```token1:token2:token3```, ```:``` is called a separator. To sort such file: ```sort -k 3 -t ":" a.txt```

## Uniq commands
- Find unique content ```sort -u a.txt```, but uniq command is more powerful, ```uniq a.txt``` works only on sorted files, ```sort a.txt | uniq```.
- With uniq command, we can use multiple options:
  - ```-d```: to disply ony duplicate lines.
  - ```-c```: to disply numbers of occurences of each line.
  - ```-i```: to ignore case while comparing.
  - ```-u```: to disply ony unique lines.
  
## Input and Output
- command take some input and produces some output:  
  - Input in two forms: stdin or command line argument, stdin example: `echo "hello" >> file.txt`,  command line argument example:  `touch file.txt`
  - Output in two forms: stdout or stderror, stderror in cas when the terminal print arrors.
- Standard Input, Standard Output and Standard Error are data stream and can be redirected from one place to another place. Hence, piping and redirection are possible on those data streams.
    - stdIn associated with the number 0, by defualt it is connected with the keyboard.
    - stdOutput associated with the number 1, connected with the terminal.
    - stdError associated with the number 2, connected with the terminal.

## Redirecting stdInput stdOutput and  stdError
- Redirecting stdOutput: We can perform redirection using `>` and `>>`, `cat 1> output.txt`
- Redirecting standard error: Instead of terminal we can redirect messages from terminal to another place, a file as an example. `cal jkbjkcabjkac 2> log.txt`, 2 stands for stdError.
- Redirecting standard input: we can use the `<` symbol to perform input redirection, `cat 0< a.txt`, 0 is optional.
- Examples:
    - `cat 0<a.txt 1>copy.txt 2>error.txt`
    - `cat <a.txt >copy.txt 2>error.txt`
    - `cat <a.txt &>copy.txt`, means either output or error direction to the copy.txt file.
    - Redirect the documentation content of the ls command to some output file:  ```man ls > newfile.txt```.

## Piping  
- `ls -l /etc | more`, the output of the first command will be the input of the second command.
- `ls -l /etc > somefile.txt | more`, no piping beacause the redirection symbol breaks the piping.
- `tee` commmand: if we want to save the output of intermedite command and want to pass that output as input to next command, `ls -l /etc tee somefile.txt | more`
- `rm` command can't take data stream as input, but can only get arguments from the command line terminal, for that purpose, the command `xargs` can be used to converts data stream to arguments. Example: `cat /etc | xargs rm`
- pipe symbol `|` can be used to link two commands, `>` is useful when redirecting the output to another place.

## Execute multiple command
- `ls -l /etc | more`: the preceding commands are dependent commands, to run multiple independent commands in one line, we can use the `;` symbol or by using `&&`.
- By using `;`: e.g. `cmd1;cmd2;cmd3`, if `cmd2` fails, `cmd3` will be executed.
- By using `&&`: e.g. `cmd1&&cmd2&&cmd3`, if `cmd2` fails, `cmd3` will not be executed.

## Commands aliasing
- Aliases are nicknames given to a given command.
- Syntax: `alias nickname="original command name"`, example: `alias cls=clear`. Spaces are not allowed before and after the `=` symbol.
- To list the existed aliases: `alias`, to delete a given alias: `unalias cls`, to delete all aliases `unalias -a`
- To know the original name of an alias: `type cls`
- Aliases are temporary unless we persist them permanently: 
    - Editing the .bashrc file, It could be found inside the user home directory.
    - Create our new aliasing file, the name of the file should be .bash_aliasses and should be located in the user home directory.
    
## Regular expressions
- If we want to represent a collection of strings according to a particular pattern, then we should go for 
Regular expressions.
- Some reg expressions rules:
    - \* ----> 0 or more character.
    - ?  ----> 1 character.
    - [abc]  ----> a or b or c.
    - [!abc]  ----> only one character but not a or b or c.
    - [a-z]  ----> any lower case character from a to z.
    - [A-Z]  ----> any upper case character from A to Z.
    - [a-zA-Z] ----> any alphabet from a to z or from A to Z.
    - [0-9]  ----> any digit from 0 to 9.
    - [a-zA-Z0-9]  ----> any of the two above.
    - [!a-zA-Z0-9] ---->  negation of the above.
- Examples: `ls *`, `ls *.*`, `ls *.txt`, `ls a*`, `ls a*t.*`, `ls a?.*`.
    - `ls [abc]*`: aaaaaa, bbbb, ....
    - `ls [!abc]*`: should not start with a, b  or c.

## locate
- We can use locate to locate files and directories in our system.
- `locate file.txt`, `locate *.txt`: to locate the given entries, locate command look in a database to locate the given entries, the database is updated only one time a day, so to update the database we should use the following command: `sudo updatedb`
- `locate -S`: to get the statistics of the database, `locate -i FilE.txt` to ignore case sensivity. `locate --limit 5 a.txt` to limit the search to 5 entries.
- `locate --existing b.jpeg`, or with `-e` option: check if the gievn file exist or not.
- Advantage of using a database is related to performance.

## find command
- It provides more search option comparing to the locate command. contrary to the locate command, the find command will search directly in the file system.
- We can search only files, only directories, search by name, search by size...
- `find`: by default, it will look for all files and directories from the current directory and below in the linux file system.
- `find /home`: look for all files and directories from the current directory and below.
- `find -maxdepth 2`: will limit the search only in the 2 levels.
- By default the find command will also look for hidden files.
- `find -type f`: will limit the search to the files.
- `find -type d`: will limit the search to the directories.
- `find . -type f -name d?.*`: look for files inside the current directory and below with the given name that match given regular expression, `-iname` option to ignore case.
- `find . -type f -size +200k`: look for files that have size greater than 200 kbytes, `-size -200k` for less than, `-size 100k` for equality size. 

## Compression and uncompression of files (episode 33)
#### Creation of archive files
- `tar` command: tape archive, to group multiple files and directories into a single archive, `tar -cvf demo.tar file1 file2 dir1`, `-c` create, `-v` verbose,`-f` named file.
- `tar -tvf demo.tar`: print table of content of the tar file.
- `tar -xvf demo.tar`: extract the given tar file.

#### Apply compression algorithm on archive files (gzip bzip2)
- `gzip demo.tar`: To compress a given file, `demo.tar.gz` will be created.
- `gunzip demo.tar.gz`: To decompress a given compressed file. 
- `bzip2` and `bunzip2` as a second alternative to compress and decompress files.
- Archiving and compressing (`gzip`) in one command: using the `-z` option, `tar -czvf demo.tar file1 file2 dir1`
- Decompressing (`gunzip`) and extracting the archive in one command: using the `-x` option, `tar -xvzf demo.tar.gz`

## grep command
- Globally search a regular expression and print it, global regular expression print, global regular expression parser.
- `locate` and `find` help to find required files and directories, `grep` command help to find content within the file.
- Syntax: `grep <pattern> filname`, and it will print all matched lines.
- `grep someword filname1.txt filname2.txt`: look for the pattern in the given files.
- `grep someword *`: look for the pattern in the current directory and not in the sub-directories, to ignore case we should use the `-i` option, `--color` to display the result in a colored form. 
- `grep someword -c *`: to print how much time the pattern is found.
- `grep someword -n *`: to print the lines number where the pattern is found. 
- `grep someword -l *`: to print only the file names where the pattern is found. 
- `grep someword -v *`: to print the lines where the pattern is not found. 
- `grep -w 'word1' *`: will search for the exact word, `aword100` will not be valid, only `word1` will be a correct awnser.
- Display before, after and surrounding lines including search result: `-A` means After, `-B` means Before, `-C` means Before and After. `grep 'word1' -B3 *`
- Search multiple contents in a file: `egrep '(word1|word2)' *`, `grep` can understand only some patterns; for this reason we use `egrep`
- `grep -o 'word1' *`: will print only matched pattern.
- `egrep -R '(word1|word2)' *`: will execute recursivly, it means also checking the sub-directories.

## Regular expressions patterns
#### Character Patterns
- `grep  'd*' *`: display all lines which contains d followed by any number of characters.
- `grep  'c[aei]b' *`: all lines wich contains `cab`, `ceb` or `cib`
- `grep  'b..x' *`: `.` means any character, it will search for all 4 letter words beginning with b and ending by x.  

#### Word Patterns
- `grep 'linux' demo.txt`: display all lines which contains the word `linux`, for example linuxworld will be valid.
- `grep '\<linux\>' demo.txt`: display all lines which contains exactly `linux`, so linuxworld is invalid.
- `grep '\<linux' demo.txt`: display all lines which starts with `linux`.
- `grep 'linux\>' demo.txt`: display all lines which ends with `linux`.
  
#### Line Patterns
- `^`: line starts with, `grep '^d' demo.txt` will print all lines that start with `d`.
- `$`: line ends with.
- `\<the\>`: lines that start exactly with the word `the`
- `^[aeiu]`: lines that start with `a`, `e`, `i` or `u`
- `^[^aeiu]`: lines that do not start with `a`, `e`, `i` or `u`
- `^....$`: lines that contains only 4 charachters.
- `^\.`: lines that starts with the `.` symbol.
- `^$`: blank lines, to remove blank lines, `grep '^$' file.txt > temp.txt`, `mv temp.txt file.txt`.

#### Additional Patterns available only when using the egrep command
- `|`: it matches any of the passed string, `egrep '(linux|java|docker)' *`.
- `{m}`: it matches exactly m occurences of the preceiding character.  `egrep '[0-9]{10}' *` will match every 10-digit mobile numbers.
- `{m, n}`: it matches minimum m occurences and maximum occurences of the preceiding character.  `egrep '[0-9]{8, 10}' *` will match every 8-digit, 9-digit and 10-digit mobile numbers. `{m, }` means no restriction for the maximum occurences. 

## The cut command
- we use the cut command to extract specific data from files, the file can be either normal or tabular.
- `cut -c 9 emp.dat`: print the `9th` character in each line.
- `cut -c 3-5 emp.dat`: print the `3th`, `4th`, `5th` character in each line, `-c 3-` the 3th to the last character, `-c -3` will print the `3` first characters by each line.
- `cut -c 3-5 7-9 emp.dat`: will display the `3th`, `4th`, `5th` characters and also the `7th`, `8th` and `9th`
- Display content based on delimiter: `name|username|password`, to print the second column we can use `cut -d "|" -f 3 tabularfile`, `d` option for delimiter and `f` for field, `-f 1-3` to get the columns 1, 2 and 3, `-f -2` to get up to the second column, `-f 1, 3` to get only the first and third column, to get all columns execpt the third column, we can use  `cut -d "|" --complement -f 3 tabularfile`


## Stackoverflow awnsers
- [What is the difference between ps and top command?](https://unix.stackexchange.com/questions/62176/what-is-the-difference-between-ps-and-top-command)