#Guzzle Client
```php
$client = new Client('http://mysite');
$request = $client->get('/getTest?number=123');
$request->setAuth('user', '');
$resp = $request->send();
$body =  $resp->getBody();
$json =  $resp->json();

$clientp = new Client('http://mysite');
$request = $clientp->post('/postTest', null, array('number' => 123));
$request->setAuth('user', '');
$resp = $request->send();
$body =  $resp->getBody();
$json =  $resp->json();
```




