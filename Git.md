#Git key cache
https://help.github.com/articles/caching-your-github-password-in-git/#platform-linux

Set 3600 or 7200

#Git see what changed
http://stackoverflow.com/questions/8522619/how-do-i-get-the-list-of-files-about-to-be-updated-by-git-pull-without-knowing

#Multiple user on a computer
https://help.github.com/articles/generating-ssh-keys/#step-4-add-your-ssh-key-to-your-account


#Gitignore
http://stackoverflow.com/questions/1139762/ignore-files-that-have-already-been-committed-to-a-git-repository

```sh
git rm -r --cached .
git add .
git commit -m "fixing .gitignore"
```



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

`git clean -f -n` (-fd directories)  
`git clean -f` (-fd directories)  