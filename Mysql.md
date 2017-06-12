#user authentication or login
Since 5.7? password column was changed to authentication_string

#Grant privileges for root and other users
`SELECT host,user,password,Grant_priv,Super_priv FROM mysql.user;`

> Then use code below
	UPDATE mysql.user SET Grant_priv='Y', Super_priv='Y' WHERE User='root';
	FLUSH PRIVILEGES;
	GRANT ALL ON *.* TO 'root'@'localhost';

#Setup root password
`mysqladmin -u root password -p 'pass'`

#Solve sudo issue on mysql
> Remove root and add back
	DROP USER 'root'@'localhost';
	CREATE USER 'root'@'%' IDENTIFIED BY '';
	GRANT ALL PRIVILEGES ON *.* TO 'root'@'%';
	FLUSH PRIVILEGES;
[link](https://askubuntu.com/questions/766334/cant-login-as-mysql-user-root-from-normal-user-account-in-ubuntu-16-04)
