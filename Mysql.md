#Download MySQL Community Server (OSX)
https://dev.mysql.com/downloads/mysql/
	Installed to /usr/local/mysql/bin/mysql
	sudo mysql.server start
> ERROR! The server quit without updating PID file
	It's because OSX mysql & sudo mysql is different.

#log files
mysql -uroot -se "SHOW VARIABLES" | grep -e log_error -e general_log -e slow_query_log

#Workout for mysql socket error on OSX because of MAMP
`Can't connect to local MySQL server through socket '/tmp/mysql.sock'`
ln -s /Applications/MAMP/tmp/mysql/mysql.sock /tmp/mysql.sock

`Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock'`
Couldn't figure out the exact problem. But see below.
Docker has different socket file in its container!

The mysql.sock file is created when INSTANCE starts and is removed when INSTANCE is shutdown.


#user authentication or login
Since 5.7? password column was changed to authentication_string

#change user password
SET PASSWORD FOR 'user-name-here'@'hostname-name-here' = PASSWORD('new-password-here');

#Create user
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';
FLUSH PRIVILEGES;

#Grant privileges for root and other users
`SELECT host,user,password,Grant_priv,Super_priv FROM mysql.user;`
`SELECT host,user,authentication_string,Grant_priv,Super_priv FROM mysql.user;`

> Then use code below
	UPDATE mysql.user SET Grant_priv='Y', Super_priv='Y' WHERE User='root';
	FLUSH PRIVILEGES;
	GRANT ALL ON *.* TO 'root'@'localhost';

#Specific priviliges
	GRANT ALL PRIVILEGES ON database.* TO 'user'@'localhost';

#See permissions
	SHOW GRANTS FOR CURRENT_USER;

#Setup root password
`mysqladmin -u root password -p 'pass'`

#Solve sudo issue on mysql
> Remove root and add back
	DROP USER 'root'@'localhost';
	CREATE USER 'root'@'%' IDENTIFIED BY '';
	GRANT ALL PRIVILEGES ON *.* TO 'root'@'%';
	FLUSH PRIVILEGES;
[link](https://askubuntu.com/questions/766334/cant-login-as-mysql-user-root-from-normal-user-account-in-ubuntu-16-04)

#Commands
SHOW DATABASES


#Java Related.
java.sql.SQLSyntaxErrorException: Table 'mydb.hibernate_sequence' doesn't exist
->	use @GeneratedValue(strategy = GenerationType.IDENTITY)
 instead of @GeneratedValue(strategy = GenerationType.AUTO)


#Starting MySQL
> ERROR! The server quit without updating PID file
	Try Uninstall & install


#Uninstalling with brew
`brew uninstall mysql`
`rm /usr/local/etc/my.cnf`
`rm -rf /usr/local/var/mysql`
> If necessary
`rm -rf /usr/local/Cellar/mysql@5.7`
`rm /etc/my.cnf`


