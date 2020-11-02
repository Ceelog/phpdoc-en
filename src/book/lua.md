Lua
===

**Table of Contents**

-   [Introduction](/intro/lua.html)
-   [Installing/Configuring](/lua/setup.html)
    -   [Requirements](/lua/setup.html#Requirements)
    -   [Installation](/lua/setup.html#Installation)
    -   [Runtime Configuration](/lua/setup.html#Runtime%20Configuration)
    -   [Resource Types](/lua/setup.html#Resource%20Types)
-   [Lua](/class/lua.html) — The Lua class
    -   [Lua::assign](/class/lua.html#Lua::assign) — Assign a PHP
        variable to Lua
    -   [Lua::call](/class/lua.html#Lua::call) — Call Lua functions
    -   [Lua::\_\_construct](/class/lua.html#Lua::__construct) — Lua
        constructor
    -   [Lua::eval](/class/lua.html#Lua::eval) — Evaluate a string as
        Lua code
    -   [Lua::getVersion](/class/lua.html#Lua::getVersion) — The
        getversion purpose
    -   [Lua::include](/class/lua.html#Lua::include) — Parse a Lua
        script file
    -   [Lua::registerCallback](/class/lua.html#Lua::registerCallback) —
        Register a PHP function to Lua
-   [LuaClosure](/class/luaclosure.html) — The LuaClosure class
    -   [LuaClosure::\_\_invoke](/class/luaclosure.html#LuaClosure::__invoke)
        — Invoke luaclosure

Introduction
------------

Class synopsis
--------------

**Lua**

<span class="ooclass"> class **Lua** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`Lua::LUA_VERSION` <span class="initializer"> = Lua 5.1.4</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">assign</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">call</span> ( <span class="methodparam"><span
class="type">callable</span> `$lua_func`</span> \[, <span
class="methodparam"><span class="type">array</span> `$args`</span> \[,
<span class="methodparam"><span class="type">int</span> `$use_self`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">\_\_call</span> ( <span
class="methodparam"><span class="type">callable</span>
`$lua_func`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \[, <span
class="methodparam"><span class="type">int</span> `$use_self`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$lua_script_file`<span class="initializer"> = NULL</span></span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">eval</span> ( <span class="methodparam"><span
class="type">string</span> `$statements`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">include</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">registerCallback</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$function`</span> )

}

Predefined Constants
--------------------

**`Lua::LUA_VERSION`**  

Lua::assign
===========

Assign a PHP variable to Lua

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::assign</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`name`  

`value`  

### Return Values

Returns `$this` or **`NULL`** on failure.

### Examples

**Example \#1 <span class="function">Lua::assign</span>example**

``` php
<?php
$lua = new Lua();
$lua->assign("php_var", array(1=>1, 2, 3)); //lua table index begin with 1
$lua->eval(<<<CODE
    print(php_var);
CODE
);
?>
```

The above example will output:

    Array
     (
         [1] => 1
         [2] => 2
         [3] => 3
     )

Lua::call
=========

Lua::\_\_call
=============

Call Lua functions

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::call</span> ( <span
class="methodparam"><span class="type">callable</span>
`$lua_func`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \[, <span
class="methodparam"><span class="type">int</span> `$use_self`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::\_\_call</span> ( <span
class="methodparam"><span class="type">callable</span>
`$lua_func`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \[, <span
class="methodparam"><span class="type">int</span> `$use_self`<span
class="initializer"> = 0</span></span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`lua_func`  
Function name in lua

`args`  
Arguments passed to the Lua function

`use_self`  
Whether to use *self*

### Return Values

Returns result of the called function, **`NULL`** for wrong arguments or
**`FALSE`** on other failure.

### Examples

**Example \#1 <span class="function">Lua::call</span>example**

``` php
<?php
$lua = new Lua();
$lua->eval(<<<CODE
    function dummy(foo, bar)
        print(foo, ",", bar)
    end
CODE
);
$lua->call("dummy", array("Lua", "geiliable\n"));
$lua->dummy("Lua", "geiliable"); // __call()
var_dump($lua->call(array("table", "concat"), array(array(1=>1, 2=>2, 3=>3), "-")));
?>
```

The above example will output:

    Lua,geiliable
    Lua,geiliable
    string(5) "1-2-3"

### See Also

-   <a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>

Lua::\_\_construct
==================

Lua constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Lua::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$lua_script_file`<span class="initializer"> = NULL</span></span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`lua_script_file`  

### Return Values

Lua::eval
=========

Evaluate a string as Lua code

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::eval</span> ( <span
class="methodparam"><span class="type">string</span>
`$statements`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`statements`  

### Return Values

Returns result of evaled code, **`NULL`** for wrong arguments or
**`FALSE`** on other failure.

### Examples

**Example \#1 <span class="function">Lua::eval</span>example**

``` php
<?php
$lua = new Lua();
$lua->eval(<<<CODE
    print(2);
CODE
);
?>
```

The above example will output:

    2

Lua::getVersion
===============

The getversion purpose

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Lua::getVersion</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns `Lua::LUA_VERSION`.

Lua::include
============

Parse a Lua script file

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::include</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`file`  

### Return Values

Returns result of included code, **`NULL`** for wrong arguments or
**`FALSE`** on other failure.

Lua::registerCallback
=====================

Register a PHP function to Lua

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Lua::registerCallback</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$function`</span> )

Register a PHP function to Lua as a function named "$name"

### Parameters

`name`  

`function`  
A valid PHP function callback

### Return Values

Returns `$this`, **`NULL`** for wrong arguments or **`FALSE`** on other
failure.

### Examples

**Example \#1 <span
class="function">Lua::registerCallback</span>example**

``` php
<?php
$lua = new Lua();
$lua->registerCallback("echo", "var_dump");
$lua->eval(<<<CODE
    echo({1, 2, 3});
CODE
);
?>
```

The above example will output:

    array(3) {
      [1]=>
      float(1)
      [2]=>
      float(2)
      [3]=>
      float(3)
    }

Introduction
------------

LuaClosure is a wrapper class for LUA\_TFUNCTION which could be return
from calling to Lua function.

Class synopsis
--------------

**LuaClosure**

<span class="ooclass"> class **LuaClosure** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_invoke</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

}

LuaClosure::\_\_invoke
======================

Invoke luaclosure

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">LuaClosure::\_\_invoke</span> ( <span
class="methodparam"><span class="type">mixed</span> `$args`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`args`  

### Return Values

### Examples

**Example \#1 <span
class="function">LuaClosure::\_\_invoke</span>example**

``` php
<?php
$lua = new Lua();
$closure = $lua->eval(<<<CODE
    return (function ()
        print("hello world")
    end)
CODE
);

$lua->call($closure);
/* after PHP 5.3 */
$closure();
?>
```

The above example will output:

    hello worldhello world
