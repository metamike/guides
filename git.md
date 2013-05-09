Git
===
Focuses on using git with Github.

Basics
------
* Git configuration: ~/.gitconfig.

    ```
    git config --global user.name "<name>"
    git config --global user.email "<email>"
    git config --global color.ui true
    git config --global color.status auto
    git config --global color.branch auto
    git config --list
    ```
* Create a new branch and switch to it

    ```
    git checkout -b <branch>
    git push origin <branch>
    ```
* Create a remote-tracking branch and switch to it

    ```
    git checkout -b <branch> origin/<branch>
    ```
* Remove a file you added to the staging area

    ```
    git add <file>
    git reset <file>
    rm <file>
    ```
* Show logs at different verbosities

    ```
    git log --stat --summary
    git log -p
    ```
* Show a version of a file

    ```
    git show <tag|branch|commit|HEAD>:<file>
    ```
* Show differences between versions (diff or log).  <from> and <to> can be revisions, tags, branches (tips), or HEAD.

    ```
    git diff <from>..<to> [things]
    git diff <from>.. [things]
    ```
* Push a tag to Github

    ```
    git push origin <tag>
    ```
* Delete a branch

    ```
    git branch -d <branch>
    git push origin :<branch>
    ```
* Clean/Reset working tree completely

    ```
    git clean -fdx
    ```
* Revert a merge

    ```
    git revert -m 1 <SHA of the merge commit>
    ```
* Re-"parent" a branch from one to another (RISKY)

    ```
    git rebase --onto <new parent> <old parent> <branch>
    (conflicts) git add <files> && git rebase --continue
    (abort during conflicts) git rebase --abort
    ```
* Prune remote branches that are dead

    ```
    git remote update --prune
    ```

Concepts
--------
* Locations: Working Set/Tree, Staging Area/Index, Local Repository, Remote Repository
* Git configuration: ~/.gitconfig.
* Fast-forward merge: Git only moves the HEAD pointer to the latest commit on the branch
