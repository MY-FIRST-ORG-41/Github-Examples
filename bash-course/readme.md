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
if you find the directory 



