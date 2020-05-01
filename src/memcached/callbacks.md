Callbacks
=========

**Table of Contents**

-   [Result callbacks](/memcached/callbacks.html#Result%20callbacks)
-   [Read-through cache
    callbacks](/memcached/callbacks.html#Read-through%20cache%20callbacks)

Result callbacks
----------------

Result <span class="type">callbacks</span> are invoked by <span
class="methodname">Memcached::getDelayed</span> or <span
class="methodname">Memcached::getDelayedBykey</span> methods for each
item in the result set. The callback is passed the Memcached object and
the array with the item information. The callback does not have to
return anything.

**Example \#1 Result callback example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);
$items = array(
    'key1' => 'value1',
    'key2' => 'value2',
    'key3' => 'value3'
);
$m->setMulti($items);
$m->getDelayed(array('key1', 'key3'), true, 'result_cb');

function result_cb($memc, $item)
{
    var_dump($item);
}
?>
```

The above example will output something similar to:

    array(3) {
      ["key"]=>
      string(4) "key1"
      ["value"]=>
      string(6) "value1"
      ["cas"]=>
      float(49)
    }
    array(3) {
      ["key"]=>
      string(4) "key3"
      ["value"]=>
      string(6) "value3"
      ["cas"]=>
      float(50)
    }

Read-through cache callbacks
----------------------------

Read-through cache callbacks are invoked when an item cannot be
retrieved from the server. The callback is passed the Memcached object,
the requested key, and the by-reference value variable. The callback is
responsible for setting the value and returning true or false. If the
callback returns true, Memcached will store the populated value on the
server and return it to the original calling function. Only <span
class="methodname">Memcached::get</span> and <span
class="methodname">Memcached::getByKey</span> support these callbacks,
because the memcache protocol does not provide information on which keys
were not found in the multi-key request.

**Example \#1 Read-through callback example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$profile_info = $m->get('user:'.$user_id, 'user_info_cb');

function user_info_cb($memc, $key, &$value)
{
    $user_id = substr($key, 5);
    /* lookup profile info in the DB */
    /* ... */
    $value = $profile_info;
    return true;
}
?>
```
