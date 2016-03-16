#reverse proxy

<VirtualHost *:80>
    ServerName alpha.com
    ProxyPreserveHost On

    # Servers to proxy the connection, or;


  1 <VirtualHost *:80>
    # List of application servers:
    # Usage:
    # ProxyPass / http://[IP Addr.]:[port]/
    # ProxyPassReverse / http://[IP Addr.]:[port]/
    # Example:
    ProxyPass / http://0.0.0.0:5601/
    ProxyPassReverse / http://0.0.0.0:5601/


  1 <VirtualHost *:80>

    CustomLog "/var/log/mylog.log.%Y%m%d 86400 540" combined
    ErrorLog "/var/log/myError.log.%Y%m%d 86400 540"

    <Directory "/var/www/html/public">
      Options FollowSymLinks Includes ExecCGI
      AllowOverride All
      Require all granted
    </Directory>

</VirtualHost>


#Apache body size limit, query size

https://httpd.apache.org/docs/2.2/ja/mod/core.html#limitrequestbody