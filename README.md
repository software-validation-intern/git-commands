# Useful Git commands...also in case i messed up
## https://rogerdudler.github.io/git-guide/

<br></br>

# Stage changes
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

<br></br>


# Create new branch
```python
git switch -c <new branch name>
```

<br></br>


# Push locally created branch to remote [aka update new branch to be on Github]
```python
git push --set-upstream origin <new branch name>
OR
git push -u origin <branch>
```

<br></br>

# Commit staged changes
```python
git commit -m "<committ message>" # Commit staged changes directly with message
OR
git commit -a # Opens a editor to type in commit messages
```

<br></br>

# Push committed changes to remote [aka push committed changes to be on Github]
```python
git push
OR
git push origin
```

<br></br>

# Revert back to a certain commit
```python
git reset --hard <old-commit-id>
git push -f <remote-name> <branch-name> # To update the Github repo with the remote repo
# eg. git push -f origin master 

git log # To check the <old-commit-id>
git log --oneline -n # The n is the number of logs you want to show
git remote -v # To check <remote-name>, the <remote-name> is the name on the far left
# Branch name is the one you see on Git bash, self explonatory
```

<br></br>

# Delete local branch that is already merged into the master/main branch on remote
```python
git branch --merged master | grep -v '^[ *]*master$' | xargs git branch -d
OR
git branch --merged main | grep -v '^[ *]*main$' | xargs git branch -d
```

<br></br>

# See what files are being tracked
```python
git ls-tree -r master --name-only
```

<br></br>

# Remove exisiting local files/folders that are already being tracked by git
```python
git rm -r --cached --ignore-unmatch folder_name
```

<br></br>
# Remove all existing tracked files by git and commit
```python
git rm -r --cached . && git add . && git commit -am "Remove ignored files"
```

<br></br>

# Markdown guide
- [Markdown syntax docs](https://www.markdownguide.org/basic-syntax/)
- [Include image in markdown](https://stackoverflow.com/questions/42961712/how-to-include-image-as-markdown-in-visual-studio-code)

<br></br>

# Export current environment's package list to a requirements.txt
```python
pip install pipreqs

pipreqs /path/to/project

OR

pip3 freeze > requirements.txt  # This will create the file at whichever directory you are currently in
```

<br></br>

# If you accidentally revert a commit and cannot see its history in changes anymore?
```python
git reflog
git checkout HEAD@{n}
```
