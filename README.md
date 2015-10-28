# OSCON tutorial: Git and GitHub Fundamentals
Oct 28, 2015

## Git config
```
git config --list
git config user.name "Franciscus Cornelis Donders"
git config user.email f.donders@donders.ru.nl
git config core.editor vim
```

## Flow of tutorial
```
git init
git status
```
Note there's only one hidden folder with all the plumbing in the repository's root.
So let's add a text file, called `ReadMe.md` with any editor you like.
```
git add ReadMe.md
git commit -m "added a new ReadMe file"
```
After some more changes, we'll do a `git commit` without the `--m` setting.
This is why setting the editor to some known one is helpful, because the default editor `vim` may not be common in your field.

Note that after file editing, `git status` show the file again in *Changes not staged for commit*.

INSERT EXPLANATION of *Working Directory*, *Staging Area*, and *History*.

You can select specific *hunks* from the Working Directory to the Staging Area:
```
git add -p
```
If you reject one or more hunks, or change the file after `git add`, you'll see that in `git status` in both *Staging* and *not staged for commit*.  
Git does not work on a file-basis, but on a patch-basis.
It does not think about files, but about content.

The differences between
* `git diff` shows difference between Staging and Working
* `git diff --staged`
* `git diff HEAD`

SETTING UP OF REMOTE REPOSITORY

```
git remote add origin URL.git
git push --set-upstream origin master
```
The option `--set-upstream` clarifies that the local *master* branch is tracking the remote *master* branch. 

GitHub, GitLab, etc. offer web-interfaces to edit files.
A nice choice is the Markdown format, which automatically gets rendered nicely. 
On your local repository, you have to `git pull` (or more cautiously, `git fetch`, `git merge`) the remote changes to your computer. 

## Tips for teachers
* If you do `git init FOLDER`, you have to *change into that `FOLDER`* to do more `git` commands.
