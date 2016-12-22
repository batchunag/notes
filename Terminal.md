
#Tree structure
https://coderwall.com/p/owb6eg/view-folder-tree-in-macosx-terminal
`alias tree="find . -print | sed -e 's;[^/]*/;|____;g;s;____|; |;g'"`

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

#Switch to root
sudo -i
su 

#Run command as a different user
$ su - username -c "command"
$ sudo -S -u otheruser whoami
$ sudo -i -u user whoami

#Run as apache
su -s "/bin/bash" -c "/virtualenvs/pyweb/bin/python2.7 my_code.py" apache

#List all user
cat /etc/passwd

`ps axu`
---
[Manual](http://linux.die.net/man/1/ps)
[Process codes](http://serverfault.com/questions/319684/what-s-s1-t-r-mean-in-ps-ax-ps-list)
> One cannot take control of orphaned process started in different shell.
Use `screen`.


#screen

screen -ls : see the list
screen -r #process_number  : return to process
screen -r #process_name    : return to process
screen -S newone   :  create and attach to new screen named newone
screen -D : power detach screen

ctrl + A + D : detach from screen

#foreground and background
Ctrl+Z and bg %job_id	
run `jobs` to see jobs
to bring back `fg %job_id`
> orphan processes can not be controlled but except being killed.

`crontab`
---
http://www.adminschoice.com/crontab-quick-reference
crontab -e
crontab -l

> One should escape % with \ when running crontab.

see log from /var/log/cron

#date
shell-ээс, ялангуяа crontab.аас date хувьсагч ашиглаж байгаа бол ENV.оосоо хамаарч хэл өөр байх магадлалтай тул доорхи шиг тухай бүрд зааж өгөх.
LANG=en_US.UTF-8 date

Эсвэл бүр системийн тохиргоогоо Англи болгож болно.  
env LC_ALL=c date

* Гэхдээ энэ тохиолдолд хамаагүй.
$(date +\%Y-\%m-\%d)

* Date yesterday | last week
$(date -d "yesterday" '+%Y-%m-%d')

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

#See hardware cpu & processor info
sysctl hw

#download htop
brew install

#Run processes parallel with bash
a.sh & b.sh

#Prevent system from sleeping
http://osxdaily.com/2014/06/16/caffeinate-prevent-sleep-while-command-active-mac-os-x/
`caffeinate -i [command / process]`
`caffeinate -d [command / process]`
Also command alone is useful. `caffeinate `

#Find files not owned by specific user
find . \! -user foo -print

#Appending audio files
cat * > xxx.mp3

Different way
cat first_part.mp3 > newfile.mp3
cat second_part.mp3 >> newfile.mp3
cat third_part.mp3 >> newfile.mp3

#Play audio from terminal
afplay alpha.mp3

#Convert audio files 
afconvert pineapple.m4a -o pine.wav -d LEI16@16000
For help->
afconvert -hf
afconvert --help

#Diff show total number of lines
diff file1 file2 | grep "^>" | wc -l


#Unicode
Change locale (use `locale` to check)
```export LC_ALL="ja_JP.UTF-8"```

#Make change global
edit /etc/locale.conf

```
LC_ALL="ja_JP.UTF-8"
export LC_ALL
```

#To keep ssh connection alive for longer period set ~/.ssh/config
```
Host *
  ServerAliveInterval 120
```


#Install different version for python
[Best one](http://stackoverflow.com/questions/5506110/is-it-possible-to-install-another-version-of-python-to-virtualenv)
Another  two tutorial.
[](http://toomuchdata.com/2014/02/16/how-to-install-python-on-centos/)
[](https://www.digitalocean.com/community/tutorials/how-to-set-up-python-2-7-6-and-3-3-3-on-centos-6-4)


#Running python script by apache php with python on virtualenv 
basically, to run by apache:
python and virtualenv should be in public directory.
[Some hints](http://superuser.com/questions/455935/php-script-cant-run-bash-script-sh-permission-denied)


#loop through folder
find . -type d -exec ./RenameImages {} \;

http://stackoverflow.com/questions/24007555/looping-through-folders-and-renaming-all-files-in-each-folder-sequentially-with
using awk: http://stackoverflow.com/questions/1767384/ls-command-how-can-i-get-a-recursive-full-path-listing-one-line-per-file