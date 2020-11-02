Yet Another RPC Framework
=========================

**Table of Contents**

-   [Introduction](/intro/yar.html)
-   [Installing/Configuring](/yar/setup.html)
    -   [Requirements](/yar/setup.html#Requirements)
    -   [Installation](/yar/setup.html#Installation)
    -   [Runtime Configuration](/yar/setup.html#Runtime%20Configuration)
    -   [Resource Types](/yar/setup.html#Resource%20Types)
-   [Predefined Constants](/yar/constants.html)
-   [Examples](/yar/examples.html)
-   [Yar\_Server](/class/yar-server.html) — The Yar\_Server class
    -   [Yar\_Server::\_\_construct](/class/yar-server.html#Yar_Server::__construct)
        — Register a server
    -   [Yar\_Server::handle](/class/yar-server.html#Yar_Server::handle)
        — Start RPC Server
-   [Yar\_Client](/class/yar-client.html) — The Yar\_Client class
    -   [Yar\_Client::\_\_call](/class/yar-client.html#Yar_Client::__call)
        — Call service
    -   [Yar\_Client::\_\_construct](/class/yar-client.html#Yar_Client::__construct)
        — Create a client
    -   [Yar\_Client::setOpt](/class/yar-client.html#Yar_Client::setOpt)
        — Set calling contexts
-   [Yar\_Concurrent\_Client](/class/yar-concurrent-client.html) — The
    Yar\_Concurrent\_Client class
    -   [Yar\_Concurrent\_Client::call](/class/yar-concurrent-client.html#Yar_Concurrent_Client::call)
        — Register a concurrent call
    -   [Yar\_Concurrent\_Client::loop](/class/yar-concurrent-client.html#Yar_Concurrent_Client::loop)
        — Send all calls
    -   [Yar\_Concurrent\_Client::reset](/class/yar-concurrent-client.html#Yar_Concurrent_Client::reset)
        — Clean all registered calls
-   [Yar\_Server\_Exception](/class/yar-server-exception.html) — The
    Yar\_Server\_Exception class
    -   [Yar\_Server\_Exception::getType](/class/yar-server-exception.html#Yar_Server_Exception::getType)
        — Retrieve exception's type
-   [Yar\_Client\_Exception](/class/yar-client-exception.html) — The
    Yar\_Client\_Exception class
    -   [Yar\_Client\_Exception::getType](/class/yar-client-exception.html#Yar_Client_Exception::getType)
        — Retrieve exception's type

Introduction
------------

Class synopsis
--------------

**Yar\_Server**

<span class="ooclass"> class **Yar\_Server** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_executor` ;

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">Object</span> `$obj`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">handle</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`_executor`  

Yar\_Server::\_\_construct
==========================

Register a server

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">Yar\_Server::\_\_construct</span> ( <span
class="methodparam"><span class="type">Object</span> `$obj`</span> )

Set up a Yar HTTP RPC Server, All the public methods of $obj will be
register as a RPC service.

### Parameters

`obj`  
An Object, all public methods of its will be registered as RPC services.

### Return Values

An instance of <span class="classname">Yar\_Server</span>.

### Examples

**Example \#1 <span class="function">Yar\_Server::\_\_construct</span>
example**

``` php
<?php
class API {
    /**
     * the doc info will be generated automatically into service info page.
     * @params 
     * @return
     */
    public function some_method($parameter, $option = "foo") {
         return "some_method";
    }

    protected function client_can_not_see() {
    }
}

$service = new Yar_Server(new API());
$service->handle();
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Server::handle</span>

Yar\_Server::handle
===================

Start RPC Server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yar\_Server::handle</span> ( <span
class="methodparam">void</span> )

Start a RPC HTTP server, and ready for accpet RPC requests.

> **Note**:
>
> Usual RPC calls will be issued as HTTP POST requests. If a HTTP GET
> request is issued to the uri, the service information (commented
> section above) will be printed on the page

### Parameters

This function has no parameters.

### Return Values

boolean

### Examples

**Example \#1 <span class="function">Yar\_Server::handle</span>
example**

``` php
<?php
class API {
    /**
     * the doc info will be generated automatically into service info page.
     * @params 
     * @return
     */
    public function some_method($parameter, $option = "foo") {
    }

    protected function client_can_not_see() {
    }
}

$service = new Yar_Server(new API());
$service->handle();
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Server::\_\_construct</span>

Introduction
------------

Class synopsis
--------------

**Yar\_Client**

<span class="ooclass"> class **Yar\_Client** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_protocol` ;

<span class="modifier">protected</span> `$_uri` ;

<span class="modifier">protected</span> `$_options` ;

<span class="modifier">protected</span> `$_running` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_call</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span> ,
<span class="methodparam"><span class="type">array</span>
`$parameters`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">Yar\_Client</span><span class="type">false</span></span>
<span class="methodname">setOpt</span> ( <span class="methodparam"><span
class="type">int</span> `$name`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

}

Properties
----------

`_protocol`  

`_uri`  

`_options`  

`_running`  

Yar\_Client::\_\_call
=====================

Call service

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Yar\_Client::\_\_call</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span> ,
<span class="methodparam"><span class="type">array</span>
`$parameters`</span> )

Issue a call to remote RPC method.

### Parameters

`method`  
Remote RPC method name.

`parameters`  
Parameters.

### Return Values

### Examples

**Example \#1 <span class="function">Yar\_Client::\_\_call</span>
example**

``` php
<?php

$client = new Yar_Client("http://host/api/");

/* call remote service */
$result = $client->some_method("parameter");
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Client::setOpt</span>

Yar\_Client::\_\_construct
==========================

Create a client

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">Yar\_Client::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

Create a <span class="classname">Yar\_Client</span> to a <span
class="classname">Yar\_Server</span>.

### Parameters

`url`  
Yar Server URL.

### Return Values

<span class="classname">Yar\_Client</span> instance.

### Examples

**Example \#1 <span class="function">Yar\_Client::\_\_construct</span>
example**

``` php
<?php
$client = new Yar_Client("http://host/api/");
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Client::\_\_call</span>
-   <span class="methodname">Yar\_Client::setOpt</span>

Yar\_Client::setOpt
===================

Set calling contexts

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">Yar\_Client</span><span class="type">false</span></span>
<span class="methodname">Yar\_Client::setOpt</span> ( <span
class="methodparam"><span class="type">int</span> `$name`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

### Parameters

`name`  
it can be: YAR\_OPT\_PACKAGER, YAR\_OPT\_PERSISTENT (Need server
support), YAR\_OPT\_TIMEOUT, YAR\_OPT\_CONNECT\_TIMEOUT YAR\_OPT\_HEADER
(Since 2.0.4)

`value`  

### Return Values

Returns `$this` on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">Yar\_Client::setOpt</span>
example**

``` php
<?php

$cient = new Yar_Client("http://host/api/");

//Set timeout to 1s
$client->SetOpt(YAR_OPT_CONNECT_TIMEOUT, 1000);

//Set packager to JSON
$client->SetOpt(YAR_OPT_PACKAGER, "json");

//Set Custom headers
$client->SetOpt(YAR_OPT_HEADER, array("hr1: val1", "hd2: val2"));

/* call remote service */
$result = $client->some_method("parameter");
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Client::\_\_call</span>

Introduction
------------

Class synopsis
--------------

**Yar\_Concurrent\_Client**

<span class="ooclass"> class **Yar\_Concurrent\_Client** </span> {

/\* Properties \*/

<span class="modifier">static</span> `$_callstack` ;

<span class="modifier">static</span> `$_callback` ;

<span class="modifier">static</span> `$_error_callback` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">call</span> ( <span class="methodparam"><span
class="type">string</span> `$uri`</span> , <span
class="methodparam"><span class="type">string</span> `$method`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$parameters`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$callback`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$error_callback`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`</span> \]\]\]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">loop</span> (\[ <span class="methodparam"><span
class="type">callable</span> `$callback`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$error_callback`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">reset</span> ( <span class="methodparam">void</span>
)

}

Properties
----------

`_callstack`  

`_callback`  

`_error_callback`  

Yar\_Concurrent\_Client::call
=============================

Register a concurrent call

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Yar\_Concurrent\_Client::call</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">array</span> `$parameters`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$error_callback`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\]\] )

Register a RPC call, but won't sent it immediately, it will be send
while further call to <span
class="methodname">Yar\_Concurrent\_Client::loop</span>

### Parameters

`uri`  
The RPC server URI(http, tcp)

`method`  
Service name(aka the method name)

`parameters`  
Parameters

`callback`  
A function callback, which will be called while the response return.

### Return Values

An unique id, can be used to identified which call it is.

### Examples

**Example \#1 <span
class="function">Yar\_Concurrent\_Client::call</span> example**

``` php
<?php
function callback($retval, $callinfo) {
     var_dump($retval);
}

function error_callback($type, $error, $callinfo) {
    error_log($error);
}

Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback");
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"));   // if the callback is not specificed, 
                                                                               // callback in loop will be used
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback", NULL, array(YAR_OPT_PACKAGER => "json"));
                                                                               //this server accept json packager
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback", NULL, array(YAR_OPT_TIMEOUT=>1));
                                                                               //custom timeout 

//The requests are not sent yet
?>
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Concurrent\_Client::loop</span>
-   <span class="methodname">Yar\_Concurrent\_Client::reset</span>
-   <span class="methodname">Yar\_Server::\_\_construct</span>
-   <span class="methodname">Yar\_Server::handle</span>

Yar\_Concurrent\_Client::loop
=============================

Send all calls

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Yar\_Concurrent\_Client::loop</span> (\[ <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$error_callback`</span> \]\] )

Send all registed remote RPC calls.

### Parameters

`callback`  
If this callback is set, then Yar will call this callback after all
calls are sent and before any response return, with a $callinfo NULL.

Then, if user didn't specify callback when registering concurrent call,
this callback will be used to handle response, otherwise, the callback
specified while registering will be used.

`error_callback`  
If this callback is set, then Yar will call this callback while error
occurred.

### Return Values

### Examples

**Example \#1 <span
class="function">Yar\_Concurrent\_Client::loop</span> example**

``` php
<?php
function callback($retval, $callinfo) {
     if ($callinfo == NULL) {
        echo "Now, all requests are sent, and no any response available\n";
     } else {
        echo "This is a remote call response, the method name is", $callinfo["method"], 
             ". calling sequence is " , $callinfo["sequence"] , "\n";
        var_dump($retval);
     }
} 

function error_callback($type, $error, $callinfo) {
    error_log($error);
}

Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback");
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"));   // if the callback is not specificed, 
                                                                               // callback in loop will be used
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback", NULL, array(YAR_OPT_PACKAGER => "json"));
                                                                               //this server accept json packager
Yar_Concurrent_Client::call("http://host/api/", "some_method", array("parameters"), "callback", NULL, array(YAR_OPT_TIMEOUT=>1));
                                                                               //custom timeout 

Yar_Concurrent_Client::loop("callback", "error_callback"); //send the requests, 
                                                           //the error_callback is optional
?>
```

The above example will output something similar to:

    Now, all requests are sent, and no any response available
    This is a remote call response, the method name issome_method. calling sequence is 4
    string(11) "some_method"
    This is a remote call response, the method name issome_method. calling sequence is 1
    string(11) "some_method"
    This is a remote call response, the method name issome_method. calling sequence is 2
    string(11) "some_method"
    This is a remote call response, the method name issome_method. calling sequence is 3
    string(11) "some_method"

### See Also

-   <span class="methodname">Yar\_Concurrent\_Client::call</span>
-   <span class="methodname">Yar\_Concurrent\_Client::reset</span>
-   <span class="methodname">Yar\_Server::\_\_construct</span>
-   <span class="methodname">Yar\_Server::handle</span>

Yar\_Concurrent\_Client::reset
==============================

Clean all registered calls

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Yar\_Concurrent\_Client::reset</span> ( <span
class="methodparam">void</span> )

Clean all registered calls

### Parameters

### Return Values

### Examples

**Example \#1 <span
class="function">Yar\_Concurrent\_Client::reset</span> example**

``` php
```

The above example will output something similar to:

### See Also

-   <span class="methodname">Yar\_Concurrent\_Client::call</span>
-   <span class="methodname">Yar\_Concurrent\_Client::loop</span>
-   <span class="methodname">Yar\_Server::\_\_construct</span>
-   <span class="methodname">Yar\_Server::handle</span>

Introduction
------------

If service threw exceptions, A Yar\_Server\_Exception will be threw in
client side.

Class synopsis
--------------

**Yar\_Server\_Exception**

<span class="ooclass"> class **Yar\_Server\_Exception** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_type` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getType</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`message`  

`code`  

`file`  

`line`  

`_type`  

Yar\_Server\_Exception::getType
===============================

Retrieve exception's type

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yar\_Server\_Exception::getType</span> ( <span
class="methodparam">void</span> )

Get the exception original type threw by server

### Parameters

This function has no parameters.

### Return Values

string

### Examples

**Example \#1 <span
class="function">Yar\_Server\_Exception::getType</span> example**

``` php
//Server.php
<?php
class Custom_Exception extends Exception {};

class API {
    public function throw_exception($name) {
        throw new Custom_Exception($name);
    }
}

$service = new Yar_Server(new API());
$service->handle();
?>

//Client.php
<?php
$client = new Yar_Client("http://host/api.php");

try {
    $client->throw_exception("client");
} catch (Yar_Server_Exception $e) {
    var_dump($e->getType());
    var_dump($e->getMessage());
}
```

The above example will output something similar to:

    string(16) "Custom_Exception"
    string(6) "client"

### See Also

-   

Introduction
------------

Class synopsis
--------------

**Yar\_Client\_Exception**

<span class="ooclass"> class **Yar\_Client\_Exception** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getType</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`message`  

`code`  

`file`  

`line`  

Yar\_Client\_Exception::getType
===============================

Retrieve exception's type

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Yar\_Client\_Exception::getType</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns *"Yar\_Exception\_Client"*.

### Examples

**Example \#1 <span
class="function">Yar\_Client\_Exception::getType</span> example**

``` php
<?php

/* ... */

?>
```

The above example will output something similar to:

    ...

### See Also

-   <span class="methodname">Yaf\_Server\_Exception::getType</span>
