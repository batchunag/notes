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