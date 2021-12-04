# Learning the bash shell

- Print the version of the bash : `echo $BASH_VERSION`.
- Print the current running shell: `echo $SHELL`.
- `(~)`: the tilde notation is an abbreviation of the home directory.
- `cd -` : changes to whatever directory you were in before the current one. 

### Basic wildcards:
  - `?`: any single character.
  - `*`: any string of characters.
  - `[set]`: any character int set.
  - `[!set]`: any character not int set.
  - `[.,;]`: match . , or ;
  - `[-_]` : - or _
  - `[!0-9]`: match all non digits.
  - `[\!]`: match the exclamation symbol.

### I/O Redirection:
  -  `cat < file.txt` will print the content of the given file to the terminal.
  -  `sort < file.txt` will sort the lines in the given file and print the result to the terminal.
  -  `date > time.txt` will saves the current time in the given file.    
  -  Input and output redirectors can be combined, `cat < file1 > file2` will copy the content of file1 into file2, the content of file2 will be ovewritten.

### Pipelines
- It is possible to redirect the output of a given cmmand to the input of another command.
- Example: `cut -d: -f1 < /etc/passwd | sort` to get all users of the system in sorted order. 

### Background job
- To run a program in a background mode: `sleep 15 &`, the sleep command will run in a background mode, we can see the state of background running programs with: `jobs`.
- If we expect output from a background running program, it is preferably to redirect the output to a specified file. 

### Control keys
- `CTRL-U` :  kill, Erase entire command line.
- `CTRL-C` :  intr, Stop current command.
