POST and GET
----
```javascript
var data = {'slat':1.02,
             'slong': 1.29}

 $.ajax({
            type : "POST",
            url : "/api/location",
            data: JSON.stringify(data),
            contentType: 'application/json;charset=UTF-8',
            success: function(result) {
                console.log(result);
            }, 
            error: function(result) {
                console.log(result);
            }
        });
```
async is useful for global variable.

```javascript
$.ajax({
	        type : "GET",
	        async: false,
            url : "/api/location",
	        // timeout: 1000, 
	        success: function(result) {
	 			slat = result.slat;
	 			slong = result.slong;

	        }
	    });
```