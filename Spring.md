#Spring with Vue
https://blog.codecentric.de/en/2018/04/spring-boot-vuejs/
https://github.com/jonashackt/spring-boot-vuejs
https://www.baeldung.com/spring-boot-vue-js
https://spring.io/guides/gs/spring-boot/

#Login System
https://www.baeldung.com/registration-with-spring-mvc-and-spring-security

#Chatbot
https://github.com/kingbbode/spring-boot-chatbot

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
