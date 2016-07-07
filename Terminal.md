
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

`ps axu`
---
[Manual](http://linux.die.net/man/1/ps)
[Process codes](http://serverfault.com/questions/319684/what-s-s1-t-r-mean-in-ps-ax-ps-list)
One cannot take control of orphaned process started in different shell.
Use `screen`.


#screen

screen -ls : see the list
screen -r #process_number  : return to process
screen -r #process_name    : return to process
screen -S newone   :  create and attach to new screen named newone

ctrl + A + D : detach from screen


`crontab`
---
http://www.adminschoice.com/crontab-quick-reference
crontab -e
crontab -l

> One should escape % with \ when running crontab.

#date
shell-ээс, ялангуяа crontab.аас date хувьсагч ашиглаж байгаа бол ENV.оосоо хамаарч хэл өөр байх магадлалтай тул доорхи шиг тухай бүрд зааж өгөх.
LANG=en_US.UTF-8 date

Эсвэл бүр системийн тохиргоогоо Англи болгож болно.  
env LC_ALL=c date

* Гэхдээ энэ тохиолдолд хамаагүй.
$(date +\%Y-\%m-\%d)

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

#find text in file
grep -R "*in" ./dir/
grep '^\.Pp' myfile

#look for files
find / -type f -name "*.conf"

#See file and directory size
du -sh /*

#See disk free space
df -h

#View multicore CPU load balance using top command
Press 1(Breakdown of cpu) or I(toggle Iris mode)

#download htop

#Find files not owned by specific user
find . \! -user foo -print