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