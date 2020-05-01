ArrayAccess::offsetExists
=========================

Whether an offset exists

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">ArrayAccess::offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

Whether or not an offset exists.

This method is executed when using <span class="function">isset</span>
or <span class="function">empty</span> on objects implementing <span
class="classname">ArrayAccess</span>.

> **Note**:
>
> When using <span class="function">empty</span> <span
> class="function">ArrayAccess::offsetGet</span> will be called and
> checked if empty only if <span
> class="function">ArrayAccess::offsetExists</span> returns **`TRUE`**.

### Parameters

`offset`  
An offset to check for.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

> **Note**:
>
> The return value will be casted to <span class="type">boolean</span>
> if non-boolean was returned.

### Examples

**Example \#1 <span class="function">ArrayAccess::offsetExists</span>
example**

``` php
<?php
class obj implements arrayaccess {
    public function offsetSet($offset, $value) {
        var_dump(__METHOD__);
    }
    public function offsetExists($var) {
        var_dump(__METHOD__);
        if ($var == "foobar") {
            return true;
        }
        return false;
    }
    public function offsetUnset($var) {
        var_dump(__METHOD__);
    }
    public function offsetGet($var) {
        var_dump(__METHOD__);
        return "value";
    }
}

$obj = new obj;

echo "Runs obj::offsetExists()\n";
var_dump(isset($obj["foobar"]));

echo "\nRuns obj::offsetExists() and obj::offsetGet()\n";
var_dump(empty($obj["foobar"]));

echo "\nRuns obj::offsetExists(), *not* obj:offsetGet() as there is nothing to get\n";
var_dump(empty($obj["foobaz"]));
?>
```

The above example will output something similar to:

    Runs obj::offsetExists()
    string(17) "obj::offsetExists"
    bool(true)

    Runs obj::offsetExists() and obj::offsetGet()
    string(17) "obj::offsetExists"
    string(14) "obj::offsetGet"
    bool(false)

    Runs obj::offsetExists(), *not* obj:offsetGet() as there is nothing to get
    string(17) "obj::offsetExists"
    bool(true)
