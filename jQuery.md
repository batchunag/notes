
#input live update
https://gist.github.com/brandonaaskov/1596867

#IME Enter not submit form
Use keydown instead of keyup
http://stackoverflow.com/questions/22705698/distinguishing-between-enter-keypress-for-japanese-kanji-suggestion-and-other

#Do not make AJAX synchronous
http://stackoverflow.com/questions/14220321/how-to-return-the-response-from-an-asynchronous-call

#Select ID with semicolon
$('#test\\:abc')

#Creating jQuery object


```javascript
var div = $("<div></div>");
$("#box").append(div);

$("#box").append("<div></div>");

var $div = $("<div>", {id: "foo", class: "a"});
$div.click(function(){ /* ... */ });
$("#box").append($div);
```

#jQuery injection
var script = document.createElement('script');script.src = "https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js";document.getElementsByTagName('head')[0].appendChild(script);

