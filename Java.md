Difference of HashMap vs Treemap vs LinkedHashMap
-----
Treemap: keys are sorted

http://www.programcreek.com/2013/03/hashmap-vs-treemap-vs-hashtable-vs-linkedhashmap/]

HashMap methods
http://www.programcreek.com/2013/04/frequently-used-methods-of-java-hashmap/

#String formatting
sb.append(String.format("%.3f\n",ans));

#注意comparator for long types
return l1 -l2 --> doesn't work, should be like below
	if (l1>l2)
		return 1;
	if (l1<l2)
		return -1;
	return 0;

#Edit Java entity object as a hashmap (JSON)
https://www.leveluplunch.com/java/examples/convert-object-bean-properties-map-key-value/
public void convert_object_to_map_jackson () {

    NoteBook moleskineNoteBook = new NoteBook(200, "Moleskine Notebooks");

    ObjectMapper objectMapper = new ObjectMapper();

    @SuppressWarnings("unchecked")
    Map<String, Object> objectAsMap = objectMapper.convertValue(moleskineNoteBook, Map.class);

    assertThat(objectAsMap, hasEntry("numberOfSheets", (Object) new Double(200.0)));
    assertThat(objectAsMap, hasEntry("description", (Object) "Moleskine Notebooks"));
}