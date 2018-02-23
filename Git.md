#Git key cache
https://help.github.com/articles/caching-your-github-password-in-git/#platform-linux

Set 3600 or 7200

#Git see what changed
http://stackoverflow.com/questions/8522619/how-do-i-get-the-list-of-files-about-to-be-updated-by-git-pull-without-knowing

#Multiple users on a computer
https://help.github.com/articles/generating-ssh-keys/#step-4-add-your-ssh-key-to-your-account

#Multiple users on SourceTree
⌘N -> Settings -->Add & Remove accounts


#Gitignore
http://stackoverflow.com/questions/1139762/ignore-files-that-have-already-been-committed-to-a-git-repository

```sh
*it is safer*
git rm --cached filename 

**First commit any outstanding code changes**
git rm -r --cached .
git add .
git commit -m "fixing .gitignore"
```

#Git pull error
 git remote set-url origin https://username@github.com/username/rss.git


##Reset Files
http://stackoverflow.com/questions/1817766/revert-to-origins-master-branchs-version-of-file

Assuming you did not commit the file, or add it to the index, then:
`git checkout filename`
Assuming you added it to the index, but did not commit it, then:
`git reset HEAD filename`
`git checkout filename`
Assuming you did commit it, then:
`git checkout origin/master filename`
Assuming you want to blow away all commits from your branch (VERY DESTRUCTIVE):
`git reset --hard origin/master`

#Clean Untracked files
http://stackoverflow.com/questions/61212/how-do-i-remove-local-untracked-files-from-my-current-git-branch

To see the changes
`git clean -f -n` (-fd directories)  
To execute
`git clean -f` (-fd directories)  

#Checkout remote branch
`git fetch origin`
`git checkout -b test origin/test`

#Create a local branch and checkout
`git checkout -b mybranch`

#Delete local branch
`git branch -d mybranch`

#Push new branch to remote
git push -u origin <branch>

#Overwrite branch
git branch -f mybranch

#Clean
`git clean -df`
`git checkout -- .`
git clean removes all untracked files and git checkout clears all unstaged changes.


#Stash
git stash
sit stash list
git stash apply stash@{2}

git stash show 1
git stash show -p 0
git stash drop 1

git stash {command} {hash} //For dropped stash

#git show
git show object
git show $REV:$FILE
git show somebranch:from/the/root/myfile.txt
git show HEAD^^^:test/test.py
The command takes the usual style of revision, meaning you can use any of the following:

branch name (as suggested by ash)
HEAD + x number of ^ characters
The SHA1 hash of a given revision
The first few (maybe 5) characters of a given SHA1 hash

#git diff
diff two branch
git diff --name-status branch1 branch2
git diff mybranch master -- myfile.cs

#See previous commit changes
git diff HEAD^ HEAD

#git copy from other branch
git checkout otherbranch myfile.txt

#git update last commit message.
git commit --amend (it also works before push)
git push origin -f (publishes by force. Should never use at master)

#git patch the difference
git format-patch mybranch --stdout > diff.patch
git diff mybranch master > diff.txt

#diff apply the changes
git apply --stat diff.patch *check the status without applying*
git apply --check diff.patch *same as above*
git apply -3 diff.txt *If there are conflicts, it uses 3way merge*

#git amend
git am -3 < changes.patch *we can use mergetool*

#git log
git log --follow file.java *to see all the changes*
git log -p --follow file.java *to see all the changes with details*
git log --reverse *see in reversed order*


#Ignore changes to a file that's already tracked 
git update-index --assume-unchanged <file>

#See committed changes about to be pushed
git diff (--stat) --cached origin/my_branch
