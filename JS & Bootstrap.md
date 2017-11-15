Javascript Tutorial
----
<http://learnxinyminutes.com/docs/javascript/>  
<http://bonsaiden.github.io/JavaScript-Garden>  
<https://www.learneroo.com/modules/64/nodes/350>  

Bootstrap
-----
Components: <http://getbootstrap.com/components>  

Timeline
<http://blog.templatemonster.com/2014/04/23/tutorial-build-vertical-timeline-archives-page-using-bootstrap/>  
<http://bootsnipp.com/snippets/featured/timeline-responsive>  
<http://ironsummitmedia.github.io/startbootstrap-agency/>  

Anchor scrolling  
<http://ironsummitmedia.github.io/startbootstrap-grayscale/>



HTML
----

```html
<p><button id="scroll">scrollLeft()</button></p>
<div id="test"></div>
```
CSS

```css
#test {
    width: 100px;
    height: 100px;
    background: green;
    position: relative;
    left: 1000px;
}
```
JS

```js
$('#scroll').click(function() {
    $('html,body').animate({
        scrollLeft: $('#test').css('left')
    }, 800, function() {

        $('html, body').animate({
            scrollLeft: 0
        }, 800);

    });
});
```

Another example

```js
$(document).ready(function(){
    $("button").click(function(){
      $('div').animate(
             { scrollLeft: '+=50' }, 1000);
    });
});
```

[Page slider](http://alvarotrigo.com/fullPage/#3rdPage)

[Geographical distance](http://www.geodatasource.com/developers/javascript)

#Cool way to create element
http://stackoverflow.com/questions/10619445/the-prefered-way-of-creating-a-new-element-with-jquery

```javascript
$div = $("<div>", {class: "col-xs-6"})
        .html($("<img>", {class: "img-responsive", src:"static/img/dad.png", style: "width: 100%;"}));
```
#async function

```javascript
function superPower(a, b) {
    var m = Math.pow(10,8);
    
    function p(w,n,call){
        if (n==0) {
            //call();
            return 1;
        }
        var x = p(w,Math.floor(n/2), call);
//        console.log(w + " ^ " + Math.floor(n/2) + " = "+ x);
        var r = Math.floor(Math.sqrt(x));
        var t = x -r*r;
        var x = ((x*r%m)*r%m+x*t)%m;
        if (n%2==1)
            x = x*w%m;
        return x;
    }
    
    var q = {};
    var z = 1;
    var c = 0;
    while(c<b){
        //console.log(z);
        var zz = z;
        if (!(z in q))
            q[zz] = p(a,z, function(){exit();});
        z = q[zz];
        c+=1;
    }
    return z;
}
```


#Debug
debugger;

#Array append
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
// Append all items from arr2 onto arr1
Array.prototype.push.apply(arr1, arr2);
or arr1.concat(arr2);


#Class intersection: just write the selectors together without spaces in between.

$('.a.b')
So for an element that has an ID of a with classes b and c, you would write:

$('#a.b.c')

#date formatting double digit

("0" + this.getDate()).slice(-2)
("0" + (this.getMonth() + 1)).slice(-2)

#Get date today
var today = new Date().toJSON().slice(0,10);

#Drap&Drop for file upload
https://www.sitepoint.com/html5-file-drag-and-drop/
https://jsfiddle.net/oL2akhtz/

#Charting and graph visualization
http://thenextweb.com/dd/2015/06/12/20-best-javascript-chart-libraries/
Libraries like FusionCharts, GoogleCharts, Dygraphs or one of the D3 derivatives may work best for corporations with large data sets, or small businesses that rely heavily on data analysis. If you just need something small and quick, Morris.js or Chart.js might work better for you. For graphs and networks, Cytoscape or Sigma.js is probably the way to go.

#DOM traversing without jQuery
https://www.w3.org/wiki/Traversing_the_DOM