#Java
> java.lang.IllegalStateException: Failed to load ApplicationContext
	Caused by: com.coxautodev.graphql.tools.FieldResolverError: No method or field found with any of the following signatures 
		graphql.Query.findAllAuthors()
		graphql.Query.getFindAllAuthors()
		graphql.Query.findAllAuthors

Needs the .graphqls file.
https://github.com/eugenp/tutorials/tree/master/spring-boot/src/main/resources/graphql

#Improvements with Intellij
> Schema 
https://qiita.com/ryo2132/items/b9bad0e1be756337482e
https://www.prisma.io/blog/new-tooling-to-improve-your-graphql-workflows-7240c81e1ba3


#Example
https://github.com/spring-petclinic/spring-petclinic-graphql/blob/master/backend/src/main/java/org/springframework/samples/petclinic/repository/PetRepository.java

https://dev.to/sambenskin/howto-integrate-a-mysql-database-into-your-java-spring-boot-graphql-service-26c

#Using Mysql
We don't need Dao for mysql

We need one class, (its' resolver???) and Query.
```java
@Entity
@Table(name="mydatas")
public class Mydata {
    ..

}

????
public class MydataResolver implements GraphQLResolver<Mydata> {

}

public class Query implements GraphQLQueryResolver{
    ...
}
```


Graphql Java files.
https://github.com/eugenp/tutorials/tree/master/spring-boot/src/main/java/com/baeldung/graphql
> Example: Author, AuthorDao, AuthorResolver
	Author: Define the class
	AuthorDao: Uses to filter Author
	AuthorResolver: Relationships?
```java
public class Author {
    private String id;
    private String name;
    private String thumbnail;

    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getThumbnail() {
        return thumbnail;
    }

    public void setThumbnail(String thumbnail) {
        this.thumbnail = thumbnail;
    }
}

public class AuthorDao {
    private List<Author> authors;

    public AuthorDao(List<Author> authors) {
        this.authors = authors;
    }

    public Optional<Author> getAuthor(String id) {
        return authors.stream().filter(author -> id.equals(author.getId())).findFirst();
    }
}


public class AuthorResolver implements GraphQLResolver<Author> {
    private PostDao postDao;

    public AuthorResolver(PostDao postDao) {
        this.postDao = postDao;
    }

    public List<Post> getPosts(Author author) {
        return postDao.getAuthorPosts(author.getId());
    }
}
```

Tutorials
> Follow https://www.baeldung.com/spring-graphql
	with github code.
> Additional 
https://www.pluralsight.com/guides/building-a-graphql-server-with-spring-boot	


