# Cheatsheet Undoing changes and restoring old file versions with Git

Authors: Martina Mayrhofer, Melany Rieger, Daniela Serra

## Git checkout
Git checkout has a lot of features. The most frequently use cases include:\n
1. It is used for looking at old commits and updates the working directory to represent the state of the old commit. Metaphorically you can "travel back in time" and ckeck previous versions of your directory. 
2. You can have multiple things you're working on different branches and switch easily between branches with checkout.
3. It updates the files in the working directory and then shows you whether you're ahead/behind your origin pointer of that branch.
4. It's also noteworthy that when switching between branches, you can do changes to one branch without interfering with the other one.

Commands:
1. git checkout \<branchname>
2. git checkout -b \<branchname> -> create a new branch 
3. git checkout main -> go back to main branch 

## Git revert
Git revert creates a new commit with the inverse of the chosen commit.
1. We can continue using the same branch.
2. It inverts the changes introduced by the commit and appends a new commit with the resulting inverse content without deleting the commit history.
3. Instead of deleting or orphaning commits in the commit history, a revert will create a new commit that inverses the changes specified.
4. Git revert undoes a single commit —> it does not "revert" back to the previous state of a project by removing all subsequent commits.
5. Is used for bug fixing.

## Git Reset
Different options
1. git reset --soft \<commit SHA> -> All commits up to the specified header are pushed back into the staging area.
2. git reset --mixed \<commit SHA> -> All commits up to the specified header are pushed back into the working directory.
3. git reset --hard \<commit SHA> -> All commits up to the specified header are completely deleted.
Important to note:
With reset commands, the history is always deleted accordingly. 

## Additional commands
### Git clean
It only works for untracked files. It only deletes the file and no change within the file.
The command is no longer reversible.
