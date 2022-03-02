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
   #### Length operator
   - if `exo1` is a file, `echo ${#exo1}` will print 4.

   ### Command Substitution
   The syntax of command substitution is: `$(unix command)`.
   Example : `a=$(ls)`, the variable `a` will contain the output of the `ls` command.
   
   ### pushd and popd
   - The functions pushd and popd implement a stack of directories that enable you to move to another directory temporarily and have the shell remember where you were.

   ## Flow control
   Bash supports the follwing flow control construct:
   - if, else.
   - for
   - while
   - until
   - case
   - select

## Shell variables, environement variables 

![image](https://user-images.githubusercontent.com/34305250/155591888-3f549de9-a2ce-4ea6-821c-40ffb9d489b0.png)

- An environement varibale can be accessed by sub process, but a shell variable can be created and acceed only by the shell process.
- `env` or `printenv` : to print the list of the environement variables.
- `export var1=myvariale`: to define a new env variable.
- `unset var1`: to remove the declared env variable.
- `var1=something`: to declare var1 as a shell variable.
- `unset var1`: to delete var1 from the declared shell variables.
- `set`: to print all the shell variable that were set.
- `set -o`: to print all the available shell options, for example make history command available in the shell.
- `set +o history`: will switch off the history option from the shell, no history of the typed commands will be available, `set -o history` to switch on.
- `pstree -s -p 1000`: to print the arborescence of a given process.
- `$USER`: connected user.
- `$Home`: home directory.
- `SHELL`: path of current shell.
- `PWD`: current working directory.
- `UID`: current unique user id.
- `OSTYPE`: the operating system type.
- `PS1` and `PS2`: the prompt.

- Difference between ${} and $(): https://stackoverflow.com/questions/27472540/difference-between-and-in-bash
- A shell program to read an input value and output a command result:
  ```
  #! /bin/bash
  read -p "Which service you want to ckeck the status: " service
  status=$(systemctl status ${service} | grep active)
  echo $status
  ```
- To declare a readonly variable: `readonly variable="hello"`.
- `unset var1`: to unset the variable `var1`, the `var1` will no longer be used, as if it wasn't declared. 
- echo `$?`: to print the exit status of the last executed command.
- `test 1 -eq 1`, followed by echo `$?`: will print 0.
- `test 1 -eq 1` is same as `[ 1 eq 1 ]`, using two brackets, we are allowed to use more operators: `[[ 1 = 1 ]]` 
- `(())` are used to do matematical calculation: 
  ```
    f=$((1+1))
    ((c=3+5))
    echo $f
    echo "c equal to $c"
  ```
- for floating point calculatio, we need to use the `bc` command as follows:
  ```
  d=$(echo "1.2 + 1.3" | bc)
  echo "d equal to $d"
  ```
