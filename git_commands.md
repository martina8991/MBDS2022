## various git commands
git checkout --. => restores deleted files/stellt letztes commit wieder her\
Git --version => gibt Version an\
git init => muss im richtigen folder durchgeführt werden? => initializes the folder as a repo\
cat .git/refs/heads/master => zeigt hash-Wert vom “Master/Main“ branch \
Git branch –delete “branchname” – deletes branch locally


## Wie erstellt man einen Branch im lokalen Repo ?
git branch “branchname” => macht mir neben dem master/main einen neuen branch\
git checkout „branchname“ => wechselt zu diesem branch \
git branch => zeigt alle Branches + main/master\
git push --set-upstream origin “branchname” => branch wird zu remote repo hinzugefügt (auch als eigener branch, der nicht Teil des masters ist)


## Git Config Command 
git config --global user.name “user”\
git config --global user.email "email"

## git config -l => shows information about account 
git config --list => shows user and e-mail\
git config --global --unset-all user.name => delete username\
git config --global –edit => edit user and e-mail


## git log – Show commit history.
git log -3  # show last 3 commits\
git log --oneline  # show all commits (short format)\
git log --stat  # show the amount each file was changed in commits\
git log --oneline --stat  # options can be combined (that's actually a pretty useful command)

## git show – Show one or more objects (blobs, trees, tags and commits).
git show REVISION:path/to/file  - REVISION can be a Git commit, a tag name, a branch name, a relative commit name\
git show HEAD~2:src/main.py  - view the version of src/main.py from 2 commits ago\
git show 390f  - view log message and textual diff of the commit whose SHA-1 identifier starts with 390f


## git diff – Show changes between commits, commit and working tree, etc. (atlassian.com); examples:
git diff  - show changes WORKING TREE -> INDEX\
git diff --cached  - changes INDEX -> LAST COMMIT; what you would be committing if you run "git commit"\
git diff HEAD  - changes WORKING TREE -> LAST COMMIT; what you would be committing if you run "git commit -a"\
git diff HEAD\~1  - changes WORKING TREE -> SECOND LAST COMMIT\
git diff HEAD\~1 HEAD  - changes SECOND LAST COMMIT -> LAST COMMIT\
git diff --stat  - summarize changes (filenames and amount of changes) WORKING TREE -> INDEX\
git diff --stat <sha1> <sha2>  - summarize changes between two commits


## How to update local repo:
git status => gives files that have been modified\
git add “file-name” => fügt file zum staging hinzu ODER\
git add -A => all changes of all files will be moved to the Staging area\
git status => gives status of repo => what is changed, staged, commited etc.\
git commit -m “message: I changed x and y” => commit to staged changes with a message 


Permanently save user name and pw as a plain text file on device => not very secure!!!!\
git config --global credential.credentialStore plaintext

## Commands for Remote Repo
git remote -v => shows where you can push repo onto (useful for when you download a repo and want to push it onto github on your own repo)\
git remote set-url origin "link to remote repo"\
git push origin master => pushes repo onto the url => as pw use personal access token


## How to pull repo from github?
git pull “link to remote repo”\
Or \
git clone “link to remote repo”\
git clone is how you get a local copy of an existing repository to work on. It's usually only used once for a given repository, unless you want to have multiple working copies of it around.\
git pull (or git fetch + git merge) is how you update that local copy with new commits from the remote repository. If you are collaborating with others, it is a command that you will run frequently.\
Clone: Get a working copy of the remote repository.\
Pull: I am working on this, please get me the new changes that may be updated by others.

## Difference between different commands 
git clone means you are making a copy of the repository in your system.\
git fork means you are copying the repository to your Github account.\
git pull means you are fetching the last modified repository.\
git push means you are returning the repository after modifying it.\
In layman's term: git clone is downloading and git pull is refreshing. 


## Konflikte
Konflikt wenn man das remote repo und das lokale repo gleichzeitig verändert ohne vorher zu pushen/pullen\
Wenn man pushen möchte => rejected \
wen man pullen möchte => fail\
Man kann remote repo pullen und dabei das local und remote mergen => 
1.	git config pull.rebase false
2.	git pull
3.	beide Änderungen werden übernommen im local repo (aber nicht im remote)
Oder\
1.	Git fetch
git fetch => fetches most recent remote repo without overwriting local repo
git fetch gathers any commits from the target branch that do not exist in the current branch and stores them in your local repository. However, it does not merge them with your current branch.

2.	git merge (merged beide Veränderungen, jedoch kann er das nicht selbstständig machen wenn die Veränderung in der gleichen Zeile ist)

3.	Remote Veränderungen werden im local repo übernommen (aber keine localen im remote)


Wenn Konflikt überhaupt nicht lösbar => files wo anders speichern => local repo löschen => online repo nochmal downloaden => manuell schauen wo man die lokalen Änderungen einbauen kann
