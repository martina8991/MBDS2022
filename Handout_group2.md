# Cheatsheet Undoing changes and restoring old file versions with Git

Authors: Martina Mayrhofer, Melany Rieger, Daniela Serra

## Git checkout
Is used for looking at old commits and make it a new working directory.
It also checks for branch updates.
It is important to know that this command restores old versions without interfering with the latest version.
1. git checkout
2. git checkout -b -> create a new branch
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
1. git reset --soft -> All commits up to the specified header are pushed back into the staging area.
2. git reset --mixed -> All commits up to the specified header are pushed back into the working directory.
3. git reset --hard -> All commits up to the specified header are completely deleted.
Important to note:
With reset commands, the history is always deleted accordingly. 

## Additional commands
### Git clean
It only works for untracked files. It only deletes the file and no change within the file.
The command is no longer reversible.