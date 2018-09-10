#Check if mongod version is above 4.0.0
	> mongod --version
	Don't know why but 4.0.2 works
>If not remove old version and install 4.0.2
	apt-get purge mongo*
	install here https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/
	

#Some note: changing mongodb path
https://medium.com/@paulrohan/how-to-install-mongodb-on-ubuntu-15-04-and-15-10-9301e53a0d94

#Start service
sudo service mongod start
Confirm by tailing: /var/log/mongodb/mongod.log

#Restart
sudo service mongod restart

#18.04 Unit mongod.service not found.
mongod -->  IllegalOperation: Attempted to create a lock file on a read-only directory: /data/db, terminating

> System config
vim /lib/systemd/system/mongodb.service