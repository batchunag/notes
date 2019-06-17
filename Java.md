Difference of HashMap vs Treemap vs LinkedHashMap
-----
Treemap: keys are sorted
http://www.programcreek.com/2013/03/hashmap-vs-treemap-vs-hashtable-vs-linkedhashmap/]

HashMap methods
http://www.programcreek.com/2013/04/frequently-used-methods-of-java-hashmap/

#Remember to
use JodaTime over TimeUnit etc.
--> Now, Java libraries like TimeUnit is more preffered over Joda.
check "){"

#String formatting
sb.append(String.format("%.3f\n",ans));

#注意comparator for long types
```code
return l1 -l2 --> doesn't work, should be like below
	if (l1>l2)
		return 1;
    if (l1<l2)
		return -1;
	return 0;
```

#Edit Java entity object as a hashmap (JSON)
https://www.leveluplunch.com/java/examples/convert-object-bean-properties-map-key-value/

```java
public void convert_object_to_map_jackson () {

    NoteBook moleskineNoteBook = new NoteBook(200, "Moleskine Notebooks");

    ObjectMapper objectMapper = new ObjectMapper();

    @SuppressWarnings("unchecked")
    Map<String, Object> objectAsMap = objectMapper.convertValue(moleskineNoteBook, Map.class);

    assertThat(objectAsMap, hasEntry("numberOfSheets", (Object) new Double(200.0)));
    assertThat(objectAsMap, hasEntry("description", (Object) "Moleskine Notebooks"));
}
```

#ArrayList initialization
ArrayList<String> cities = new ArrayList<>(Arrays.asList("London", "Tokyo", "New York"));
ArrayList<Integer> array = new ArrayList<Integer>(10);
> Although it's capacity is 10, it's size is still 0!.
List<Integer> list = new ArrayList<Integer>(Collections.nCopies(100, 0));


#String[] initialization
String[] myStringArray = new String[3];
String[] myStringArray = {"a","b","c"};
String[] myStringArray = new String[]{"a","b","c"};

#Array to list
Arrays.asList(myArr)

#New Immutable Empty list
ImmutableList.of()


#Immutable List to Immutable Set
final ImmutableSet<String> mySet = ImmutableSet.copyOf(myList);

#JSON conversion
import net.sf.json.JSONObject;
import net.sf.json.JSONArray;

final String data = request.getParameter("data");
final JSONObject resultMap = JSONObject.fromObject(data);

final JSONArray resultArray = resultMap.getJSONArray("items");
final String resultString = resultMap.getString("item");

#Jackson: Java Object to JSON
ObjectMapper mapper = new ObjectMapper();
requestWrapper.setBody(mapper.writeValueAsString(parameterMap);

#Value Immutable
    @Value.Immutable
    @JsonSerialize(as = Value.Immutable.class)
    @JsonDeserialize(as = Value.Immutable.class)
    public interface MapBody {
        Integer getUserId();
        String getUsername();
    }

#Http Servlet
Request content is read only-once. Request.getInputStream() becomes null.
So if we want to clone the request, we should use custom HttpServletRequestWrapper and clone the request before reading any content.

    private static class MyWrapper extends HttpServletRequestWrapper {

        private String body;

        MyWrapper(final HttpServletRequest request) {
            super(request);
        }

        public void setBody(final String body) {
            this.body = body;
        }

        @Override
        public BufferedReader getReader() {
            return new BufferedReader(new StringReader(body));
        }
    }
> Another way
    public class MultiReadHttpServletRequest extends HttpServletRequestWrapper{
        ...
    }

#More on HttpServletRequestWrapper
> https://stackoverflow.com/questions/44182370/why-do-we-wrap-httpservletrequest-the-api-provides-an-httpservletrequestwrappe
    private HttpServletRequest adjustParamDates(final HttpServletRequest req) {
      final Map<String, String[]> adjustedParams = reformatDates(req.getParameterMap());
      return new HttpServletRequestWrapper(req) {
        public String getParameter(String name) {
          return adjustedParams.get(name) == null ? null : adjustedParams.get(name)[0];
        }

        public Map<String, String[]> getParameterMap() {
          return adjustedParams;
        }

        public Enumeration<String> getParameterNames() {
          return Collections.enumeration(adjustedParams.keySet());
        }

        public String[] getParameterValues(String name) {
          return adjustedParams.get(name);
        }
      });
    }

#Servlet routing using getRequestDispatcher with additional parameters.
> Following also works.
    request.setAttribute("newParam", newParam); // in the first servlet before forwarding to the second
    request.getRequestDispatcher("/SecondServlet").forward(request, response);
    Retrieve the "attribute" in second servlet thru 
    String newParam = (String)request.getAttribute("newParam");    
> Forward POST to POST
    protected void doPost(HttpServletRequest request, HttpServletResponse response) {
        request.getRequestDispatcher("servlet2?foo=bar").forward(request, response);
    }
    protected void doPost(HttpServletRequest request, HttpServletResponse response) {
        String foo = request.getParameter("foo"); // Returns "bar".
    }

#Unit test
EasyMock
Expect -> Replay -> Verify

replayAll() -> verifyAll() -> resetAll()

(Following is better)
resetAll() -> replayAll() -> verifyAll()

```java
EasyMock.expect(returnFunction("woot", 5)).andReturn(123);
EasyMock.expect(returnFunction("fubar", 45)).andReturn(321);
voidFuntion("p");
EasyMock.expectLastCall();

public myTestClass extends EasyMockSupport {

}
```

For promise function:
final Promise<Void> voidPromise =  createMock(Promise.class);
expect(voidPromise.claim()).andReturn(null);

#Parameterized
> Required for the test class
    @RunWith(JUnitParamsRunner.class) 
    public class MyClassTest () {
        ..
    }
> parametersForTestMyMethod for the testMyMethod.
Or use @Parameters(method="mySpecialParameters")

```java
private List parametersForTestMyMethod() {
    return ImmutableList.of(
            new Object[] { 1, "Some String", "Expected"},
            new Object[] { 2, "Another String", "Expected value"}
    );
}

@Test
@Parameters
public void testMyMethod(final int id, final String value, final String expected) {
    assertEquals(expected, doSth(id, value));
}

```    


#Redirect
response.sendRedirect(internalUrl);
response.setHeader(externalUrl);

#Custom Header
request.getHeader("user-agent");

#Propertiy file reader
Juice

#Guava caching
```java
 private final Cache<String, ImmutableList<Integer>> KEY_IDS_CACHE = CacheBuilder.newBuilder()
            .expireAfterWrite(12, TimeUnit.HOURS)
            .build();

private ImmutableList<Integer> getIdsCache(final String key) {
        @Nullable final ImmutableList<String> cache = KEY_IDS_CACHE.getIfPresent(key);
        if (cache != null) {
            return cache;
        }
        synchronized (KEY_IDS_CACHE) {
            @Nullable final ImmutableList<String> cacheSecondTry = KEY_IDS_CACHE.getIfPresent(key);
            if (cacheSecondTry != null) {
                return cacheSecondTry;
            }

            final ImmutableList<Integer> idsList = getIds(key);
            KEY_IDS_CACHE.put(key, idsList);

            return idsList;
        }
    }
```

#Exceptions

 > Unchecked exception: defects in the program (bugs)
    RuntimeExceptions: IllegalArgumentException, NullPointerException, or IllegalStateException
>  Checked exception: invalid conditions in areas outside the immediate control of the program
     Exception:

We don't need *throws* for RuntimeException     

#Abstract class for Utility class
You could just declare a private constructor that does nothing.
"abstract" keyword usually means that class is *intended to be subclassed and extended*. That's definitely not what you want here.
More discussion: https://stackoverflow.com/questions/309553/should-helper-utility-classes-be-abstract

#Private constructor
> The use of private constructor is to serve singleton classes. 

#Static method: Method without needing of the object
> One rule-of-thumb: ask yourself "does it make sense to call this method, even if no Obj has been constructed yet?" If so, it should definitely be static.


#Java Classpath
https://docs.oracle.com/javase/8/docs/technotes/tools/findingclasses.html

#JPA Hibernate
Enum:  @Enumerated(EnumType.STRING) is requried above the field.

#Lombok
@AllArgsConstructor
GeneratedValue ID is also included in the constructor.
Only way is to use class inheritance.
https://stackoverflow.com/questions/48784923/is-using-id-field-in-allargsconstructor-while-using-spring-jpa-correct

#Read from file, map, stream

https://www.baeldung.com/java-serialization
https://www.baeldung.com/java-read-file

#NPE Null Point Exception for JPA Repository
@Autowired
MyRepo repo; //shouldn't have private static etc.

#CrudRepository vs JpaRepository
JpaRepository is just an extension of CrudRepository. 
So use CrudRepository when it's enough.

#Custom Query in CrudRepository
```java
@Repository
public interface MyRepository extends CrudRepository<Paper, Long> {
    @Query("SELECT p FROM Table p WHERE p.myColumn = :myValue")
    List<myColumn> findByValue(@Param("myValue") long myValue);
}
```

#REST
> PutMapping

```java
@PutMapping(path="/update")
public ResponseEntity<UserResponse> updateUser(@Valid @RequestBody User user) {
    return userRepository.save(user);
}
```

#lambda for optional, one line ifPresent.orElse
> Note that they have dedicated function for Java 9 and above.

```java
final Optional<MyClass> value = getSomeValue();
myMap.put("key", value.map(MyClass::methodReturnsDouble).orElse(0.0f));
```
> if value is empty -> return 0, or the value by the method.

#Terniary operator indendation
```java
result = (foo == bar) ? result1 :
         (foo == baz) ? result2 :
         (foo == xyz) ? result3 :
                        result4;
```