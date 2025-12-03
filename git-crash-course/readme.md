## Commits

<<<<<<< Updated upstream
## Branches

=======
When we want to commit code we wrtie git commit which will open up the commit edit message in the editor of choice

```sh
git commit
```
Set the global editor

```sh
git config --global core.editor emacs
```

Make a commit and commit message without openning an editor

```sh
git commit -m "Add another exclamation"
```

> When you create an unwanted commit like before add the file and then add the file and again commit and then push they show you two commits so remove the unwanted commit you use .

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

>>>>>>> Stashed changes
## Remotes

## Stashing

## Merging