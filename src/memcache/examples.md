Examples
========

**Table of Contents**

-   [Basic usage](/memcache/examples.html#Basic%20usage)

Basic usage
-----------

**Example \#1 memcache extension overview example**

In this example, an object is being saved in the cache and then
retrieved back. Object and other non-scalar types are serialized before
saving, so it's impossible to store resources (i.e. connection
identifiers and others) in the cache.

``` php
<?php

$memcache = new Memcache;
$memcache->connect('localhost', 11211) or die ("Could not connect");

$version = $memcache->getVersion();
echo "Server's version: ".$version."<br/>\n";

$tmp_object = new stdClass;
$tmp_object->str_attr = 'test';
$tmp_object->int_attr = 123;

$memcache->set('key', $tmp_object, false, 10) or die ("Failed to save data at the server");
echo "Store data in the cache (data will expire in 10 seconds)<br/>\n";

$get_result = $memcache->get('key');
echo "Data from the cache:<br/>\n";

var_dump($get_result);

?>
```

**Example \#2 Using memcache session handler**

``` php
<?php

$session_save_path = "tcp://$host:$port?persistent=1&weight=2&timeout=2&retry_interval=10,  ,tcp://$host:$port  ";
ini_set('session.save_handler', 'memcache');
ini_set('session.save_path', $session_save_path);

?>
```
