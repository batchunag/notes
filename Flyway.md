#Connect using url
flyway -user=$(whoami) -password= -url=jdbc:mysql://127.0.0.1:3306/db

flyway info

flyway migrate

flyway repair

> Unable to instantiate JDBC driver:
	Update dependency as here: https://github.com/flyway/flyway/issues/1923
	spring-jdbc, mysql-connector-java are required.
>  Factory method 'flyway' threw exception; nested exception is java.lang.IllegalStateException: Cannot find migrations location in: [classpath:db/migration]
	put `spring.flyway.locations=classpath:db/mysql/migrations` in application.properties.
	put the db/mysql/migrations under src/main/resources

> SELECT command denied to user ... for table 'user_variables_by_thread'	
	Flyway version 5.2.3 has bug. -> Revert to 5.2.1

>  org.flywaydb.core.api.FlywayException: Unable to connect to the database. Configure the url, user and password!	
	Maven tool from Intellij works.

com.mysql.jdbc.Driver is updated to com.mysql.cj.jdbc.Driver

> (using password: NO) Error Code : 1045
	Couldn't resolve.

> config: following works.(only in maven. i.e. pom.xml)
 mvn flyway:migrate -Dflyway.configFile=./src/main/resources/flyway.properties
 	Maven plugin is necessary: https://flywaydb.org/documentation/maven/#goals


> ERROR:
Unable to obtain Jdbc connection from DataSource (jdbc:mysql://localhost:3306/mydb?serverTimezone=UTC) for user 'user': Could not connect to localhost:3306: unexpected end of stream, read 0 bytes from 4

--> Due to different mysql version.