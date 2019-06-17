#How to update in Ubuntu
Download & Replace

#Idea aliases
alias idea='~/idea/idea-IC-145.972.3/bin/idea.sh > /dev/null 2>&1 &' \~

alias i=`rm *.iml; rm -Rf .idea/; ant clippy-project`
> ant clean idea compile #after `rm *.iml; rm -Rf .idea/`

#Troubleshooting
> check persmission issues.
	Make sure some temp folders like ide-lib are removed.
> Try checkout the code to empty folder.

#Publishing library locally
run `ant publocal` on the project.
run `ant clean` & `ant clippy-project` on another.	

#Resolve unknown references
`ant compile`

#docker list
docker ps

#Show in navigation explorer
See small icons in IDE.

#Compilation
Use "Mark directory as"
and Rebuild

#Long full qualifed imports like com.google.common.base.Strings
--> uncheck "Use fully qualified class names" in Code Style (Imports)

#Keyboard freezes
ibus-daemon -rd

#indy
$ indy -u status
$ indy -u commit -m "Commit message" -r alpha beta

#Ignore dependency
-Dignore.dependency.errors=$(date +%Y%m%d)

#search everywhere
Double Shift
Ctrl+Shift+F

#How to resolve the gradle project.
- Refresh button
- Try to reimport the project.

