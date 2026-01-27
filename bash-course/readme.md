# Chapter 1

## Bash
>  The standard command-line shell and scripting language used on most Linux systems. It is the program that acts as the REPL in a typical terminal session.

In Bash, the dash (-) or double-dash (--) is used to distinguish options (also called "flags") from the actual data you want to process. 

Why do we mix alphabets with it?
Mixing letters with dashes tells a command how to behave rather than what to act on.

Single Dash (-) for Short Options: These are single letters used for speed. For example, read -r tells the read command to use the "raw" option.

Double Dash (--) for Long Options: These use full words to make scripts easier to read. For example, ls --all is the same as ls -a, but it is much clearer to someone reading your code.

Chaining: You can often combine short options to save time. Typing ls -la is a shortcut for typing ls -l -a.

## REPL
>  Stans for `read eval print loop` An interactive software environment that reads user input, executes (evaluates) it, displays the result (prints), and repeats this process (loops). Bash is a program that uses this structure.
## Linux
>	The kernel, which is the core software that manages a computer's hardware resources. Ubuntu is built on top of the Linux kernel.
## Ubuntu
>  A complete operating system (a specific distribution of Linux) that bundles the Linux kernel with many other programs, including the Bash shell and a graphical interface.

## Terminal and finder
echo command is used to display a text in the terminal.
```sh
echo "hello world"
```

pwd command is used to show the working directory.
```sh
pwd
```

explorer.exe . command is used to auto open the working directory.
```sh
explorer.exe .
```

ls command is used to list the files of working directory.
```sh
ls
```

If you check the file is exist or not you use.
```sh
test -f file-name
[[ -f file-name ]]
[[ -f file-name ]] && echo if exists
```

when you stop running program you that was run for a long time you use.
```sh
command-name ^C
```


touch is used to creeate the file in any working folder.
```sh
touch file_1.txt
```

mkdir is used to create folder.
```sh
mkdir folder-name
``` 

rm is delete the file.
```sh
rm file-name
```

rmdir  is remove the empty folder if any file or anything inside it they give us error.
```sh
rmdir folder-name
```

 rm -rv this remove folder and all the things inside it.
  >-r (recursive): Required to delete directories and their contents.

  >-v (verbose): Shows you exactly what is being deleted as it happens.
 ```sh
 rm -rv folder-name
 ```

Use this if you want to delete the folder forcefully without being prompted for confirmation.
>-f (force): Ignores non-existent files and never prompts for confirmation.
 ```sh
 rm -rfv foo
 ```

 Change directory us used to change the directory or folder.
 ```sh
 cd /folder-name
 ```

 ## Basic file manipulation

 To rename or move the file we use mv command.
 ```sh
 mv file-name that one you rename and file-name  that renamed your file
 ```

 To copy the file you use.
 ```sh
 cp data-file-name empty-file-name
 ```

 mv command is dangerous if you have already have a file of same name mv overwrite your previous file with new file.

 If you have many files of same name in any folder and you want to delete all the files in one go.
 > give the same name that have same in all the files like lesson-1.txt and lesson is same in all the files so we give.
 ```sh
 rm first-same-filename-*.txt
 ```

When you use -i with rm they give you option to y/n to delete the selective file.
> -i (interactive) prompt you to conferm what you want to do.

```sh
rm -i lesson*
```

When you wnat to create a shortcut of any command you use alias.
>i am creating a shortcut of rm
```sh
alias rm='rm -i'
```
and you wrote alias rm they list your rm command.
>and when you want to remove or delete this shortcut you use.
```sh
unalias rm
```

When you check the history of your all previous command you use.
```sh
history
```

## Hidden files

To create a hidden file we use.
```sh
touch .file-name
```
to list the hidden files we use.
```sh
ls -a
```
When we go to the last working directory we use.
```sh
cd -
```
When we go to the start one first directory we use.
```sh
cd --
```
When we go back directories one by one we use.
```sh
cd ..
```
When we go to another folder we use.
```sh
cd /mnt/folder-name
```

## Searching in files

When we overwrite the new data into the files we use.
```sh
echo data > file-name
```
When we append the data we use
```sh
echo data >> file-name
```
When we check the data under any file we use.
```sh
cat file-name
```
we also use.
```sh
./file-name
```

If you type cat -n myname, the -n tells the computer to use the option to show line numbers
```sh
cat -n myname
```

they show all the data.

When we grep or get specific data within a file we use.
```sh
grep data file-name
```
when we grep the data and we know the starting word so we use.
```sh
grep '^data' file name
```
that means only grab the data that was start with data word `^` this is used to tell the starting.

When we only know the ending or last words we use.
```sh
grep 'data$' file-name
```
the `$` sign show the ending.

when we find a text one line after the word or letter we know we use.
```sh
grep -A1 data file-name
```

when we find a text one line before the word or letter we know we use.
```sh
grep -B1 data file.txt
```

when you find the middle line after and before you use.
```sh
 grep -C1 data file.txt
```

when your data is casesensitive and you get all the related data you use.
```sh
grep -i data file-name
```

when you find only the matching data that is casesensitive we use.
`^data.` this means starting with selecting character and after this any.
```sh
grep -io '^data.' file-name
```

when we need to get very specific character from the data we use pipelines.

`|` this is a pipeline.
```sh
cat file-name | grep -i data | grep data
```
this is a query with pipeline. you use pipeliines according to your need.

we also use `>` like pipeline.
```sh
cat file-name > empty-file-name
```
and `<<` this is document.
and `<<<` this is here string.
```sh
command <<< "string" 
or
command <<< $variable
```
```sh
file_list="image.png,data.csv,notes.txt"
grep -o "data.csv" <<< "$file_list"
```
`-o` means only matching this command means instead of printing the whole line of file_list only print the matiching pattern so the matching pattern is data.csv output.
```sh
data.csv
```

## Paging Files

when you add paging you use less.
you use less with pipelines is more powerfull instead of using less alone.
```sh
less file-name or data-path
or
cat file.txt | grep -i data | less
```
you also use `/` for search data in less.

## Manual pages

It is very usefull in bash when you find the information or documentaion of your command you use and it not show the information about builtin-commands.
```sh
man command-name
```

And you also use help to find the information about your built-in-commands it only show the information about buitin-commands.
```sh
help command-name
```
when you find type of your command you use.
```sh
type command-name
```
and when you find all the types of your command you use.
```sh
type -a command-name
```
and when you find your all the built-in comands you use.
```sh
compgen -b
```
this will list all the built-in commands.

And when you write your all built-in commands data into another file in one go you use.
```sh
compgen -b > file-name
```

# Chapter 2

## Programs and commands

when you find the type of your text under the file you use.
for a single or specific file.
```sh
file file-name
```
for all files.
```sh
file *.txt
```

The command echo "$PATH" is used to display the current value of the PATH environment variable in a Unix-like shell
```sh
echo "$PATH"
```

when you replace something you use tanslate.
```sh
echo "$PATH" | tr : '\n'
```
here `:` is replace with `\n` so eveything that have after the colon they are going to new line.

`tr` is use for tranzlate.

## Basic Variables

when you create a variable in bash you use
```sh
name = 'muneeb'
```
And when you use this variable.
```sh
echo "$name"
```
we have many built-in variables like.
when you find the user.
```sh
echo $USER
OR
woami
```
when you find your scripting shell you use.
```sh
echo $SHELL
```
when you find the type of the machine you use.
```sh
echo $MACHTYPE
```
when you find the hostname you use.
```sh
echo $HOSTNAME
```
when you unset the varible you use.
```sh
unset varible-name
```
when you find the name of your system you use.
```sh
uname
```
when you find all the details of your system you use.
```sh
uname -a
```

## Vim crash course

vim is a text editor if you don't have vim so install vim.
```sh
apt install vim
```
when you go to the vim editor you simply use.
```sh
vim file-name or path-name
```
if you write anything to vim you use `i` now you go to the insert form and when you go back to the normal form you press `esc` and when you save the inserting text into your file you press `:` and then you press `w` for write and whe you quit you use `:` and then `q` we also use `wq` to write and quit at a same time.

we have a shortcut keys in vim to delete and paste new-line etc.
```sh
dd is use to delete a line.
p is used to paste a line.
o is use to go to a brand new line.
shift+o is used to got backward to a brand new line.
. period is use for do the current command task like if you press dd to delete a line and then you press period they delete your line and if you press p to paste a line and then you press period thy paste your line.
```

we create script on vim. go to vim using vim file-name and write any command under the vim text editor and save it and when you run bash file-name they vim run your command automatically that command you give under the vim.
```sh
vim file-name
under the vim i write `ls` and save the file.
when i write `bash file-name` they use `ls` automatically.
```
you also use bat for full output like syntax highlighting.
```sh
bat file-name
```

## File Permissions

we check over file have permission or not by using
```sh
ls -l
```
`-l` is using for long `ls -l` means long listing.

if your syntax is looking like this means your file have permission.
```sh
-rwxrwxrwx
```
and if they look like this meand permission is denied of this file.
```sh
-rw-r--r--
```

To give the permission to your file you use.
```sh
chmod +x file-name
```

To give forcefully permission to a file you use.
```sh
chmod 755 file-name
```
now you run `./file-name` they show you the data inside your file.

if your vim text editor show you syntax erorr of bash so in text editor give the path of bash find echo $SHELL command for path finding and then give this path to the text editor like this `#!/bin/bash` like this.

## Scripting

We have syntax checker command if you want to check the syntax of any bash script you use.
```sh
bash -n file-name
echo $?
```
if file exists `echo $?` give `0` and if not exists they give `1`.

when you take a input form user you use read.
```sh
read variable-name
```
and when you press `enter` they wait you for give any name when you give name they store that name in the variable you give and you see that name using echo $v-name.

Instead of a blank screen, you can ask a question using -p:
```sh
read -p "What is your favorite color? " color
echo "You chose $color!"
```

if you check many flags working you use.
```sh
help test
```

In Bash, $@ is a special parameter used to represent all arguments passed to a script or function means when you use loop instead of giving many paratmeters name for the argumnets use this they represent all the arguments passed for loop.
```sh
"$@"
```

## Loops
syntax of loop.
>#### For loop
```sh
for variable in list_of_items
do
    # Commands to be executed
done
```
```sh
for i in {1..5}
do
    echo "Iteration $i"
done
```
>#### While loop
```sh
while [ condition ]
do
    # Commands to be executed
done
```
```sh
count=1
while [ $count -le 5 ]
do
    echo "Count is $count"
    ((count++))
done
```
>#### Until loop
```sh
until [ condition ]
do
  # Commands to be executed until the condition is true
done
```
```sh
count=1
until [ $count -gt 5 ]
do
  echo "Count is $count"
  ((count++))
done
```
>#### Loop with continue and break
```sh
for i in {1..5}
do
  if [ $i -eq 3 ]; then
    continue # Skip the rest of the commands in this iteration
  fi
  echo "Number: $i"
  if [ $i -eq 4 ]; then
    break # Exit the loop entirely
  fi
done
```

## Functions

syntax of functions in bash.
```sh
function_name () {
  # Commands to be executed within the function
}
```

## Conditionals

The syntax of conditionals.
```sh
if [ condition ]; then
    # commands to run if true
elif [ condition2 ]; then
    # commands to run if condition1 is false and condition2 is true
else
    # commands to run if all previous conditions are false
fi
```
```sh
case "$variable" in
    pattern1)
        # commands
        ;;
    pattern2|pattern3)
        # commands
        ;;
    *)
        # default commands
        ;;
esac
```
```sh
if [ "$1" == "hello" ]; then
    echo "You said hello!"
else
    echo "You said something else."
fi  # This 'fi' closes the entire 'if' block above
```

if you write abc x to z so you don't need to write all the abc you only need to use.
```sh
A..z
1..10
```
they write all the abc and 1 to 10 counting for you.

## Input and output

when you fine decimal no of your word etc you use.
```sh
xxz
hexdump
od
```

When you run echo -n hello, the result hellomuneebahmad@DESKTOP-IVD4ROP... occurs because the -n flag tells the terminal not to move to a new line after printing the text.
```sh
echo -n data
```
This -n flag suppresses that newline means stop the newline that comes after end.

# Chapter 3

## Recap

practice the previous commands and then go further.

# Chapter 4

## Case statements

Syntax of case statements.
```sh
case "$variable" in
    pattern1)
        # commands
        ;;
    pattern2|pattern3)
        # commands
        ;;
    *)
        # default commands
        ;;
esac
```

# Chapter 4

## Indexed arrays

Declare an array with elements.
```sh
my_array=("apple" "banana" "cherry")
```

Declare an empty array.
```sh
declare -a another_array
```

Assign individual elements.
```sh
another_array[0]="first"
another_array[1]="second"
```

Access the elements
```sh
echo ${my_array[0]}
echo ${my_array[1]}
echo ${my_array[-1]}
```

Expands each element to a separate word (recommended for loops)
```sh
echo "${my_array[@]}"
```
Expands to a single word with all elements separated by the first character of IFS (Internal Field Separator)
```sh
echo "${my_array[*]}"
```

Append new elements to the end
```sh
my_array+=("date" "elderberry")
```
Remove a specific element
```sh
unset my_array[1]
```
Remove the entire array
```sh
unset my_array
```
Getting Array Length (Number of elements):
```sh
echo ${#my_array[@]}
echo ${#variable-name}
```
`#` is working like a length function in bash they tell us the length of any variable or etc.

## Associative arrays

Associative arrays must be explicitly declared with declare -A.
```sh
declare -A assoc_array
assoc_array[key1]="value1"
assoc_array[key2]="value2"
```

Compound assignment
```sh
declare -A colors=([red]="FF0000" [blue]="0000FF")
```
Accessing elements.
```sh
echo ${colors[red]}
```
Accessing All Keys (Indices):
```sh
echo "${!colors[@]}"
```

## IFS variables

The IFS (Internal Field Separator) variable in Bash is a special shell variable that defines the character or characters used as delimiters to split strings into words or fields.

Set IFS to a comma for this single command
```sh
line="field1,field2,field3"
IFS=',' read -r var1 var2 var3 <<< "$line"
echo "Var1: $var1, Var2: $var2, Var3: $var3"
```

```sh
line="apple,banana,cherry"
```
Set IFS to a comma *only* for the read command
```sh
IFS=',' read -r field1 field2 field3 <<< "$line"

echo "Field 1: $field1"
echo "Field 2: $field2"
echo "Field 3: $field3"
```
IFS is working same as split function in python.

## Command subsitution

Command substitution runs a command and replaces it with the actual text output. 

Analogy: It’s like copying a value from a calculator and pasting it into a document.

When to use: When you need a specific piece of data (like a date, username, or file count) to use as a string or store in a variable.

Limitation: It waits for the command to finish completely before "pasting" the result, and it stores everything in memory. 

The 'date' command runs, and the text "Wed Jan 21..." replaces the $(...) part.
```sh
echo "Hello $(whoami)"
```
output
```sh
Hello username
```

when you move file into any directory you use.
```sh
mv file-name directory-name/
```

when you move many file into any directory in one go you also use.
```sh
mv file-name1 file-name2 file-name3 directory-name/
```

when you move all the files in any directory in one go you use.
```sh
mv * directory-name/
```
## Arthematic operators 

To check the documentaion page of this operation for information you use.
```sh
 help let
 ```
 ```sh
 id++, id--      variable post-increment, post-decrement
        ++id, --id      variable pre-increment, pre-decrement
        -, +            unary minus, plus
        !, ~            logical and bitwise negation
        **              exponentiation
        *, /, %         multiplication, division, remainder
        +, -            addition, subtraction
        <<, >>          left and right bitwise shifts
        <=, >=, <, >    comparison
        ==, !=          equality, inequality
        &               bitwise AND
        ^               bitwise XOR
        |               bitwise OR
        &&              logical AND
        ||              logical OR
        expr ? expr : expr
                        conditional operator
        =, *=, /=, %=,
        +=, -=, <<=, >>=,
        &=, ^=, |=      assignment
```

## Processes substituion
Process substitution runs a command and replaces it with a temporary filename (usually something like /dev/fd/63). 

Analogy: Instead of copying the text, it’s like creating a temporary live-feed document that other programs can read from as if it were a physical file.

When to use: When a command requires a file path as an argument, but you want to give it the output of another command without actually saving a real file.

Benefit: It works in "streaming" fashion. The reading command can start processing data immediately before the first command has even finished.

syntax.
```sh
files=$(ls)
echo "$files"
```

output
```sh
/dev/fd/63
```
## Recap

Practice all the preious sections.

# Chapter 5

## Cut and Tr

`cut` is used to extract sections from lines, while `tr` is used to translate, delete, or squeeze (compress) individual characters. 
```sh
echo file-name | tr : '\n'
```
they replace all the `:` in the file with `\n` new line.
```sh
echo file-name | cut -d , -f 2
```
`-d` is delimeter and `-f` is field.

Extract the first five characters of a string
```sh
echo "Hello World" | cut -c 1-5
Output: Hello
```
Extract the first and third fields using a space as a delimiter
```sh
echo "apple orange banana" | cut -d' ' -f1,3
Output: apple banana
```

Extract fields 2 through 4 from a colon-delimited line
```sh
echo "user:x:1000:1000:User Name:/home/user:/bin/bash" | cut -d':' -f2-4
Output: x:1000:1000
```
You also use cut like this.
```sh
cut -d' ' -f1,3 /etc/passwd or any file-path
```

## Sed awk and grep

if you check users in you system you use.
```sh
cat /etc/passwd
```
for help.
```sh
man 5 passwd
```
if you change the name of your system you use.
```sh
sed 's/changeable-system-name/given-name/'
```
if you change expression you use.
```sh
sed -e 's/bash/fish/'
```
`-e` for exprerssion now bash is changes as fish.
if you don't want to use `-e` you use.
```sh
sed 's#/bin/bash#/bin/fish#'
```
if you don't want to use `#` sign you use `|` or `//`.

Awk is a language but we learn bash so we touch a little bit of awk.
```sh
cat /etc/passwd | awk '{ print $0 }'
cat /etc/passwd | awk '{ print $1 }'
cat /etc/passwd | awk -F: '{ print $1 }'
cat /etc/passwd | awk -F: '{ print $2 }'
cat /etc/passwd | awk -F: '{ print $2, $7 }'
cat /etc/passwd | awk -F: '{ printf("%s has shell %s\n", $2, $7); }'
cat /etc/passwd | awk -F: '$1=="muneebahmad" { print $1, $7 }'
```
there is some command of awk.
we have some usefull commands.
```sh
sort
uniq
uniq -c 
```
`-c` for count.
we have a word count command.
```sh
wc
wc -l
wc -c
wc -w
```
`-l` for lines
`-c` for character
`-w` for words
`wc` for all

## Find command

if you find the files and directories in your current directry you use.
```sh
find .
```
`.` this shows you current directory and give you all the files of your current directory.

if you find only regular files you use.
```sh
find . -type f
find path-name -type f
```
if you find directory.
```sh
find . -type d
```
if you find siblings.
```sh
find . -type l
```
for empty directory.
```sh
find /var/empty/ -type d
find /var/empty/ -type f
```
for help.
```sh
man find
```
`/` using forward slash you search in man page.
```sh
  b      block (buffered) special

              c      character (unbuffered) special

              d      directory

              p      named pipe (FIFO)

              f      regular file

              l      symbolic link; this is never true if the -L option or the -follow option is  in  effect,  unless
                     the symbolic link is broken.  If you want to search for symbolic links when -L is in effect, use
                     -xtype.

              s      socket

              D      door (Solaris)
```

They give all the .txt files.
```sh
find path-name -type f -name '*.txt'
find path-name -type f -name '*.txt' -exec echo i found a file {} yay
```
`-exec` give msg i found a file with all finding files and end with yay {} under brackets have file-path.

## Bash Arguments

when you debug your bash script or to check the error clearly you use.
```sh
bash -x script-name
```
you also set this under the script.
```sh
set -x
```
to disable it use.
```sh
set +x
```
you also use ps4 variable in your script.
```sh
ps4='hello: ' bash -x script-name
```
```sh
output
hello: `content-of-bash-script`
```

If you check the syntax of you script you use `-n` is use for syntax checking if your syntax is incorrect they show you the syntax error only without printing the whole correct version and error version.
```sh
bash -n script-name
```
`-u` is use for check the undefined variable.
```sh
bash -u script-name
```
you set environment variable in script.
```sh
variable-name=data script-name
```
```
export variable-name=data
```
when you declare this same variable under the script they use you environment variable data.

you use shellcheck for bash and other scripts they check for prompts and errors.
```sh
shellcheck script-name
```

## Pipe status

if you have very big and complex pipeline and you run `echo $?` this for check the pipeline and they always give you your pipeline is good because first command of your pipeline is working but there is any command in your pipeline is failing and you check it which one is fail and which one is correct you use.
```sh
echo "${PIPESTATUS[*]}"
```
If you have four command in your pipline the output is.
```sh
TRUE | FALSE | TRUE | FALSE
  0      1       0      1
```
 `1` is for wrong and `0` is for correct.

## Timing commands

To check the time of your command that you run.
```sh
man time
help time
time command
```
In simple words, `htop` is the "Task Manager" for your Linux or Unix-based terminal. While a standard terminal just shows text, htop provides a colorful, interactive dashboard that shows exactly what your computer is doing in real-time. 
```sh
sudo apt install htop
htop
```
Common Interactive Commands
Key 	Function

`htop -S`	Setup: Configure meters, colors, and visible columns.

`htop -/`	Search: Find a specific process by name.

`htop -\`	Filter: Show only processes matching a specific string.

`htop -t`	Tree View: Group processes by parent-child relationships.

`F6 / < / >`	Sort: Choose which column (e.g., MEM%, CPU%) to sort by.

`htop -k`	Kill: Send signals (like SIGTERM or SIGKILL) to terminate a process.

`htop -q`	Quit: Exit the htop application.

`htop -u` User Filter: Show only processes owned by a specific user.

`Space	Tag`: Select multiple processes to perform bulk actions.

## Sudo
`sudo` stands for "SuperUser Do."
Think of it as the "Please" command for your computer.

`How it works`:
>Normally, your computer limits what you can do to prevent you from accidentally breaking something important (like deleting system files). sudo is how you tell the computer, "I am the administrator, and I know what I'm doing."

`Without sudo`:
>You are like a guest in a house. you can move the chairs or open the fridge, but you can’t knock down a wall or change the locks.

`With sudo`:
>You are the owner of the house. You have the "master key" to do anything, including major renovations.

`Examples':

`Normal command`: `apt install game`
>`Result`: 
>>Permission Denied (the computer won't let a "guest" install software).

`With sudo`: `sudo apt install game`
>`Result`: 
>>The computer asks for your password, then installs the game.

## Sourcing code

In bash `.` and `source` are same.
source is like using your script code in another empty script like use this at the top of your code script `source` and `.` and the name of your empty script.
```sh
help source
help .
source ./directory-name/empty-script-name
. ./directory-name/empty-script-name
. ./directory-name/empty-script-name || exit 1
```
and when you use `./directory-name/empty-script-name` they show all the data that have in your main script.

you also use directory name like this.
```sh
libdirs=./directory-name
. -p "$libdirs" script-name || exit 1
source -p "$libdirs" script-name || exit 1
```
when you directly called some function in your script like python function `if name == '__main__'` so use.
```sh
if ! (return 2>/dev/null); then
      function-name
      #we are being called directly
fi
```
## Curlies vs. parens

`nl` is used for number lines
```sh
nl
```
`Parentheses ( ) — Subshell Example`
>Commands inside parentheses run in a subshell. Any environment changes (like defining a variable or changing directories) are lost when the subshell finishes.
```sh
# Set a starting variable
x=10

# Run commands in a subshell
( x=20; cd /tmp; echo "Inside subshell: x=$x, pwd=$(pwd)" )

# Check values in the main shell
echo "Outside subshell: x=$x, pwd=$(pwd)"
```
`output`
```sh
Inside subshell: x=20, pwd=/tmp
Outside subshell: x=10, pwd=/home/user
```
`Curly Braces { } — Current Shell`

`Example`
>Commands inside curly braces run in the current shell environment. Changes persist after the block ends.

`Syntax Rule`: 
>You must have a space after { and a semicolon (or newline) before }.
```sh
# Set a starting variable
y=10

# Run commands in the current shell
{ y=20; cd /tmp; echo "Inside braces: y=$y, pwd=$(pwd)"; }

# Check values in the main shell
echo "Outside braces: y=$y, pwd=$(pwd)"
```
`output`
```sh
Inside braces: y=20, pwd=/tmp
Outside braces: y=20, pwd=/tmp
```

## Return vs output

`return`
>is used to set the exit status (numeric, 0-255) of a function, indicating success or failure.

`Output`
>(echo) sends data to stdout (text/string), allowing the caller to capture that information. 
```sh
#!/bin/bash

# Function using BOTH return and output
my_function() {
    echo "Hello World"  # This is the OUTPUT (stdout)
    return 3            # This is the RETURN STATUS ($?)
}

# 1. Capture the output in a variable
captured_output=$(my_function)

# 2. Get the return status ($?)
my_function
exit_status=$?

echo "Output: $captured_output"
echo "Exit Status: $exit_status"
```
`output`
```sh
Hello World
Output: Hello World
Exit Status: 3
```

## Recap
practice the previous commands and then go to the next

# Chapter 8

## Parameter expansion

when you get length of the string.
```sh
echo "${#variable-name}"
```
when you captialize the first letter of the string.
```sh
echo "${variable-name^}"
echo "${variable-name^ch-name}
```
when you captialize the whole string
```sh
echo "${variable-name^^}"
```
when you captialize only the specific character in whole string.
```sh
echo "${variable-name^^ch-name}"
```
we also captialize more then one character in whole string.
```sh
echo "${variable-name^^[ch-names]}"
```
we also convert the capital to lower.
```sh
echo "${variable-name,,}"
echo "${variable-name,}"
echo "${variable-name,,capital-ch-name}"
echo "${variable-name,,[capital-ch-names]}
```
we also set default value to a parameter.
```sh
name=$1
name=${1:-Muneeb}
```
when you run the script without passing an argument Muneeb is running as default.

we also set command or variable in this.
```sh
name=${1:-$USER}
```
When you run the script without giving an argument they show you the username they use the `$USER` command and when you give any name as argument they work as parameter and give you the name.

if you use.
```sh
name=${1?}
name={1?'you must supply a name'}
```
now when you run the script without passing an arrgument they give you an error message parameter value is not set by default argument is required.

when you change the path name you use many things you also use this.
```sh
echo "${Path/o/a}"
echo "${Path//o/a}"
```
if you find the directory path or file path or system path you use.
```sh
echo "$PATH"
dirname "$PATH"
basename "$PATH"
```
We also delete specific part form path using.
```sh
echo "${Path#*/}"
echo "${Path##*/}"
echo "${Path%/*}"
echo "${Path//[af]/o}"
echo "${Path//[af]/5}"
echo "${Path//[afvc]/5}"
echo "${Path//[afvc]/__&__}"
echo "${Path//[afvc]/__\&__}"
```
`#` sign means delete form the left.
`%` sign means delete form the right.
`/` slash meand find and replace.

When you make substrings in bash you use.
```sh
echo "${s:0}"
echo "${s:1}"
echo "${s:2}"
echo "${s:3}"
echo "${s:0:2}"
echo "${s:3:5}"
echo "${s:1:-1}"
```
`:` is used for define substring.
we also go backwards by using `-`.


## Parameter transformation

Quotes the value in a format reusable as input.
```sh
${var@Q}
```

Expands backslash escape sequences (like \n) in the value.(Expands escapes if present)
```sh	
${var@E}
```

Expands the value as if it were a prompt string (e.g., \u@\h).	user@hostname (if set)
```sh
${var@P}	
```

Expands to an assignment statement or declare command.	var='hello world'
```sh
${var@A}	
```

Expands to a string representing the variable's attributes.	i (for integer), a (for array)
```sh
${var@a}
```	

Quotes array keys and values for reuse as input (indexed/associative).	[0]="val1" [1]="val2"
```sh
${var@K}
```	

Similar to K, but expands keys/values to separate words.
```sh
${var@k}	
```

## Array expansion

`Values`
>Expands to all elements, each as a separate word (Best practice).
```sh
"${arr[@]}"	
```
>Expands to all elements as a single word, joined by IFS (usually space).
```sh
"${arr[*]}"	
```
>Expands to the value at index or key i.
```sh
"${arr[i]}"	
```

`Metadata`
>Returns the total number of elements in the array.
```sh
${#arr[@]}	
```
>Returns all indices (for indexed arrays) or keys (for associative arrays).
```sh
"${!arr[@]}"
```	
>Returns the character length of the string at index i.
```sh
${#arr[i]}	
```

`Slicing`	
>Expands to len elements starting from index off.
```sh
"${arr[@]:off:len}"	
```
>Expands to all elements from index off to the end.
```sh
"${arr[@]:off}"	
```

`Search/Replace`
>Replaces the first match of pat with rep in every element.
```sh
"${arr[@]/pat/rep}"	
```
>of pat with rep in every element.
```sh
"${arr[@]//pat/rep}"	
```
>Replaces pat with rep only if it matches the start of an element.
```sh
"${arr[@]/#pat/rep}"	
```
>Replaces pat with rep only if it matches the end of an element.
```sh
"${arr[@]/%pat/rep}"
```	

`Deletion/Stripping`
>Removes the shortest prefix matching pat from every element.
```sh
"${arr[@]#pat}"
```
>Removes the longest prefix matching pat from every element.
```sh
"${arr[@]##pat}"	
```
>Removes the shortest suffix matching pat from every element.
```sh
"${arr[@]%pat}"	
```
>Removes the longest suffix matching pat from every element.
```sh
"${arr[@]%%pat}"	
```

`Case Mod`	
>Capitalizes the first letter of every element.
```sh
"${arr[@]^}"	
```
>Converts every element to uppercase.
```sh
"${arr[@]^^}"
```	
>Lowercases the first letter of every element.
```sh
"${arr[@],}"
```	
>Converts every element to lowercase.
```sh
"${arr[@],,}"	
```
>If var="arr", this expands to all elements of arr (Bash 5.0+).
```sh
Indirect	${!var[@]}	
```

## Basic globbing

When you seperate your files based as new line means you list your all files and all are in a new line.
```sh
ls -1 directory-name/
ls -1 directory-name/*
ls -1 directory-name/*.txt
ls -1 directory-name/*.jpg
ls -1 directory-name/file-name.*
ls -1 directory-name/ba?.txt
ls -1 directory-name/ba[abcr].txt
ls -1 directory-name/ba[abcr].*
echo directory-name/*
printf '%s\n' directory-name/*
```
`ba?` means after ba is any character.
`ba[abcr]` means after ba is in btw abc or r.

## EXtended globbing
`?(pattern-list)`
>`Explanation`: 
>>Matches zero or one occurrence of the specified patterns.

>`Example`:
```sh
ls -1 photo?(s).jpg
```
>`Matches`: 
```sh
photo.jpg, photos.jpg.
```
>`Does NOT match`:
```sh
photoss.jpg
```

`*(pattern-list)`
>`Explanation`: 
>>Matches zero or more occurrences of the specified patterns.

>`Example`:
```sh
ls -1 file*([0-9]).txt
```
>`Matches`:
```sh
file.txt, file1.txt, file123.txt.
```
>`Does NOT match`: 
```sh
fileA.txt
```

`+(pattern-list)`
>`Explanation`: 
>>Matches one or more occurrences of the specified patterns.

>`Example`: 
```SH
ls -1 ab+(2|3).jpg
```
>`Matches`: 
```SH
ab2.jpg, ab3.jpg, ab222.jpg, ab33.jpg.
```
>`Does NOT match`: 
```sh
ab.jpg (requires at least one occurrence of 2 or 3).
```

`@(pattern-list)`
>`Explanation`: 
>>Matches exactly one of the specified patterns.

>`Example`: 
```sh
ls -1 report.@(pdf|docx)
```
>`Matches`: 
```sh
report.pdf, report.docx.
```
>`Does NOT match`:
```sh
report.txt, report.pdfdocx. 
```

`!(pattern-list)`
>`Explanation`: 
>>Matches anything except the specified patterns.

>`Example`: 
```sh
ls !(*.jpg|*.gif)
```
>`Matches`: 
```sh
file.txt, script.sh, README.md (everything that is not a .jpg or .gif).
```
>`Does NOT match`:
```sh
image.jpg, animation.gif. 
```

The shopt command is a Bash shell built-in that allows users to set and unset options and commands to control various aspects of the shell's behavior.
```sh
help shopt
shopt
shopt extglob
shopt option-name
```
`-s` for  Set.
`-u` for unset.
`-p` for print.
`-q` for quit.
`-o` Restricts the optname values to those used by the set -o command. 

Many shopt options are disabled by default.
```sh
shopt autocd
shopt cdspell
shopt extglob
shopt dotglob
shopt nullglob
shopt cmdhist
```
>`autocd` If set, typing the name of a directory as a command will automatically cd to it.

>`cdspell`	Attempts spelling correction on directory components in the cd command (interactive only).

>`extglob`	Enables extended pattern matching features in the shell (e.g., ?(pattern-list), *(pattern-list), etc.).

>`dotglob`	If set, filename patterns will match filenames beginning with a . (dot).

>`nullglob`	Allows filename patterns that match no files to expand to a null string, rather than themselves.

>`cmdhist`	Saves all lines of a multi-line command as a single history entry for easy re-editing.

if you turned off and on history expansion.
```sh
set -H
set -H
```

## Glob shell options

`nullglob`
>By default, if a glob pattern doesn't match any files, Bash returns the literal pattern itself. nullglob changes this so that unmatched patterns expand to nothing (an empty string). 

>`Enable`: 
```sh
shopt -s nullglob
```
>`Default Behavior`: 
```sh
ls *.zip in an empty folder returns an error: ls: cannot access '*.zip': No such file or directory.
```
>`With nullglob`: 
```sh
ls *.zip expands to just ls, which lists everything in the current directory—a common side effect to be aware of.
```
Best Use: Use this in for loops to ensure the loop doesn't run if no files match the pattern. 

`dotglob`
>Standard globs (like *) ignore hidden files—those starting with a dot .. Enabling dotglob includes hidden files in pattern expansions. 

>`Enable`: 
```sh
shopt -s dotglob
```
>`Default Behavior`: 
```sh
ls * ignores .bashrc or .gitignore.
```
>`With dotglob`: 
```sh
ls * will include .bashrc, .gitignore, and other hidden files.
```
Note: It still typically excludes the special directories . (current) and .. (parent) to prevent accidental recursive loops in commands like rm -rf *. 

`globstar`
>This option enables the ** pattern for recursive directory searching. Without it, ** behaves exactly like a single *. 
>`Enable`: 
```sh
shopt -s globstar
```
>`Recursive Match`: 
```sh
ls **/*.txt matches every .txt file in the current directory and all of its subdirectories at any depth.
```
>`Directory Only`: 
```sh
Using **/ will limit the recursive expansion to only directories and subdirectories.
```
Limitation: It is powerful but can be slow in very large directory trees. 

## Brace expansion

This is a powerfull tool to creating a large number of files very fast.
```sh
echo file{1,2,3}.txt
touch file{1..100}.txt
mkdir -p project/{src,bin,lib}
cp config.sh{,.bak}
output
file1.txt file2.txt file3.txt
cp config.sh config.sh.bak
```
```sh
Numeric: {1..5} → 1 2 3 4 5
Alphabetic: {a..c} → a b c
Zero-padding: {01..05} → 01 02 03 04 05
Increments (Step):echo {0..10..2} → 0 2 4 6 8 10
Nesting:echo {a,{b,c},d} → a b c d
Cartesian Product:
echo {A,B}{1,2} → A1 A2 B1 B2
`seq` 1 20 seq for sequence
```

## Understanding printf

```sh
man 3 printf
```
```sh
printf "%s" "Hello"
printf "%d" 10
printf "%.2f" 3.1415
printf "%x" 255
printf "%q" "a b"
printf "100%%"
printf -v variable-name 'hello %s' muneeb
printf '%s\n' '$variable-name'
```
```sh
%s	String
%d	Signed integer
%f	Floating point	
%x	Hexadecimal
%q	Shell-quoted string
%%	Literal percent sign
```

## Date formatting

```sh
man strftime
date
date +FORMAT
date +%F
date "+%d/%m/%Y %H:%M:%S" 
date -d "yesterday" +%Y-%m-%d
printf "%(FORMAT)T" TIMESTAMP
printf "%(%Y-%m-%d)T\n" -1
current_date=$(date +%Y%m%d)
printf -v my_date "%(%F)T" -1
```
`Common Format Specifiers:`

%Y: 4-digit year (e.g., 2026)
%m: Month of year (01–12)
%d: Day of month (01–31)
%H: Hour (00–23)
%M: Minute (00–59)
%S: Second (00–60)
%F: Full date (YYYY-MM-DD); equivalent to %Y-%m-%d
%T: Full time (HH:MM:SS); equivalent to %H:%M:%S
%s: Seconds since Unix epoch (1970-01-01)

## Regular expression

Common Regex Metacharacters
Bash uses standard POSIX ERE metacharacters:
```sh 
Anchors: ^ (start of line/string), $ (end of line/string).
Quantifiers: * (0 or more), + (1 or more), ? (0 or 1), {n,m} (specific range).
Wildcards: . (any single character except newline).
Classes: [a-z] (range), [^0-9] (negated range).
Alternation: | (logical OR)
```

## Using mapfile

mapfile and readarray are same in bash.
```sh
help mapfile
help readarray
mapfile -t file-name
mapfile -t -n 2 file-name 
```
`-t` is use for trim.
`n 2` is use for select the no of lines.
if you get more information about other flags use help mapfile.

## Brackets vs test

```sh
type -a test
type -a `[`
type -a `[[`
help test
help `[`
help `[[`
```
instead of using `>` or `<` sign to compare numbers use `-gt` if you don't want to use `-gt` use `(())` double parenthesis.

single bracket and double bracket are same in bash but prefer to use double brackets because syntax is simple of double brackets.

## Special strings

`Special Parameters (Built-in Variables)`
>These parameters are reserved by the shell to provide metadata about your script and its execution environment. 
Parameter 	Description
```sh
$0	The name of the script being executed.
$1 to $9	Positional arguments passed to the script.
$#	The total number of arguments passed to the script.
$*	All arguments as a single string (separated by the first character of IFS).
$@	All arguments as separate quoted words.
$?	The exit status of the most recently executed command (0 for success).
$$	The Process ID (PID) of the current shell.
$!	The PID of the most recently executed background process.
$-	Current flags/options set for the shell.
$_	The last argument of the previous command.
```
`2. ANSI-C Escape Sequences ($'...')`
>These sequences represent non-printable or special formatting characters when used within the $'...' quoting syntax.
```sh 
Sequence 	Name	Result
\n	Newline	Moves the cursor to the start of the next line.
\t	Horizontal Tab	Inserts a horizontal tab space.
\r	Carriage Return	Moves the cursor to the beginning of the current line.
\a	Alert (Bell)	Produces an audible or visible alert.
\\	Backslash	Represents a literal backslash \.
\'	Single Quote	Represents a literal single quote '.
\xhh	Hex Value	Character with the hex value hh.
\uHHHH	Unicode	16-bit Unicode character (hex HHHH).
```
`3. Special Characters (Metacharacters)`
>These characters have functional meanings in the shell and must be quoted (e.g., '*' or \*) if you want to use them literally. 
```sh
Character 	Shell Function
#	Starts a comment.
;	Command separator (allows multiple commands on one line).
&	Runs a command in the background.
**`	`**
*	Wildcard: matches any string of characters.
?	Wildcard: matches any single character.
$	Starts a variable expansion or command substitution.
> / <	Output/Input redirection.
"	Partial quoting: preserves most special characters but allows $ and `.
'	Full quoting: treats every character literally.
```

## Trap signals

```sh
help trap 
trap -l
```
when you use your function value in the end of the output.
```sh
trap cleanup
```
when you run your script with info message you use.
```sh
trap fun-name debug
```
when you running your script like job you se.
```sh
trap SIGINFO
trap SIGINT
```

when you kill anything that was running instead of stopping you use.
```sh
ctrl+z
sleep 60
kill %%
kill %1
```
when you check the status of your jobs running you use.
```sh
jobs
```

## Named pipes

```sh
mkfifo ./pipe-name
tmux att
tmux new
```
Tmux used to split the terminal in sub terminals
Install Tmux 
```sh
sudo apt-get install tmux
```
Split the terminal vertically (left and right panes):
```sh
Press Ctrl+b then %
```
Split the terminal horizontally (top and bottom panes):
```sh
Press Ctrl+b then " (double quote)
```
Navigate between panes:
```sh
Press Ctrl+b then an arrow key (up, down, left, or right).
```
Exit a pane:
```sh
Type exit in the pane you wish to close. 
```
GNU Screen
Screen is another robust alternative that is often pre-installed on many systems. 
Install GNU Screen (if not already installed):
```sh
On Ubuntu/Debian: sudo apt-get install screen
```
Enable horizontal split:
```sh
Press Ctrl+a then S (uppercase S).
```
Switch focus to the new region:
```sh
Press Ctrl+a then Tab.
```
Create a new shell in the new region:
```sh
Press Ctrl+a then c (lowercase c). 
```
Using Built-in Terminal Features
Many modern terminal applications include built-in features for splitting windows or tabs without relying on a separate multiplexer. 
GNOME Terminal (Ubuntu default):
```sh
Split horizontally: Shift+Ctrl+D
Split vertically: Ctrl+b (or just open a new tab with Ctrl+Shift+T).
```
iTerm2 (macOS):
```sh
Split vertically: Cmd+D
Split horizontally: Cmd+Shift+D
```
Windows Terminal (Windows 10/11):
```sh
Split vertically: Alt+Shift++ (plus sign)
Split horizontally: Alt+Shift+- (minus sign)
```
Konsole (KDE):
```sh
Split vertically: Ctrl+(
Split horizontally: Ctrl+)
```

## Color output

In Bash, color and style are controlled by ANSI escape sequences. The standard format for these sequences is:
```sh
\e[<STYLE>;<FG_COLOR>;<BG_COLOR>m 
```
`Curl`
```sh
curl ysap.sh
curl xmas.ysap.sh | bash
```
1. Basic Format Breakdown
```sh
\e[: Starts the escape sequence (can also use \033[ or \x1B[).
```
`STYLE`: 
>Numeric code for text formatting (e.g., bold, underline).
`FG_COLOR`: 
>Numeric code for the text color.
`BG_COLOR`: 
>Numeric code for the background color.
`m`: 
>Terminates the escape sequence.
\e[0m: The Reset code. Always use this at the end of a string to stop color bleeding. 

Standard 16-Color Table
These are the most compatible codes across different terminal types.
```sh 
Color 	Style (Normal/Bold)	Foreground (Text)	Background	High Intensity FG
Black	0 / 1	30	40	90
Red	0 / 1	31	41	91
Green	0 / 1	32	42	92
Yellow	0 / 1	33	43	93
Blue	0 / 1	34	44	94
Magenta	0 / 1	35	45	95
Cyan	0 / 1	36	46	96
White	0 / 1	37	47	97
```
Text Style Codes
```sh
Code 	Effect	Note
0	Reset	Clears all styles and colors.
1	Bold	Increases intensity.
2	Dim	Faint text (limited support).
3	Italic	Not universal.
4	Underline	Standard underline.
5	Blink	Often disabled.
7	Inverse	Swaps FG and BG colors.
9	Strikethrough	Limited terminal support.
```
```sh
# Example: Bold Red text on a Green background
echo -e "\e[1;31;42mThis is a test\e[0m"

# Best Practice: Use variables
RED='\e[31m'
NC='\e[0m' # No Color
printf "I ${RED}love${NC} Bash\n"
```
for making the commands little bit easier you use tput.
```sh
tput bold
tput reset
etc
```
## Cursor commands

Cursor Controls
```sh
ESC Code Sequence	Description
ESC[H	moves cursor to home position (0, 0)
ESC[{line};{column}H
ESC[{line};{column}f	moves cursor to line #, column #
ESC[#A	moves cursor up # lines
ESC[#B	moves cursor down # lines
ESC[#C	moves cursor right # columns
ESC[#D	moves cursor left # columns
ESC[#E	moves cursor to beginning of next line, # lines down
ESC[#F	moves cursor to beginning of previous line, # lines up
ESC[#G	moves cursor to column #
ESC[6n	request cursor position (reports as ESC[#;#R)
ESC M	moves cursor one line up, scrolling if needed
ESC 7	save cursor position (DEC)
ESC 8	restores the cursor to the last saved position (DEC)
ESC[s	save cursor position (SCO)
ESC[u	restores the cursor to the last saved position (SCO)
```

## Is a TTY

```sh
man isatty
```

## PS1 variable

In Bash, PS1 (Prompt String 1) is the primary environment variable that defines the appearance of your command-line prompt. 
1. Common Escape Sequences 
Bash interprets special backslash-escaped characters in the PS1 string to display dynamic information. 
```sh
Sequence 	Expanded Meaning
\u	Current username
\h	Hostname (up to the first '.')
\w	Full path of current working directory (~ for home)
\W	Basename of the current directory only
\d	Current date (e.g., "Mon Sep 20")
\t	Current time in 24-hour HH:MM:SS format
\$	Displays # for root user, $ for regular users
\n	Inserts a newline
```
how to test and set ps1
```sh
PS1="\u@\h:\w\$ "
```
when you get the last argument of the last command that was run you use.
```sh
vim !$
```
```sh
set -H
set +H
```
when you search the command under the history you use.
```sh
ctrl+r
```

## Customzing bash

in cd we have autocomplete option if you give some wrong alphabets of your directory-name cd give you a correct directory-name.
```sh
cd directory-name
```
when we go to the current directory we use
```sh
..
```
when we highlight any output from any script we use.
```sh
hl data
hl '[data]'
ls -lha
colordiff file-name-1 file-name-2
truecolor-rainbow
```

## Readline shortcuts

```sh
up-arrow-key
down-arrow-key
```
if you check the previous and afterward commands in history you use.
```sh
alt+p
alt+n
```
if you go backward and forward fast word by word you use.
```sh
alt+f
alt+b
```
when i use swapping btw two words i use.
```sh
alt+t
```
when i want to delete one word back i use.
```sh
alt+d
ctrl+w
```
To go start and end of the command efficiently and delete all the data or commands form your terminal you use.
```sh
ctrl+a
ctrl+e
ctrl+u
```
`Cursor Movement`
```sh
Shortcut 	Description
Ctrl-a	Move to the beginning of the line.
Ctrl-e	Move to the end of the line.
Ctrl-b	Move back one character.
Ctrl-f	Move forward one character.
Alt-b	Move back one word.
Alt-f	Move forward one word.
Ctrl-] x	Move forward to the next occurrence of character x.
```
`Editing Text`
```sh
Shortcut 	Description
Ctrl-d	Delete the character under the cursor.
Backspace	Delete the character before the cursor.
Alt-d	Cut (kill) the word after the cursor.
Ctrl-w	Cut (kill) the word before the cursor.
Ctrl-u	Cut (kill) everything from the cursor to the beginning of the line.
Ctrl-k	Cut (kill) everything from the cursor to the end of the line.
Ctrl-y	Paste (yank) the last cut text at the cursor position.
Ctrl-t	Transpose (swap) the character before the cursor with the one at the cursor.
Alt-t	Transpose (swap) the word before the cursor with the one at/after the cursor.
Ctrl-_	Undo the last editing command.
Alt-r	Undo all changes to the line, restoring its initial state.
```
`History and Completion`
```sh
Shortcut 	Description
Ctrl-p or Up Arrow	Fetch the previous command from the history list.
Ctrl-n or Down Arrow	Fetch the next command from the history list.
Ctrl-r	Start a reverse incremental search through history.
Alt-. or Alt-_	Insert the last argument of the previous command.
Tab	Attempt filename or command completion.
Ctrl-l	Clear the screen, leaving the current line at the top.
Ctrl-x Ctrl-e	Open the current command line in your default text editor ($EDITOR or $VISUAL).
```
`Emacs Mode (Default)`
>These shortcuts work directly on the command line. 
```sh
Category 	Shortcut	Action
Movement	Ctrl-a	Move to beginning of the line
Ctrl-e	Move to end of the line
Ctrl-f	Move forward one character
Ctrl-b	Move backward one character
Alt-f	Move forward one word
Alt-b	Move backward one word
Ctrl-xx	Toggle between line start and current position
Editing	Ctrl-d	Delete character under cursor
Ctrl-h	Delete character before cursor (Backspace)
Ctrl-k	Cut (kill) from cursor to end of line
Ctrl-u	Cut (kill) from cursor to start of line
Ctrl-w	Cut the previous word (using whitespace as boundary)
Alt-d	Cut the word after the cursor
Ctrl-y	Paste (yank) the last cut text
Alt-y	Cycle through previous cuts and paste
Ctrl-_	Undo the last change
Alt-t	Swap (transpose) the last two words
History	Ctrl-p	Previous command in history (Up arrow)
Ctrl-n	Next command in history (Down arrow)
Ctrl-r	Search history backwards (incremental)
Ctrl-s	Search history forwards (incremental)
Alt-.	Insert the last argument of the previous command
Control	Tab	Auto-complete command or filename
Ctrl-l	Clear the screen
Ctrl-c	Cancel current process or clear line
Ctrl-z	Suspend current process
```
`Vi Mode (Command Mode)` 
>After pressing ESC, you enter Command Mode with these standard Vi keys. 
```sh
Category 	Shortcut	Action
Movement	h, l	Move cursor left, right
w, b	Move forward, backward one word
0, $	Move to start, end of line
Editing	i, a	Enter Insert Mode before/after cursor
x	Delete character under cursor
dd	Delete current line
u	Undo last change
v	Edit current line in full $EDITOR (e.g., Vim)
History	k, j	Previous, next history command
/	Search history backward
```


