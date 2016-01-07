
#Tree structure
https://coderwall.com/p/owb6eg/view-folder-tree-in-macosx-terminal

or download
http://www.cyberciti.biz/faq/linux-show-directory-structure-command-line/

#Oh-My-Zsh
```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
[Cheatsheet](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)

#Syntax Highlighting
git clone git://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

Open up ~/.zshrc and add zsh-syntax-highlighting to the end of the plugins=( ... ) array.

#Switch user
sudo -u chunag zsh

Install iTerm
Install Zsh
	See INSTALL file

`ps ax`
---
[Manual](http://linux.die.net/man/1/ps)
[Process codes](http://serverfault.com/questions/319684/what-s-s1-t-r-mean-in-ps-ax-ps-list)

`crontab`
---
 Crontab: 

`copy`
---
cp -pRv source dest


#Network
sudo sysctl -w net.link.ether.inet.proxyall=1
sudo sysctl -w net.inet.ip.forwarding=1


#ifconfig
ifconfig bridge0 create
ifconfig bridge0 up addm en0 addm en1
// ifconfig bridge0 up deletem en0
// ifconfig bridge0 destroy


#Building bridge
 Try configuring ip manually

#rename files #regexp
`for f in *old_part*; do mv $f ${f/old_part/new_part}; done`

#script language
month=$(date +%m)
year=$(date +%Y)

line1="cd ~/"
line2="python a.py $month > ~/out.txt"
line3="python b.py > ~/out_$year$month.txt"
echo -e "$line1\n$line2\n$line3" > out.sh
