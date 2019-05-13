# Git Tutorial

Init & Fetching
------------

    git init : initialise a local repository
    git clone <repo_url> : clone a remote repository
    git remote add origin <repo_url> : add a new remote repository

    git add <file> : add <file> to the index
    git add . : add all files to the index

    git commit -m "message" : add file to the local repository

    git push : push commited changes to the remote repository
    git pull : update the local repository and the working directory
    git pull --all : Fetch all remotes.
    git fetch : update the local repository only

> After a git fetch, git merge updates the working tree. git pull is
> equal to fetch + merge


    git rm -f <file> : delete <file> from index and working directory
    git rm --cached <file> : delete <file> from index

&#13;

> When we modify an exisiting file and before adding it to the index, git
> checkout -- <file> : Discard changes in the working directory.

&#13;

> When we modify an exisiting file and after adding it to the index, git
> reset HEAD <file> : Unstage the index but leave the file as it is in
> the working directory.

&#13;

    git reset --hard HEAD~1 : delete the last commit if it hasn't been pushed and remove all changes even untracked files

&#13;

    git reset && git checkout . && git clean -fd : reset the update completely and drop all changes

Branching
---------

    git branch : list all branches
    git branch -r: list all remote branches
    git branch -a : list all branches

&#13;

    git branch hotfix : create hotfix branch
    git checkout hotfix : switch to hotfix branch

&#13;

    git checkout -b iss55 : create iss55 local branch and switch to it.
    git checkout -b iss55 origin/iss55 : create iss55 local branch from remote one and switch to it.

&#13;

    git branch -d iss55 : delete local branch iss55
    git branch -r -d origin/iss55 : delete the local remote-tracking branch
    git push <where-to-push> <source-ref>:<destination-ref> : Pushing source-ref to remote
    git push origin --delete iss55 : delete the remote branch/ref or tags

&#13;

    git merge hotfix : merge hotfix with the current branch
    git fetch --all --prune : fetch all remote branches (--prune delete all remote-tracking branch)
    git branch -vv : give information about local and tracking branches

Tags
---------

    git tag : list local tags
    git tag -l : list all tags (after fetch --all --prune)
    git tag tagname : create a local tag
    git tag -d tagname : delete local tag
    git push origin tagname : push the tag to the remote branch
    git push origin --delete tagname : delete the remote tag

Squash
----------
    git reset --hard <Last commit HASH before modification>
    git merge --squash <Last commit HASH of modification>

Squash Soft
----------
    git reset --soft <Last commit HASH before modification>

Force push
-----------
    git push origin +HEAD:BRANCH_NAME

Rebase
-----------
    git rebase origin/BRANCH_NAME
