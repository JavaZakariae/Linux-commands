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
- `CTRL-B, CTRL-F` : go backward/farward.
- `CTRL-A, CTRL-E` : jump to the beginning/end of the line.

### Profiles
- The files `.bash_profile`, `.bash_logout` and `.bashrc` when you log in or out or start a new shell.
- `source .bash_profile`: the source command executes the commands in the specified file.
- If `.bash_profile` doesen't exist, bash will look for `bash_login`, If that dosen't exist, it will look for `.profile`.
- `.bash_profile` is read and executed only by the login shell, if you start up a new shell by typing shell, it will attempt to read commands from the file `.bashrc`.
- The file `.bash_logout` is read and executed every time a login shell exits.

### Aliases
- An alias can be defined on the command line, in the `bash_profile` or in the `.bashrc` file.
- alias `name=command`, This syntax specifies that `name` is an alias od thegiven command, keep in mind no space before and after the equal symbol.

### Shell Variables

  ```
   echo "alice: $@"
   echo "$0: $1 $2 $3 $4"
   echo "$# arguments"
  ```
   - Assume, the preceiding script is called alice, if we type alice in wonderland, the following output will be printed:
    
  ```
     alice: in wonderland
     alice: in wonderland
     2 arguments
  ```
   In this case, `$3` and `$4` are null. `$0` denote the name of the script, `$1` and `$2` for the given arguments, `$#` for the number of arguments.
   
   ### String Operators
   - `echo ${ varname:- word }` : will print the default value `word` if varname is undefined.
   - `echo ${ varname:= word }` : if `varname` is undefined, print `word` and assign that value to the `varname` variable.
   - `echo ${ varname:?message }`: if `varname` is undefined, print `message`.
