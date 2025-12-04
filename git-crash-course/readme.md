## Git Hidden Folders

There is a folder called `.git` which tells you that our project is a git repo.

If we wanted to create a git repo in new-project so we create the folder and initialize that repo using   `git init`

```sh
mkdir /workspaces/temp/new-project
cd /workspaces/temp/new-project
git init
touch Readme.md
# to open a file
code readme.md 
git status
git add .
git add readme.md
# make changes to readme.md
git commit -m "add readme file"
```

## Clonning

we have three ways to clone: HTTPS, SSH, Github CLI

since we are using github codspaces we create a temporary directory in our workspace

```sh
mkdir /workspaces/temp
cd /workspaces/temp
```

>To connect your github codespaces to your vscode you use three ways `HTTPS` `SSH` `Github-CLI` 

## HTTPS

```sh
git clone https://github.com/MY-FIRST-ORG-41/Github-Examples.git
cd Github-Examples
```

For `HTTPS` you can genrate a personal access token (PAT).

```sh
https://github.com/settings/token
```
you use the personal access token (PAT) as your password when you login.
- Give it access (Permissions) to contents for commits.

## SSH

> First we genrate the `SSh-keys`pair  in your local machine .

```sh
ssh-keygen -t rsa
```

> Path of storing that keys .

```
/home/muneebahmad/.ssh/alt-github_id_rsa.pub
```

> For wsl users if you create a non default keys Add that keys in your local machine .

```sh
eval `ssh-agent`
ssh-add /home/muneebahmad/.ssh/alt-github_id_rsa
```

> To show that keys in your terminal for copy .

```sh
cat /home/muneebahmad/.ssh/alt-github_id_rsa.pub
```

> Copy files and paste it into the github SSH key genration for authenticate over local machine to github .

> Then  We test our connection for github to over local computer here:

```sh
ssh -T git@github.com
```

> If they tell authenticated so then we create the clone .

```sh
git clone git@github.com:MY-FIRST-ORG-41/Github-Examples.git
cd Github-Examples
```

## Github-CLI

Install the CLI

eg. Linux (Ubuntu)

```sh
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
&& sudo mkdir -p -m 755 /etc/apt/keyrings \
&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y
sudo apt update
sudo apt install gh
```
> For login we use .

```sh
gh auth login
```

> Then create clone

```sh
gh repo clone MY-FIRST-ORG-41/Github-Examples
```

## Commits

when we want to commit code we wrtie git commit which will open up the commit edit message in the editor of choice .

```sh
git commit
```
When you commit anything to be update .

```sh
git commit -m "Add another exclamation"
```

> When you create an unwanted commit like before add the file and then add file and again commit and then push they show you two commits so remove the unwanted commit you use .

```sh
git stash
git rebase -i HEAD~2
git stash pop
git push origin dev --force-with-lease
```
To see your local history .

```sh
git log --online
```

When you set your global editor .

```sh
git config --global core.editor emacs
```

## Branches

To create a branch .

```sh
git branch branch-name
```

To check the created branch .

```sh
git branch
git branch --list
```

To switched between two branches .

```sh
git checkout branch-name
```

To delete the branch .

```sh
git branch -d branch-name
```

To push your remote branch like which one you create .

```sh
git push -u origin branch-name
```

## Remotes

We can add remotes via upstream adding a branch .

```sh
git remote add ...
git branch -u origin new-feature
```

## Stashing

When you save your data to anywhere to rebase it and then pop it out you use stashing .

```sh
git stash list
git stash
git stash save my-name
git stash apply
git stash pop
```

## Merging

When you merge between two branches you use .

```sh
git checkout dev
git merge main
```


## Add

when we want to stage changes that will included in the commit we use . to add all possible files.

```sh
git add readme.md
git add .
```

## Remove

To remove a folder

```sh
rm -rf .git/
```

To remove file

 ```sh
 rm Readme.md
 ```

## Reset

Reset allows you to move staged changes to be unstaged
This is usefull when you revert all the files not to be commited

```sh
git add .
git reset
```

> git reset will revert a git add .

## Status

git status shows what files will or will not be commited.

```sh
git status
```

## GitConfig File

Gitconfig file stored your global configurations such as email, name, editor and more.

Showing the contents of your .gitconfig file
```sh
Git config --list --show-origin
git config --list
```
When you first install git on a machine you are suppose to set up your name and email

```sh
git config --global user.name "muneeb ahmad"
git config --global user.email m71443537@gmail.com
```

## Log

Git log will show recent git commits in the list

```sh
git log
```

sometimes we stuck into the git log command to get out of this we press `q` .

## Push

When we want to push a repo to our remote origin

```sh
git push
```

To push your remote branch like which one you create .

```sh
git push -u origin branch-name
```