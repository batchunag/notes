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

#insserv: LSB dpkg dependency error 
Remove bad scripts in /etc/init.d

#Broken packages
sudo apt-get update --fix-missing

sudo apt-get autoclean
sudo apt-get update
sudo apt-get upgrade
sudo apt-get autoremove

#remove specific package
sudo apt-get remove <package_name>

#Change cpu governor
sudo apt-get install cpufrequtils
sudo cpufreq-set -r -g performance

#Check apt-get package version
apt-cache policy <package name>

#Get all packages installed
sudo apt list --installed

#Intercept http connections
https://askubuntu.com/questions/252179/how-to-inspect-outgoing-http-requests-of-a-single-application
> Run with sudo -i

To capture the RAW packets ...

sudo tcpdump -i any -w /tmp/http.log &
This will capture all the raw packets, on all ports, on all interfaces and write them to a file, /tmp/http.log.

Run your application. It obviously helps if you do not run any other applications that use HTTP (web browsers).

Kill tcpdump

killall tcpdump
To read the log, use the -A flag and pipe the output toless:

tcpdump -A -r /tmp/http.log | less

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

#Nice terminal
Guake: https://www.binarytides.com/install-guake-xubuntu-14-04/