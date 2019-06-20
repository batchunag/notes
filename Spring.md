#Spring with Vue
https://blog.codecentric.de/en/2018/04/spring-boot-vuejs/
https://github.com/jonashackt/spring-boot-vuejs
https://www.baeldung.com/spring-boot-vue-js
https://spring.io/guides/gs/spring-boot/

#Login System
https://www.baeldung.com/registration-with-spring-mvc-and-spring-security
Code based
https://medium.com/@hantsy/protect-rest-apis-with-spring-security-and-jwt-5fbc90305cc5
https://github.com/hantsy/springboot-jwt-sample/blob/master/src/main/java/com/example/demo/domain/User.java

> To Implement/Customize UserDetailsService
https://www.logicbig.com/tutorials/spring-framework/spring-security/user-details-service.html

#Chatbot
https://github.com/kingbbode/spring-boot-chatbot

#Configuration Vs Component.
http://dimafeng.com/2015/08/29/spring-configuration_vs_component/
Place them with same or below package when @SpringBootApplication class is located.
https://www.concretepage.com/spring-boot/spring-boot-crudrepository-example

#Maven
junit dependency error
--> Check scope.

#Mysql - hibernate
Class Employee {
   private String firstName;
   private String lastName; 
}

will become `select employee0_.first_name,employee0_last_name from employee employee0_;` in sql by default.

using 
`spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl` in application.properties, will help get
`select employee0_.firstName,employee0_lastName from Employee employee0_;`


Database configuration
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#howto-two-datasources
> Use 2: One for local dev(in memory), one for prod (mysql etc.)
	--> Use h2 for dev, use another properties in prod.

H2 only
https://dzone.com/articles/spring-boot-and-spring-jdbc-with-h2
More: http://www.springboottutorial.com/spring-boot-and-h2-in-memory-database
	Detailed: https://www.baeldung.com/spring-boot-data-sql-and-schema-sql




#Graphql configuration.
https://stackoverflow.com/questions/45959234/authentication-in-spring-boot-using-graphql


#Reading application.properties in Spring Boot
http://appsdeveloperblog.com/reading-application-properties-spring-boot/
> Three ways
	~ Read application.properties using Environment object, 
	~ Read a property from application.properties file using @ConfigurationProperties
	~and reading a property using the @Value annotation.

#Bean & Autowired
https://stackoverflow.com/questions/34172888/difference-between-bean-and-autowired	

# Missing Bean.
 > Unable to start ServletWebServerApplicationContext due to missing ServletWebServerFactory bean

#Tutorials
Upload file
	Spring tutorial: https://spring.io/guides/gs/uploading-files/#initial
	GCP tutorial: https://codelabs.developers.google.com/codelabs/spring-cloud-gcp-gcs/

#Spring MVC NoSuchMethodError 500
Check the mvc versions.
Removing javax.servlet version helped.
```xml
<artifactId>javax.servlet-api</artifactId>
<!-- <version>3.1.0</version> -->
```            

#Context path
https://qiita.com/kazuki43zoo/items/e12a72d4ac4de418ee37

#Compressing Resources/API
server.compression.enabled=true
server.compression.mime-types=application/json,application/xml,text/html,text/xml,text/plain,application/javascript,text/css
server.compression.min-response-size=1024
More https://www.callicoder.com/configuring-spring-boot-application/

#Gzip for Embedded Container vs External Container
https://www.javainuse.com/spring/boot-zip
Couldn't confirm the compression through Postman, but Chrome inspector tool works.

#HTTP client & Feign
Having (implementing) feign client, makes it easier to use APIs from another project by just importing.
I.e, another project(client) will just import that (feign)client and use it.

#Caching
https://qiita.com/yut_arrows/items/4b664acdfa852c0bd6cd
spring.cache.cache-names=cache1,cache2
spring.cache.caffeine.spec=maximumSize=500,expireAfterAccess=600s
https://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-caching.html

Only with Spring (needs @EnableScheduling and @EnableCaching)

```java
@Scheduled(fixedRate = ONE_DAY)
@CacheEvict(value = { CACHE_NAME })
public void clearCache() {      
}
```

#Encoding issue specially with gcloud
spring.http.encoding.force=true

More: check the Response Header.


#Document in gradle.
compile("org.springframework.boot:spring-boot-starter-data-mongodb")

