#Difference between GAE and GCE etc.
https://stackoverflow.com/questions/22697049/what-is-the-difference-between-google-app-engine-and-google-compute-engine

#POM plugin
<plugin>
	<groupId>com.google.cloud.tools</groupId>
	<artifactId>appengine-maven-plugin</artifactId>
	<version>1.3.2</version>
	<configuration>
	</configuration>
</plugin>

#GCP
spring.cloud.gcp.sql.instance-connection-name=
spring.cloud.gcp.sql.database-name=
# Cloud SQL (MySQL) only supports InnoDB, not MyISAM
spring.jpa.database-platform=org.hibernate.dialect.MySQL55Dialect
spring.datasource.user=
spring.datasource.password=

spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

#Packaging 
jar -> Flexible environment
war -> Standart environment