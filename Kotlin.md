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