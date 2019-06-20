#Painless Spring boot tutorial with Maven Kotlin & MongoDB
https://medium.com/mariano-z-lopez/painless-spring-boot-tutorial-with-maven-kotlin-mongodb-18c11a08aaae


#Building a REST Service with Kotlin, Spring Boot, MongoDB, and JUnit
https://medium.com/@rhwolniewicz/building-a-rest-service-with-kotlin-spring-boot-mongodb-and-junit-14d10faa594b

#Spring-boot-kotlin-and-mongodb
https://www.novatec-gmbh.de/en/blog/how-to-web-application-with-spring-boot-kotlin-and-mongodb/
It usually works, but fails with jackson-module-kotlin.

#Spring Kotlin tutorial
https://spring.io/guides/tutorials/spring-boot-kotlin/

#Good lambdas
```java
val someList = myList
        .ifEmpty { listOf(mapOf()) }
        .mapNotNull { 
        	if (a) {
        		list1
        	} else {
        		null
        	}
    }
```            

#Using @Document 

```java
import org.springframework.data.mongodb.core.mapping.Document
import java.time.LocalDate

@Document data class Author(@Id val id:String? = null, val name:String, val birthDate:LocalDate)
```

#Unit Test
Mockk
https://blog.kotlin-academy.com/mocking-is-not-rocket-science-expected-behavior-and-behavior-verification-3862dd0e0f03

#Initializer
val mutableList = mutableListOf<Int>()
val mutableList : MutableList<Int> = ArrayList()
val mutableList : MutableList<Int> = arrayListOf()

#Stream usage compared to Java
https://stackoverflow.com/questions/34642254/what-java-8-stream-collect-equivalents-are-available-in-the-standard-kotlin-libr
