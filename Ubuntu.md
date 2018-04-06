#Desktop shortcuts
Desktop entries are located in
 /usr/share/applications or in ~/.local/share/applications 

Applications may have different names.

#Fix networking from command line
> sudo nano /etc/network/interfaces
	auto eth0  
	iface eth0 inet dhcp
> sudo nano /etc/resolv.conf
	nameserver 8.8.8.8
> sudo service networking restart


#pkexec authentication
	echo $$
> In the second terminal run
	pkttyagent --process PID_FROM_STEP_1

#Removing damaged dpkgs
> Unable to remove CLI library packages
	sudo rm /var/lib/dpkg/info lib{glade,glib,gtk}2.0-cil.postrm

#insserv LSB dpkg dependency error 
Remove bad scripts in /etc/init.d

#Broken packages
sudo apt-get update –fix-missing

sudo apt-get autoclean
sudo apt-get update
sudo apt-get upgrade
sudo apt-get autoremove

#Change cpu governor
sudo apt-get install cpufrequtils
sudo cpufreq-set -r -g performance

#Check apt-get package version
apt-cache policy <package name>

#apt-get install specific version
apt-get install <package>=version

#cputool: limit cpu usage by pid
cputool --cpu-limit (or -c) 80 -p <pid>	
> (-P is for group)

3197

#ubuntu window dragging stuck
> Press ESC or Window several times.
> Press Alt + Enter
https://askubuntu.com/questions/607867/ubuntu-14-04-gets-stuck-in-workspace-switcher-window