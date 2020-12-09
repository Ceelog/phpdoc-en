Returning values
----------------

Values are returned by using the optional return statement. Any type may
be returned, including arrays and objects. This causes the function to
end its execution immediately and pass control back to the line from
which it was called. See <span class="function">return</span> for more
information.

> **Note**:
>
> If the <span class="function">return</span> is omitted the value
> **`null`** will be returned.

### Use of return

**Example \#1 Use of <span class="function">return</span>**

``` php
<?php
function square($num)
{
    return $num * $num;
}
echo square(4);   // outputs '16'.
?>
```

A function can not return multiple values, but similar results can be
obtained by returning an array.

**Example \#2 Returning an array to get multiple values**

``` php
<?php
function small_numbers()
{
    return array (0, 1, 2);
}
list ($zero, $one, $two) = small_numbers();
?>
```

To return a reference from a function, use the reference operator & in
both the function declaration and when assigning the returned value to a
variable:

**Example \#3 Returning a reference from a function**

``` php
<?php
function &returns_reference()
{
    return $someref;
}

$newref =& returns_reference();
?>
```

For more information on references, please check out
<a href="/language/references.html" class="link">References Explained</a>.
