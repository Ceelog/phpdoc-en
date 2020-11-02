SPL Type Handling
=================

**Table of Contents**

-   [Introduction](/intro/spl-types.html)
-   [Installing/Configuring](/spl-types/setup.html)
    -   [Requirements](/spl-types/setup.html#Requirements)
    -   [Installation](/spl-types/setup.html#Installation)
    -   [Runtime
        Configuration](/spl-types/setup.html#Runtime%20Configuration)
    -   [Resource Types](/spl-types/setup.html#Resource%20Types)
-   [SplType](/class/spltype.html) — The SplType class
    -   [SplType::\_\_construct](/class/spltype.html#SplType::__construct)
        — Creates a new value of some type
-   [SplInt](/class/splint.html) — The SplInt class
-   [SplFloat](/class/splfloat.html) — The SplFloat class
-   [SplEnum](/class/splenum.html) — The SplEnum class
    -   [SplEnum::getConstList](/class/splenum.html#SplEnum::getConstList)
        — Returns all consts (possible values) as an array
-   [SplBool](/class/splbool.html) — The SplBool class
-   [SplString](/class/splstring.html) — The SplString class

Introduction
------------

Parent class for all SPL types.

Class synopsis
--------------

**SplType**

<span class="ooclass"> <span class="modifier">abstract</span> class
**SplType** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">NULL</span>
`SplType::__default` <span class="initializer"> = **`NULL`**</span> ;

/\* Methods \*/

<span class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

}

Predefined Constants
--------------------

**`SplType::__default`**  

SplType::\_\_construct
======================

Creates a new value of some type

### Description

<span class="methodname">SplType::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`initial_value`  
Type and default value depends on the extension class.

`strict`  
Whether to set the object's strictness.

### Errors/Exceptions

Throws an <span class="classname">UnexpectedValueException</span> if
incompatible type is given.

Introduction
------------

The SplInt class is used to enforce strong typing of the integer type.

Class synopsis
--------------

**SplInt**

<span class="ooclass"> class **SplInt** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplType** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SplInt::__default` <span class="initializer"> = 0</span> ;

/\* Inherited methods \*/

<span class="methodname">SplType::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

}

Predefined Constants
--------------------

**`SplInt::__default`**  

Examples
--------

**Example \#1 <span class="classname">SplInt</span> usage example**

``` php
<?php
$int = new SplInt(94);

try {
    $int = 'Try to cast a string value for fun';
} catch (UnexpectedValueException $uve) {
    echo $uve->getMessage() . PHP_EOL;
}

echo $int . PHP_EOL;
?>
```

The above example will output:

    Value not an integer
    94

Introduction
------------

The SplFloat class is used to enforce strong typing of the float type.

Class synopsis
--------------

**SplFloat**

<span class="ooclass"> class **SplFloat** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplType** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">float</span>
`SplFloat::__default` <span class="initializer"> = 0</span> ;

/\* Inherited methods \*/

<span class="methodname">SplType::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

}

Predefined Constants
--------------------

**`SplFloat::__default`**  

Examples
--------

**Example \#2 <span class="classname">SplFloat</span> usage example**

``` php
<?php
$float = new SplFloat(3.154);
$newFloat = new SplFloat(3);

try {
    $float = 'Try to cast a string value for fun';
} catch (UnexpectedValueException $uve) {
    echo $uve->getMessage() . PHP_EOL;
}

echo $float . PHP_EOL;
echo $newFloat . PHP_EOL;
?>
```

The above example will output:

    Value not a float
    3.154
    3

Introduction
------------

SplEnum gives the ability to emulate and create enumeration objects
natively in PHP.

Class synopsis
--------------

**SplEnum**

<span class="ooclass"> class **SplEnum** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplType** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">NULL</span>
`SplEnum::__default` <span class="initializer"> = **`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getConstList</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$include_default`<span class="initializer"> = **`FALSE`**</span></span>
\] )

/\* Inherited methods \*/

<span class="methodname">SplType::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

}

Predefined Constants
--------------------

**`SplEnum::__default`**  

Examples
--------

**Example \#3 <span class="classname">SplEnum</span> usage example**

``` php
<?php
class Month extends SplEnum {
    const __default = self::January;
    
    const January = 1;
    const February = 2;
    const March = 3;
    const April = 4;
    const May = 5;
    const June = 6;
    const July = 7;
    const August = 8;
    const September = 9;
    const October = 10;
    const November = 11;
    const December = 12;
}

echo new Month(Month::June) . PHP_EOL;

try {
    new Month(13);
} catch (UnexpectedValueException $uve) {
    echo $uve->getMessage() . PHP_EOL;
}
?>
```

The above example will output:

    6
    Value not a const in enum Month

SplEnum::getConstList
=====================

Returns all consts (possible values) as an array

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplEnum::getConstList</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$include_default`<span class="initializer"> = **`FALSE`**</span></span>
\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`include_default`  
Whether to include *\_\_default* property.

### Return Values

### Examples

**Example \#1 <span class="function">SplEnum::getConstList</span>
example**

``` php
<?php
$bool = new SplBool;
var_dump($bool->getConstList(true));
?>
```

The above example will output:

    array(3) {
      ["__default"]=>
      bool(false)
      ["false"]=>
      bool(false)
      ["true"]=>
      bool(true)
    }

Introduction
------------

The SplBool class is used to enforce strong typing of the bool type.

Class synopsis
--------------

**SplBool**

<span class="ooclass"> class **SplBool** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplEnum** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">bool</span>
`SplBool::__default` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">const</span> <span class="type">bool</span>
`SplBool::false` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">const</span> <span class="type">bool</span>
`SplBool::true` <span class="initializer"> = **`TRUE`**</span> ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplEnum::getConstList</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$include_default`<span class="initializer"> = **`FALSE`**</span></span>
\] )

}

Predefined Constants
--------------------

**`SplBool::__default`**  

**`SplBool::false`**  

**`SplBool::true`**  

Examples
--------

**Example \#1 <span class="classname">SplBool</span> usage example**

``` php
<?php
$true = new SplBool(true);
if ($true) {
    echo "TRUE\n";
}

$false = new SplBool;
if ($false) {
    echo "FALSE\n";
}
?>
```

The above example will output:

    TRUE

Introduction
------------

The SplString class is used to enforce strong typing of the string type.

Class synopsis
--------------

**SplString**

<span class="ooclass"> class **SplString** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SplType**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`SplString::__default` <span class="initializer"> = ''</span> ;

/\* Inherited methods \*/

<span class="methodname">SplType::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`</span> \]\] )

}

Predefined Constants
--------------------

**`SplString::__default`**  

Examples
--------

**Example \#2 <span class="classname">SplString</span> usage example**

``` php
<?php
$string = new SplString("Testing");

try {
    $string = array();
} catch (UnexpectedValueException $uve) {
    echo $uve->getMessage() . PHP_EOL;
}

var_dump($string);
echo $string; // Outputs "Testing"
?>
```

The above example will output:

    Value not a string
    object(SplString)#1 (1) {
      ["__default"]=>
      string(7) "Testing"
    }
    Testing
