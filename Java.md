Difference of HashMap vs Treemap vs LinkedHashMap
-----
Treemap: keys are sorted

http://www.programcreek.com/2013/03/hashmap-vs-treemap-vs-hashtable-vs-linkedhashmap/]

HashMap methods
http://www.programcreek.com/2013/04/frequently-used-methods-of-java-hashmap/

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

#String[] initialization
String[] myStringArray = new String[3];
String[] myStringArray = {"a","b","c"};
String[] myStringArray = new String[]{"a","b","c"};

#Array to list
Arrays.asList(myArr)

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

