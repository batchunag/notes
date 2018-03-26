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