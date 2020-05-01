parsekit\_compile\_file
=======================

Compile a PHP file and return the resulting op array

### Description

<span class="type">array</span> <span
class="methodname">parsekit\_compile\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$errors`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`<span class="initializer"> =
PARSEKIT\_QUIET</span></span> \]\] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`filename`  
A string containing the name of the file to compile. Similar to the
argument to <span class="function">include</span>.

`errors`  
A 2D hash of errors (including fatal errors) encountered during
compilation. Returned by reference.

`options`  
One of either **`PARSEKIT_QUIET`** or **`PARSEKIT_SIMPLE`**. To produce
varying degrees of verbosity in the returned output.

### Return Values

Returns a complex multi-layer array structure as detailed below.

### Examples

**Example \#1 <span class="function">parsekit\_compile\_file</span>
example**

``` php
<?php
var_dump(parsekit_compile_file('hello_world.php', $errors, PARSEKIT_SIMPLE));
?>
```

The above example will output:

    array(5) {
      [0]=>
      string(37) "ZEND_ECHO UNUSED 'Hello World' UNUSED"
      [1]=>
      string(30) "ZEND_RETURN UNUSED NULL UNUSED"
      [2]=>
      string(42) "ZEND_HANDLE_EXCEPTION UNUSED UNUSED UNUSED"
      ["function_table"]=>
      NULL
      ["class_table"]=>
      NULL
    }

### See Also

-   <span class="function">parsekit\_compile\_string</span>

parsekit\_compile\_string
=========================

Compile a string of PHP code and return the resulting op array

### Description

<span class="type">array</span> <span
class="methodname">parsekit\_compile\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$phpcode`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$errors`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`<span class="initializer"> =
PARSEKIT\_QUIET</span></span> \]\] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`phpcode`  
A string containing phpcode. Similar to the argument to <span
class="function">eval</span>.

`errors`  
A 2D hash of errors (including fatal errors) encountered during
compilation. Returned by reference.

`options`  
One of either **`PARSEKIT_QUIET`** or **`PARSEKIT_SIMPLE`**. To produce
varying degrees of verbosity in the returned output.

### Return Values

Returns a complex multi-layer array structure as detailed below.

### Examples

**Example \#1 <span class="function">parsekit\_compile\_string</span>
example**

``` php
<?php
  $ops = parsekit_compile_string('
echo "Foo\n";
', $errors, PARSEKIT_QUIET);

  var_dump($ops);
?>
```

The above example will output:

    array(20) {
      ["type"]=>
      int(4)
      ["type_name"]=>
      string(14) "ZEND_EVAL_CODE"
      ["fn_flags"]=>
      int(0)
      ["num_args"]=>
      int(0)
      ["required_num_args"]=>
      int(0)
      ["pass_rest_by_reference"]=>
      bool(false)
      ["uses_this"]=>
      bool(false)
      ["line_start"]=>
      int(0)
      ["line_end"]=>
      int(0)
      ["return_reference"]=>
      bool(false)
      ["refcount"]=>
      int(1)
      ["last"]=>
      int(3)
      ["size"]=>
      int(3)
      ["T"]=>
      int(0)
      ["last_brk_cont"]=>
      int(0)
      ["current_brk_cont"]=>
      int(-1)
      ["backpatch_count"]=>
      int(0)
      ["done_pass_two"]=>
      bool(true)
      ["filename"]=>
      string(17) "Parsekit Compiler"
      ["opcodes"]=>
      array(3) {
        [8594800]=>
        array(5) {
          ["opcode"]=>
          int(40)
          ["opcode_name"]=>
          string(9) "ZEND_ECHO"
          ["flags"]=>
          int(768)
          ["op1"]=>
          array(3) {
            ["type"]=>
            int(1)
            ["type_name"]=>
            string(8) "IS_CONST"
            ["constant"]=>
            &string(4) "Foo
    "
          }
          ["lineno"]=>
          int(2)
        }
        ["859484C"]=>
        array(6) {
          ["opcode"]=>
          int(62)
          ["opcode_name"]=>
          string(11) "ZEND_RETURN"
          ["flags"]=>
          int(16777984)
          ["op1"]=>
          array(3) {
            ["type"]=>
            int(1)
            ["type_name"]=>
            string(8) "IS_CONST"
            ["constant"]=>
            &NULL
          }
          ["extended_value"]=>
          int(0)
          ["lineno"]=>
          int(3)
        }
        [8594898]=>
        array(4) {
          ["opcode"]=>
          int(149)
          ["opcode_name"]=>
          string(21) "ZEND_HANDLE_EXCEPTION"
          ["flags"]=>
          int(0)
          ["lineno"]=>
          int(3)
        }
      }
    }

### See Also

-   <span class="function">parsekit\_compile\_file</span>

parsekit\_func\_arginfo
=======================

Return information regarding function argument(s)

### Description

<span class="type">array</span> <span
class="methodname">parsekit\_func\_arginfo</span> ( <span
class="methodparam"><span class="type">mixed</span> `$function`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`function`  
A string describing a function, or an array describing a class/method.

### Return Values

Returns an array containing argument information.

### Examples

**Example \#1 <span class="function">parsekit\_func\_arginfo</span>
example**

``` php
<?php
function foo($bar, stdClass $baz, &$bomb, $bling = false) {
}

var_dump(parsekit_func_arginfo('foo'));
?>
```

The above example will output:

    array(4) {
      [0]=>
      array(3) {
        ["name"]=>
        string(3) "bar"
        ["allow_null"]=>
        bool(true)
        ["pass_by_reference"]=>
        bool(false)
      }
      [1]=>
      array(4) {
        ["name"]=>
        string(3) "baz"
        ["class_name"]=>
        string(8) "stdClass"
        ["allow_null"]=>
        bool(false)
        ["pass_by_reference"]=>
        bool(false)
      }
      [2]=>
      array(3) {
        ["name"]=>
        string(4) "bomb"
        ["allow_null"]=>
        bool(true)
        ["pass_by_reference"]=>
        bool(true)
      }
      [3]=>
      array(3) {
        ["name"]=>
        string(5) "bling"
        ["allow_null"]=>
        bool(true)
        ["pass_by_reference"]=>
        bool(false)
      }
    }

**Table of Contents**

-   [parsekit\_compile\_file](/ref/parsekit.html#parsekit_compile_file)
    — Compile a PHP file and return the resulting op array
-   [parsekit\_compile\_string](/ref/parsekit.html#parsekit_compile_string)
    — Compile a string of PHP code and return the resulting op array
-   [parsekit\_func\_arginfo](/ref/parsekit.html#parsekit_func_arginfo)
    — Return information regarding function argument(s)
