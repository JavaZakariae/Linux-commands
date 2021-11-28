# Learning the bash shell

- Print the version of the bash : `echo $BASH_VERSION`
- Print the current running shell: `echo $SHELL`
- `(~)`: the tilde notation is an abbreviation of the home directory.
- `cd -` : changes to whatever directory you were in before the current one. 

- Basic wildcards:
  - `?`: any single character
  - `*`: any string of characters
  - `[set]`: any character int set
  - `[!set]`: any character not int set
  - `[.,;]`: match . , or ;
  - `[-_]` : - or _
  - `[!0-9]`: match all non digits
  - `[\!]`: match the exclamation symbol
