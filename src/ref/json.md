json\_decode
============

Decodes a JSON string

### Description

<span class="type">mixed</span> <span
class="methodname">json\_decode</span> ( <span class="methodparam"><span
class="type">string</span> `$json`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">bool</span><span class="type">null</span></span>
`$associative`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">int</span> `$depth`<span
class="initializer"> = 512</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\]\] )

Takes a JSON encoded string and converts it into a PHP variable.

### Parameters

`json`  
The `json` <span class="type">string</span> being decoded.

This function only works with UTF-8 encoded strings.

> **Note**:
>
> PHP implements a superset of JSON as specified in the original
> <a href="http://www.faqs.org/rfcs/rfc7159" class="link external">» RFC 7159</a>.

`associative`  
When **`true`**, JSON objects will be returned as associative <span
class="type">array</span>s; when **`false`**, JSON objects will be
returned as <span class="type">object</span>s. When **`null`**, JSON
objects will be returned as associative <span class="type">array</span>s
or <span class="type">object</span>s depending on whether
**`JSON_OBJECT_AS_ARRAY`** is set in the `flags`.

`depth`  
Maximum nesting depth of the structure being decoded.

`flags`  
Bitmask of **`JSON_BIGINT_AS_STRING`**, **`JSON_INVALID_UTF8_IGNORE`**,
**`JSON_INVALID_UTF8_SUBSTITUTE`**, **`JSON_OBJECT_AS_ARRAY`**,
**`JSON_THROW_ON_ERROR`**. The behaviour of these constants is described
on the <a href="/json/constants.html" class="link">JSON constants</a>
page.

### Return Values

Returns the value encoded in `json` in appropriate PHP type. Values
*true*, *false* and *null* are returned as **`true`**, **`false`** and
**`null`** respectively. **`null`** is returned if the `json` cannot be
decoded or if the encoded data is deeper than the nesting limit.

### Changelog

| Version | Description                                                                                                       |
|---------|-------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | **`JSON_THROW_ON_ERROR`** `flags` was added.                                                                      |
| 7.2.0   | `associative` is nullable now.                                                                                    |
| 7.2.0   | **`JSON_INVALID_UTF8_IGNORE`**, and **`JSON_INVALID_UTF8_SUBSTITUTE`** `flags` were added.                        |
| 7.1.0   | An empty JSON key ("") can be encoded to the empty object property instead of using a key with value *\_empty\_*. |

### Examples

**Example \#1 <span class="function">json\_decode</span> examples**

``` php
<?php
$json = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

var_dump(json_decode($json));
var_dump(json_decode($json, true));

?>
```

The above example will output:

    object(stdClass)#1 (5) {
        ["a"] => int(1)
        ["b"] => int(2)
        ["c"] => int(3)
        ["d"] => int(4)
        ["e"] => int(5)
    }

    array(5) {
        ["a"] => int(1)
        ["b"] => int(2)
        ["c"] => int(3)
        ["d"] => int(4)
        ["e"] => int(5)
    }

**Example \#2 Accessing invalid object properties**

Accessing elements within an object that contain characters not
permitted under PHP's naming convention (e.g. the hyphen) can be
accomplished by encapsulating the element name within braces and the
apostrophe.

``` php
<?php

$json = '{"foo-bar": 12345}';

$obj = json_decode($json);
print $obj->{'foo-bar'}; // 12345

?>
```

**Example \#3 common mistakes using <span
class="function">json\_decode</span>**

``` php
<?php

// the following strings are valid JavaScript but not valid JSON

// the name and value must be enclosed in double quotes
// single quotes are not valid 
$bad_json = "{ 'bar': 'baz' }";
json_decode($bad_json); // null

// the name must be enclosed in double quotes
$bad_json = '{ bar: "baz" }';
json_decode($bad_json); // null

// trailing commas are not allowed
$bad_json = '{ bar: "baz", }';
json_decode($bad_json); // null

?>
```

**Example \#4 `depth` errors**

``` php
<?php
// Encode some data with a maximum depth  of 4 (array -> array -> array -> string)
$json = json_encode(
    array(
        1 => array(
            'English' => array(
                'One',
                'January'
            ),
            'French' => array(
                'Une',
                'Janvier'
            )
        )
    )
);

// Show the errors for different depths.
var_dump(json_decode($json, true, 4));
echo 'Last error: ', json_last_error_msg(), PHP_EOL, PHP_EOL;

var_dump(json_decode($json, true, 3));
echo 'Last error: ', json_last_error_msg(), PHP_EOL, PHP_EOL;
?>
```

The above example will output:

    array(1) {
      [1]=>
      array(2) {
        ["English"]=>
        array(2) {
          [0]=>
          string(3) "One"
          [1]=>
          string(7) "January"
        }
        ["French"]=>
        array(2) {
          [0]=>
          string(3) "Une"
          [1]=>
          string(7) "Janvier"
        }
      }
    }
    Last error: No error

    NULL
    Last error: Maximum stack depth exceeded

**Example \#5 <span class="function">json\_decode</span> of large
integers**

``` php
<?php
$json = '{"number": 12345678901234567890}';

var_dump(json_decode($json));
var_dump(json_decode($json, false, 512, JSON_BIGINT_AS_STRING));

?>
```

The above example will output:

    object(stdClass)#1 (1) {
      ["number"]=>
      float(1.2345678901235E+19)
    }
    object(stdClass)#1 (1) {
      ["number"]=>
      string(20) "12345678901234567890"
    }

### Notes

> **Note**:
>
> The JSON spec is not JavaScript, but a subset of JavaScript.

> **Note**:
>
> In the event of a failure to decode, <span
> class="function">json\_last\_error</span> can be used to determine the
> exact nature of the error.

### See Also

-   <span class="function">json\_encode</span>
-   <span class="function">json\_last\_error</span>

json\_encode
============

Returns the JSON representation of a value

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">json\_encode</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$depth`<span
class="initializer"> = 512</span></span> \]\] )

Returns a string containing the JSON representation of the supplied
`value`.

The encoding is affected by the supplied `flags` and additionally the
encoding of float values depends on the value of
<a href="/ini/core.html#ini.serialize-precision" class="link">serialize_precision</a>.

### Parameters

`value`  
The `value` being encoded. Can be any type except a
<a href="/language/types/resource.html" class="link">resource</a>.

All string data must be UTF-8 encoded.

> **Note**:
>
> PHP implements a superset of JSON as specified in the original
> <a href="http://www.faqs.org/rfcs/rfc7159" class="link external">» RFC 7159</a>.

`flags`  
Bitmask consisting of **`JSON_FORCE_OBJECT`**, **`JSON_HEX_QUOT`**,
**`JSON_HEX_TAG`**, **`JSON_HEX_AMP`**, **`JSON_HEX_APOS`**,
**`JSON_INVALID_UTF8_IGNORE`**, **`JSON_INVALID_UTF8_SUBSTITUTE`**,
**`JSON_NUMERIC_CHECK`**, **`JSON_PARTIAL_OUTPUT_ON_ERROR`**,
**`JSON_PRESERVE_ZERO_FRACTION`**, **`JSON_PRETTY_PRINT`**,
**`JSON_UNESCAPED_LINE_TERMINATORS`**, **`JSON_UNESCAPED_SLASHES`**,
**`JSON_UNESCAPED_UNICODE`**, **`JSON_THROW_ON_ERROR`**. The behaviour
of these constants is described on the
<a href="/json/constants.html" class="link">JSON constants</a> page.

`depth`  
Set the maximum depth. Must be greater than zero.

### Return Values

Returns a JSON encoded <span class="type">string</span> on success or
**`false`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                             |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | **`JSON_THROW_ON_ERROR`** `flags` was added.                                                                                                                                                            |
| 7.2.0   | **`JSON_INVALID_UTF8_IGNORE`**, and **`JSON_INVALID_UTF8_SUBSTITUTE`** `flags` were added.                                                                                                              |
| 7.1.0   | **`JSON_UNESCAPED_LINE_TERMINATORS`** `flags` was added.                                                                                                                                                |
| 7.1.0   | <a href="/ini/core.html#ini.serialize-precision" class="link">serialize_precision</a> is used instead of <a href="/ini/core.html#ini.precision" class="link">precision</a> when encoding double values. |

### Examples

**Example \#1 A <span class="function">json\_encode</span> example**

``` php
<?php
$arr = array('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5);

echo json_encode($arr);
?>
```

The above example will output:

    {"a":1,"b":2,"c":3,"d":4,"e":5}

**Example \#2 A <span class="function">json\_encode</span> example
showing some options in use**

``` php
<?php
$a = array('<foo>',"'bar'",'"baz"','&blong&', "\xc3\xa9");

echo "Normal: ",  json_encode($a), "\n";
echo "Tags: ",    json_encode($a, JSON_HEX_TAG), "\n";
echo "Apos: ",    json_encode($a, JSON_HEX_APOS), "\n";
echo "Quot: ",    json_encode($a, JSON_HEX_QUOT), "\n";
echo "Amp: ",     json_encode($a, JSON_HEX_AMP), "\n";
echo "Unicode: ", json_encode($a, JSON_UNESCAPED_UNICODE), "\n";
echo "All: ",     json_encode($a, JSON_HEX_TAG | JSON_HEX_APOS | JSON_HEX_QUOT | JSON_HEX_AMP | JSON_UNESCAPED_UNICODE), "\n\n";

$b = array();

echo "Empty array output as array: ", json_encode($b), "\n";
echo "Empty array output as object: ", json_encode($b, JSON_FORCE_OBJECT), "\n\n";

$c = array(array(1,2,3));

echo "Non-associative array output as array: ", json_encode($c), "\n";
echo "Non-associative array output as object: ", json_encode($c, JSON_FORCE_OBJECT), "\n\n";

$d = array('foo' => 'bar', 'baz' => 'long');

echo "Associative array always output as object: ", json_encode($d), "\n";
echo "Associative array always output as object: ", json_encode($d, JSON_FORCE_OBJECT), "\n\n";
?>
```

The above example will output:

    Normal: ["<foo>","'bar'","\"baz\"","&blong&","\u00e9"]
    Tags: ["\u003Cfoo\u003E","'bar'","\"baz\"","&blong&","\u00e9"]
    Apos: ["<foo>","\u0027bar\u0027","\"baz\"","&blong&","\u00e9"]
    Quot: ["<foo>","'bar'","\u0022baz\u0022","&blong&","\u00e9"]
    Amp: ["<foo>","'bar'","\"baz\"","\u0026blong\u0026","\u00e9"]
    Unicode: ["<foo>","'bar'","\"baz\"","&blong&","é"]
    All: ["\u003Cfoo\u003E","\u0027bar\u0027","\u0022baz\u0022","\u0026blong\u0026","é"]

    Empty array output as array: []
    Empty array output as object: {}

    Non-associative array output as array: [[1,2,3]]
    Non-associative array output as object: {"0":{"0":1,"1":2,"2":3}}

    Associative array always output as object: {"foo":"bar","baz":"long"}
    Associative array always output as object: {"foo":"bar","baz":"long"}

**Example \#3 JSON\_NUMERIC\_CHECK option example**

``` php
<?php
echo "Strings representing numbers automatically turned into numbers".PHP_EOL;
$numbers = array('+123123', '-123123', '1.2e3', '0.00001');
var_dump(
 $numbers,
 json_encode($numbers, JSON_NUMERIC_CHECK)
);
echo "Strings containing improperly formatted numbers".PHP_EOL;
$strings = array('+a33123456789', 'a123');
var_dump(
 $strings,
 json_encode($strings, JSON_NUMERIC_CHECK)
);
?>
```

The above example will output something similar to:

    Strings representing numbers automatically turned into numbers
    array(4) {
      [0]=>
      string(7) "+123123"
      [1]=>
      string(7) "-123123"
      [2]=>
      string(5) "1.2e3"
      [3]=>
      string(7) "0.00001"
    }
    string(28) "[123123,-123123,1200,1.0e-5]"
    Strings containing improperly formatted numbers
    array(2) {
      [0]=>
      string(13) "+a33123456789"
      [1]=>
      string(4) "a123"
    }
    string(24) "["+a33123456789","a123"]"

**Example \#4 Sequential versus non-sequential array example**

``` php
<?php
echo "Sequential array".PHP_EOL;
$sequential = array("foo", "bar", "baz", "blong");
var_dump(
 $sequential,
 json_encode($sequential)
);

echo PHP_EOL."Non-sequential array".PHP_EOL;
$nonsequential = array(1=>"foo", 2=>"bar", 3=>"baz", 4=>"blong");
var_dump(
 $nonsequential,
 json_encode($nonsequential)
);

echo PHP_EOL."Sequential array with one key unset".PHP_EOL;
unset($sequential[1]);
var_dump(
 $sequential,
 json_encode($sequential)
);
?>
```

The above example will output:

    Sequential array
    array(4) {
      [0]=>
      string(3) "foo"
      [1]=>
      string(3) "bar"
      [2]=>
      string(3) "baz"
      [3]=>
      string(5) "blong"
    }
    string(27) "["foo","bar","baz","blong"]"

    Non-sequential array
    array(4) {
      [1]=>
      string(3) "foo"
      [2]=>
      string(3) "bar"
      [3]=>
      string(3) "baz"
      [4]=>
      string(5) "blong"
    }
    string(43) "{"1":"foo","2":"bar","3":"baz","4":"blong"}"

    Sequential array with one key unset
    array(3) {
      [0]=>
      string(3) "foo"
      [2]=>
      string(3) "baz"
      [3]=>
      string(5) "blong"
    }
    string(33) "{"0":"foo","2":"baz","3":"blong"}"

**Example \#5 **`JSON_PRESERVE_ZERO_FRACTION`** option example**

``` php
<?php
var_dump(json_encode(12.0, JSON_PRESERVE_ZERO_FRACTION));
var_dump(json_encode(12.0));
?>
```

The above example will output:

    string(4) "12.0"
    string(2) "12"

### Notes

> **Note**:
>
> In the event of a failure to encode, <span
> class="function">json\_last\_error</span> can be used to determine the
> exact nature of the error.

> **Note**:
>
> When encoding an array, if the keys are not a continuous numeric
> sequence starting from 0, all keys are encoded as strings, and
> specified explicitly for each key-value pair.

> **Note**:
>
> Like the reference JSON encoder, <span
> class="function">json\_encode</span> will generate JSON that is a
> simple value (that is, neither an object nor an array) if given a
> <span class="type">string</span>, <span class="type">int</span>, <span
> class="type">float</span> or <span class="type">bool</span> as an
> input `value`. While most decoders will accept these values as valid
> JSON, some may not, as the specification is ambiguous on this point.
>
> To summarise, always test that your JSON decoder can handle the output
> you generate from <span class="function">json\_encode</span>.

### See Also

-   <span class="interfacename">JsonSerializable</span>
-   <span class="function">json\_decode</span>
-   <span class="function">json\_last\_error</span>
-   <span class="function">serialize</span>

json\_last\_error\_msg
======================

Returns the error string of the last json\_encode() or json\_decode()
call

### Description

<span class="type">string</span> <span
class="methodname">json\_last\_error\_msg</span> ( <span
class="methodparam">void</span> )

Returns the error string of the last <span
class="function">json\_encode</span> or <span
class="function">json\_decode</span> call, which did not specify
**`JSON_THROW_ON_ERROR`**.

### Parameters

This function has no parameters.

### Return Values

Returns the error message on success, or *"No error"* if no error has
occurred.

### See Also

-   <span class="function">json\_last\_error</span>

json\_last\_error
=================

Returns the last error occurred

### Description

<span class="type">int</span> <span
class="methodname">json\_last\_error</span> ( <span
class="methodparam">void</span> )

Returns the last error (if any) occurred during the last JSON
encoding/decoding, which did not specify **`JSON_THROW_ON_ERROR`**.

### Parameters

This function has no parameters.

### Return Values

Returns an integer, the value can be one of the following constants:

| Constant                               | Meaning                                                                                                                                                                                                                                                   | Availability |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| **`JSON_ERROR_NONE`**                  | No error has occurred                                                                                                                                                                                                                                     |              |
| **`JSON_ERROR_DEPTH`**                 | The maximum stack depth has been exceeded                                                                                                                                                                                                                 |              |
| **`JSON_ERROR_STATE_MISMATCH`**        | Invalid or malformed JSON                                                                                                                                                                                                                                 |              |
| **`JSON_ERROR_CTRL_CHAR`**             | Control character error, possibly incorrectly encoded                                                                                                                                                                                                     |              |
| **`JSON_ERROR_SYNTAX`**                | Syntax error                                                                                                                                                                                                                                              |              |
| **`JSON_ERROR_UTF8`**                  | Malformed UTF-8 characters, possibly incorrectly encoded                                                                                                                                                                                                  | PHP 5.3.3    |
| **`JSON_ERROR_RECURSION`**             | One or more recursive references in the value to be encoded                                                                                                                                                                                               | PHP 5.5.0    |
| **`JSON_ERROR_INF_OR_NAN`**            | One or more <a href="/language/types/float.html#language.types.float.nan" class="link"><strong><code>NAN</code></strong></a> or <a href="/ref/math.html#is_infinite" class="link"><strong><code>INF</code></strong></a> values in the value to be encoded | PHP 5.5.0    |
| **`JSON_ERROR_UNSUPPORTED_TYPE`**      | A value of a type that cannot be encoded was given                                                                                                                                                                                                        | PHP 5.5.0    |
| **`JSON_ERROR_INVALID_PROPERTY_NAME`** | A property name that cannot be encoded was given                                                                                                                                                                                                          | PHP 7.0.0    |
| **`JSON_ERROR_UTF16`**                 | Malformed UTF-16 characters, possibly incorrectly encoded                                                                                                                                                                                                 | PHP 7.0.0    |

### Examples

**Example \#1 <span class="function">json\_last\_error</span> example**

``` php
<?php
// A valid json string
$json[] = '{"Organization": "PHP Documentation Team"}';

// An invalid json string which will cause an syntax 
// error, in this case we used ' instead of " for quotation
$json[] = "{'Organization': 'PHP Documentation Team'}";


foreach ($json as $string) {
    echo 'Decoding: ' . $string;
    json_decode($string);

    switch (json_last_error()) {
        case JSON_ERROR_NONE:
            echo ' - No errors';
        break;
        case JSON_ERROR_DEPTH:
            echo ' - Maximum stack depth exceeded';
        break;
        case JSON_ERROR_STATE_MISMATCH:
            echo ' - Underflow or the modes mismatch';
        break;
        case JSON_ERROR_CTRL_CHAR:
            echo ' - Unexpected control character found';
        break;
        case JSON_ERROR_SYNTAX:
            echo ' - Syntax error, malformed JSON';
        break;
        case JSON_ERROR_UTF8:
            echo ' - Malformed UTF-8 characters, possibly incorrectly encoded';
        break;
        default:
            echo ' - Unknown error';
        break;
    }

    echo PHP_EOL;
}
?>
```

The above example will output:

    Decoding: {"Organization": "PHP Documentation Team"} - No errors
    Decoding: {'Organization': 'PHP Documentation Team'} - Syntax error, malformed JSON

**Example \#2 <span class="function">json\_last\_error</span> with <span
class="function">json\_encode</span>**

``` php
<?php
// An invalid UTF8 sequence
$text = "\xB1\x31";

$json  = json_encode($text);
$error = json_last_error();

var_dump($json, $error === JSON_ERROR_UTF8);
?>
```

The above example will output:

    string(4) "null"
    bool(true)

**Example \#3 <span class="function">json\_last\_error</span> and
**`JSON_THROW_ON_ERROR`****

``` php
<?php
// An invalid UTF8 sequence which causes JSON_ERROR_UTF8
json_encode("\xB1\x31");

// The following does not cause a JSON error
json_encode('okay', JSON_THROW_ON_ERROR);

// The global error state has not been changed by the former json_encode()
var_dump(json_last_error() === JSON_ERROR_UTF8);
?>
```

The above example will output:

    bool(true)

### See Also

-   <span class="function">json\_last\_error\_msg</span>
-   <span class="function">json\_decode</span>
-   <span class="function">json\_encode</span>

**Table of Contents**

-   [json\_decode](/ref/json.html#json_decode) — Decodes a JSON string
-   [json\_encode](/ref/json.html#json_encode) — Returns the JSON
    representation of a value
-   [json\_last\_error\_msg](/ref/json.html#json_last_error_msg) —
    Returns the error string of the last json\_encode() or
    json\_decode() call
-   [json\_last\_error](/ref/json.html#json_last_error) — Returns the
    last error occurred
