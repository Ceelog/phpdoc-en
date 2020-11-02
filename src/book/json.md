JavaScript Object Notation
==========================

**Table of Contents**

-   [Introduction](/intro/json.html)
-   [Installing/Configuring](/json/setup.html)
    -   [Requirements](/json/setup.html#Requirements)
    -   [Installation](/json/setup.html#Installation)
    -   [Runtime
        Configuration](/json/setup.html#Runtime%20Configuration)
    -   [Resource Types](/json/setup.html#Resource%20Types)
-   [Predefined Constants](/json/constants.html)
-   [JsonException](/class/jsonexception.html) — The JsonException class
-   [JsonSerializable](/class/jsonserializable.html) — The
    JsonSerializable interface
    -   [JsonSerializable::jsonSerialize](/class/jsonserializable.html#JsonSerializable::jsonSerialize)
        — Specify data which should be serialized to JSON
-   [JSON Functions](/ref/json.html)
    -   [json\_decode](/ref/json.html#json_decode) — Decodes a JSON
        string
    -   [json\_encode](/ref/json.html#json_encode) — Returns the JSON
        representation of a value
    -   [json\_last\_error\_msg](/ref/json.html#json_last_error_msg) —
        Returns the error string of the last json\_encode() or
        json\_decode() call
    -   [json\_last\_error](/ref/json.html#json_last_error) — Returns
        the last error occurred

Introduction
------------

Exception thrown if **`JSON_THROW_ON_ERROR`** option is set for <span
class="function">json\_encode</span> or <span
class="function">json\_decode</span>. `code` contains the error type,
for possible values see <span class="function">json\_last\_error</span>.

Class synopsis
--------------

**JsonException**

<span class="ooclass"> class **JsonException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

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

Introduction
------------

Objects implementing <span class="interfacename">JsonSerializable</span>
can customize their JSON representation when encoded with <span
class="function">json\_encode</span>.

Interface synopsis
------------------

**JsonSerializable**

<span class="ooclass"> class **JsonSerializable** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">jsonSerialize</span> ( <span
class="methodparam">void</span> )

}

JsonSerializable::jsonSerialize
===============================

Specify data which should be serialized to JSON

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">JsonSerializable::jsonSerialize</span> ( <span
class="methodparam">void</span> )

Serializes the object to a value that can be serialized natively by
<span class="function">json\_encode</span>.

### Parameters

This function has no parameters.

### Return Values

Returns data which can be serialized by <span
class="function">json\_encode</span>, which is a value of any type other
than a
<a href="/language/types/resource.html" class="link">resource</a>.

### Examples

**Example \#1 <span
class="methodname">JsonSerializable::jsonSerialize</span> example
returning an <span class="type">array</span>**

``` php
<?php
class ArrayValue implements JsonSerializable {
    public function __construct(array $array) {
        $this->array = $array;
    }

    public function jsonSerialize() {
        return $this->array;
    }
}

$array = [1, 2, 3];
echo json_encode(new ArrayValue($array), JSON_PRETTY_PRINT);
?>
```

The above example will output:

    [
        1,
        2,
        3
    ]

**Example \#2 <span
class="methodname">JsonSerializable::jsonSerialize</span> example
returning an associative <span class="type">array</span>**

``` php
<?php
class ArrayValue implements JsonSerializable {
    public function __construct(array $array) {
        $this->array = $array;
    }

    public function jsonSerialize() {
        return $this->array;
    }
}

$array = ['foo' => 'bar', 'quux' => 'baz'];
echo json_encode(new ArrayValue($array), JSON_PRETTY_PRINT);
?>
```

The above example will output:

    {
        "foo": "bar",
        "quux": "baz"
    }

**Example \#3 <span
class="methodname">JsonSerializable::jsonSerialize</span> example
returning an <span class="type">int</span>**

``` php
<?php
class IntegerValue implements JsonSerializable {
    public function __construct($number) {
        $this->number = (integer) $number;
    }

    public function jsonSerialize() {
        return $this->number;
    }
}

echo json_encode(new IntegerValue(1), JSON_PRETTY_PRINT);
?>
```

The above example will output:

    1

**Example \#4 <span
class="methodname">JsonSerializable::jsonSerialize</span> example
returning a <span class="type">string</span>**

``` php
<?php
class StringValue implements JsonSerializable {
    public function __construct($string) {
        $this->string = (string) $string;
    }

    public function jsonSerialize() {
        return $this->string;
    }
}

echo json_encode(new StringValue('Hello!'), JSON_PRETTY_PRINT);
?>
```

The above example will output:

    "Hello!"
