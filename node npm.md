node npm
=========

fs: to save file into disk
------------

> Usage:
```javascript
	fs.writeFile('page1.html', "hEllo", function (err) {
		if (err) return console.log(err);
		console.log('Hello World > page1.html');
	});
```

request: send http request
---------------------
Usage: 
```javascript
	var request = require('request');
	request('http://www.amazon.co.jp', function (error, response, body) {
		do sth with body.
	});
```


cheerio: using jquery-like commands with html file
---------------------
https://github.com/cheeriojs/cheerio

```javascript
var cheerio = require('cheerio');
```

Async: asynchronous executions
---------------------
Javascript хэлэнд зарим үйлдлүүд эхэлж хийгддэг. С хэл шиг дээрээсээ доош маягаар явдаггүй.
drain: дарааллаас хамгийн сүүлийн элемент гарах үед дуудагдана.
push: ашиглаж дараалалд оруулна.

 
Доорх жишээнд давхар async хэрэглэсэн байгаа.


```javascript
	async = require('async');
	var q = async.queue(function (task, done) {
	    request(task.url, function (err, res, body) {
	      if (err) return done(err);
	      if (res.statusCode != 200) return done(res.statusCode);
	      var $ = cheerio.load(body);
	      $('div.s-item-container').each(function(i, element){
	        var text = $(this).children().eq(1).children().eq(0).children();//.prev();
	        var a = $(text).eq(0);
	        var url = a.attr('href');
	        URLs.push({url : url});
	       // console.log(url);
	      });
	      done();
	    });
	}, 1);

	q.drain = function (){
	  //console.log("Q drained");
	  URLs.drain = function(){
	   // console.log(aa);
	    //console.log("URL drain");
	    fs.writeFile('URL.text', aa, function (err) {
	      if (err) return console.log(err);
	      //console.log('URLs written');
	    });
	  }
	}

	var URLs = async.queue (function(task, done){
	    aa = aa + task.url + "\n";
	    done();
	 },5);

	for (var i = 2; i <401; i++) {
	    var pageUrl = 'http://www.amazon.co.jp/s/ref=lp_2221092051_pg_' + i + '?rh=n%3A2016926051%2Cn%3A%212016927051%2Cn%3A2221080051%2Cn%3A2221071051%2Cn%3A2221092051&page='+ i + '&ie=UTF8&qid=1428079949';
	    //console.log(pageUrl);
	    q.push({url : pageUrl});
	}
```

`out = fs.createWriteStream("file.txt")` гэж ашиглаж байгаа үед end функцийг дуудна.
`out.end()`

for loop нь synchronous бөгөөд async болгохын тулд `async.times` ашиглана. Жишээ:

```javascript

async.times(n,
    	function(i, next){
    		reader.nextLine(function(url){
			    console.log(url);
				next();//?
			})
		}, 
		function(err, result) {
		    console.log("Error: " + err);	
		});

```

`async.series`
`async.whilst`
 ашигласан

More:  https://github.com/caolan/async#queue




Esprima and Estraverse: Handling Javascript files, JSON, traversing
---------------------
> Usage:
Доорх жишээ html файлаас script буюу JS хэсгийг нь тус бүрт нь анализ хийж hiRes гэсэн утгатай элементийг авч байна.

```javascript
//GetImageFromPage.js

var esprima = require('esprima');
var estraverse = require('estraverse');
var nImages = 0;
var Images = [];

$('script').each(function(i, element){
		var js = $(this).text();
		var ast = esprima.parse(js);
		estraverse.traverse(ast, {
			enter: function(node, parent){
	    		if (node.value === 'colorImages' ){
	    			found = true;
		    	} else
	    		if (node.value === 'hiRes'){
	    			//console.log(parent.value.value);
	    			Images[nImages] = parent.value.value;
	    			nImages++;
			  		// fs.writeFile('41-1784.json', JSON.stringify(esprima.parse(js), null, 10), function (err) {
				 //      if (err) return console.log(err);
				 //      //console.log('URLs written');
				 //    });
				}
			},
	  	});
```

$ npm list
---------------------
...
npm ERR! extraneous: cheerio@0.13.1

特に支障はないのだが、気持ち悪いので以下で直す。


$ vi package.json
   ...
  "dependencies": {
    ...
    "cheerio": "~0.13.1",  これを追加

その後、
$ npm list 
として、エラーが出なくなった。

npm install -g markmon
Markdown preview depends on node js



#global variables

http://blog.mixu.net/2011/02/03/javascript-node-js-and-for-loops/



jQuery
---------------------

http://api.jquery.com/category/traversing/

JS хэлэнд === тэнцүү эсэхийг шалгана.
Selector vs Traversing
$(element).[first children attr nth-child(2) each next prev ]() гэх мэт.
children бол дараа нь eq(i) ашиглан i дугаар хүүхдийг сонгоно.



	var review = $('#averageCustomerReviews').first();
    var star;
    review = $(review).children().eq(0); //a or span
    //console.log(review.attr("id"));
    if (review.attr("id")==='acrCustomerWriteReviewLink') {
    	star = "NA";
    } else{
     	star = $(review).attr( "title" );
    }


ar-drone
---------------

https://github.com/felixge/node-ar-drone
http://www.instructables.com/id/Autonomous-AR-Parrot-Drone-20-Flying/step7/Functions/
http://www.nodecopter.com/organize
http://hackaday.com/2012/08/23/extending-the-range-of-the-ar-drone-2-ways/

pebble
--------
https://github.com/skota121/Pebble-Watch-Parrot-Drone-Controller/blob/master/Pebble%20Watch%20Code

node-red
--------

Multiple input: Use context
 http://flows.nodered.org/flow/8ba7f90f3ea8d92b1e01


Google Map using Web socket
	http://flows.nodered.org/flow/d7a45e7e693f43c9d47b
	http://ryanjbaxter.com/2015/01/13/sample-node-red-flow-using-websockets/


io.socket
-------

How routing works?
Get..
CreateServer, listen などの使用
emit, volatile emit
emission from client.
