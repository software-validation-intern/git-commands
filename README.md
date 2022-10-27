# git-functions-test
## https://rogerdudler.github.io/git-guide/

## Stage changes
```python
git add -A # stages all changes
OR
git add . # stages new files and modifications, without deletions (on the current directory and its subdirectories).
OR
git add -u # stages modifications and deletions, without new files
OR
git add * # means add all files in the current directory, except for files whose name begin with a dot.
```
```python
git add -A is equivalent to git add --all
OR
git add -u is equivalent to git add --update
```

## Create new branch
```python
git switch -c [new branch name]
```

## Push locally created branch to remote [aka update new branch to be on Github]
```python
git push --set-upstream origin [new branch name]
```


## Commit staged changes
```python
git commit -m "[committ message]" # Commit staged changes directly with message
OR
git commit -a # Opens a editor to type in commit messages
```

## Push committed changes to remote [aka push committed changes to be on Github]
```python
git push
OR
git push origin
```

## Revert back to a certain commit
```python
git reset --hard <old-commit-id>
git push -f <remote-name> <branch-name> # To update the Github repo with the remote repo
# eg. git push -f origin master 

git log # To check the <old-commit-id>
git log --oneline -n # The n is the number of logs you want to show
git remote -v # To check <remote-name>, the <remote-name> is the name on the far left
# Branch name is the one you see on Git bash, self explonatory
```

## Delete local branch that is already merged into the master/main branch on remote
```python
git branch --merged master | grep -v '^[ *]*master$' | xargs git branch -d
OR
git branch --merged main | grep -v '^[ *]*main$' | xargs git branch -d
```
