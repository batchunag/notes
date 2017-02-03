#Joining a subquery in ZEND
[link](http://stackoverflow.com/questions/4715718/how-can-i-join-a-subquery-using-zend-db-select)
```php
$user_multivalued = $db->select()
                      ->from('user_multivalued', array(
                         'user_id',
                         'field_id',
                         new Zend_Db_Expr("GROUP_CONCAT(value SEPARATOR ',') AS value"))),
                      ->where('field = ?', 25)
                      ->group('user_id')
                      ->group('field_id');      

$select = $db->select()
             ->from('users', array('user_id', 'email_address'))
             ->joinLeft(array('t1' => $user_multivalued),
                         't1.user_id = users.user_id',
                         array('languages'=>'value')
             )
             ->where('list_id = ?', 45);
```

#Adapter example
```php
$select = $this->_name->select()->setIntegrityCheck(false);
$select->from('table', array('col1','col2',))
->where('kw1 = ?', $kw)
->where('time > -8')
->where('time < 7')
->order(array('time ASC', 'count DESC'));
$row = $this->_d_dmp_ctg_master->fetchAll($select);
```



#Getting a SUM in query
$select = $db->select()
    ->from('mytable', array('sum1' => 'SUM(`col1`)', 'sum2' => 'SUM(col2)')
    ->group('year');

#Routing
No routing is necessary
We can add controller directly.
Troubleshooting--> Check logs, check compile errors

#Add another db
Add to config.ini

#Uncaught exception 'Zend_Session_Exception' with message 'Session must be started before any output has been sent to the browser; output started

-> Check unnecessary empty lines at the head or bottom. (No ?> is necessary)

