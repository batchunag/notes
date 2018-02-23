#Add inheritance
<inherits name="com.google.gwt.json.JSON" />
<inherits name="com.google.gwt.something.Something" />

#JSON
```java
String jsonString = "{'map': [{'char':'a', 'words': ['alpha', 'adam']}, {'char':'b', 'words': ['beta', 'ben']}]}";
final ListBox listBox = new ListBox();
JSONObject jsonObject = JSONParser.parse(jsonString).isObject();
JSONArray jsonArray = jsonObject.get("map").isArray();
for (int i = 0; i< jsonArray.size(); i++) {
  JSONObject item = jsonArray.get(i).isObject();
  listBox.addItem(item.get("char").toString());
  JSONArray words = item.get("words").isArray();
  for (int j = 0; j< words.size(); j++) {
        String word = words.get(j).toString();
        listBox.addItem("*** " + word);
      }
}
```

#Iteration with casting
for (int i = 0; i< grid.getRowCount(); i++) {
	final Widget widget = grid.getWidget(i, 0);
    try {
        final Label button = (Label) ((VerticalPanel) widget).getWidget(0);
        Window.alert(button.getText());
    } catch (ClassCastException exception) {
        continue;
	}
}

#List<String> to JSONArray
final JSONArray jArray = new JSONArray();
for (int i = 1; i< myList.size()+1; i++){
    jArray.set(i, new JSONString(myList.get(i)));
}