Generator::key
==============

Get the yielded key

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Generator::key</span> ( <span
class="methodparam">void</span> )

Gets the key of the yielded value.

### Parameters

This function has no parameters.

### Return Values

Returns the yielded key.

### Examples

**Example \#1 <span class="methodname">Generator::key</span> example**

``` php
<?php

function Gen()
{
    yield 'key' => 'value';
}

$gen = Gen();

echo "{$gen->key()} => {$gen->current()}";
```

The above example will output:

    key => value
