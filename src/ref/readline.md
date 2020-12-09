readline\_add\_history
======================

Adds a line to the history

### Description

<span class="type">bool</span> <span
class="methodname">readline\_add\_history</span> ( <span
class="methodparam"><span class="type">string</span> `$prompt`</span> )

This function adds a line to the command line history.

### Parameters

`prompt`  
The line to be added in the history.

### Return Values

Returns **`true`** on success or **`false`** on failure.

readline\_callback\_handler\_install
====================================

Initializes the readline callback interface and terminal, prints the
prompt and returns immediately

### Description

<span class="type">bool</span> <span
class="methodname">readline\_callback\_handler\_install</span> ( <span
class="methodparam"><span class="type">string</span> `$prompt`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Sets up a readline callback interface then prints `prompt` and
immediately returns. Calling this function twice without removing the
previous callback interface will automatically and conveniently
overwrite the old interface.

The callback feature is useful when combined with <span
class="function">stream\_select</span> as it allows interleaving of IO
and user input, unlike <span class="function">readline</span>.

### Parameters

`prompt`  
The prompt message.

`callback`  
The `callback` function takes one parameter; the user input returned.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Readline Callback Interface Example**

``` php
<?php
function rl_callback($ret)
{
    global $c, $prompting;

    echo "You entered: $ret\n";
    $c++;

    if ($c > 10) {
        $prompting = false;
        readline_callback_handler_remove();
    } else {
        readline_callback_handler_install("[$c] Enter something: ", 'rl_callback');
    }
}

$c = 1;
$prompting = true;

readline_callback_handler_install("[$c] Enter something: ", 'rl_callback');

while ($prompting) {
    $w = NULL;
    $e = NULL;
    $n = stream_select($r = array(STDIN), $w, $e, null);
    if ($n && in_array(STDIN, $r)) {
        // read a character, will call the callback when a newline is entered
        readline_callback_read_char();
    }
}

echo "Prompting disabled. All done.\n";
?>
```

### See Also

-   <span class="function">readline\_callback\_handler\_remove</span>
-   <span class="function">readline\_callback\_read\_char</span>
-   <span class="function">stream\_select</span>

readline\_callback\_handler\_remove
===================================

Removes a previously installed callback handler and restores terminal
settings

### Description

<span class="type">bool</span> <span
class="methodname">readline\_callback\_handler\_remove</span> ( <span
class="methodparam">void</span> )

Removes a previously installed callback handler and restores terminal
settings.

### Return Values

Returns **`true`** if a previously installed callback handler was
removed, or **`false`** if one could not be found.

### Examples

See <span class="function">readline\_callback\_handler\_install</span>
for an example of how to use the readline callback interface.

### See Also

-   <span class="function">readline\_callback\_handler\_install</span>
-   <span class="function">readline\_callback\_read\_char</span>

readline\_callback\_read\_char
==============================

Reads a character and informs the readline callback interface when a
line is received

### Description

<span class="type">void</span> <span
class="methodname">readline\_callback\_read\_char</span> ( <span
class="methodparam">void</span> )

Reads a character of user input. When a line is received, this function
informs the readline callback interface installed using <span
class="function">readline\_callback\_handler\_install</span> that a line
is ready for input.

### Return Values

No value is returned.

### Examples

See <span class="function">readline\_callback\_handler\_install</span>
for an example of how to use the readline callback interface.

### See Also

-   <span class="function">readline\_callback\_handler\_install</span>
-   <span class="function">readline\_callback\_handler\_remove</span>

readline\_clear\_history
========================

Clears the history

### Description

<span class="type">bool</span> <span
class="methodname">readline\_clear\_history</span> ( <span
class="methodparam">void</span> )

This function clears the entire command line history.

### Return Values

Returns **`true`** on success or **`false`** on failure.

readline\_completion\_function
==============================

Registers a completion function

### Description

<span class="type">bool</span> <span
class="methodname">readline\_completion\_function</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

This function registers a completion function. This is the same kind of
functionality you'd get if you hit your tab key while using Bash.

### Parameters

`callback`  
You must supply the name of an existing function which accepts a partial
command line and returns an array of possible matches.

### Return Values

Returns **`true`** on success or **`false`** on failure.

readline\_info
==============

Gets/sets various internal readline variables

### Description

<span class="type">mixed</span> <span
class="methodname">readline\_info</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$var_name`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">string</span><span
class="type">bool</span><span class="type">null</span></span>
`$value`<span class="initializer"> = **`null`**</span></span> \]\] )

Gets or sets various internal readline variables.

### Parameters

`var_name`  
A variable name.

`value`  
If provided, this will be the new value of the setting.

### Return Values

If called with no parameters, this function returns an array of values
for all the setting readline uses. The elements will be indexed by the
following values: done, end, erase\_empty\_line, library\_version,
line\_buffer, mark, pending\_input, point, prompt, readline\_name, and
terminal\_name.

If called with one or two parameters, the old value is returned.

### Changelog

| Version | Description                              |
|---------|------------------------------------------|
| 8.0.0   | `var_name` and `value` are nullable now. |

readline\_list\_history
=======================

Lists the history

### Description

<span class="type">array</span> <span
class="methodname">readline\_list\_history</span> ( <span
class="methodparam">void</span> )

Gets the entire command line history.

### Return Values

Returns an array of the entire command line history. The elements are
indexed by integers starting at zero.

readline\_on\_new\_line
=======================

Inform readline that the cursor has moved to a new line

### Description

<span class="type">void</span> <span
class="methodname">readline\_on\_new\_line</span> ( <span
class="methodparam">void</span> )

Tells readline that the cursor has moved to a new line.

### Return Values

No value is returned.

readline\_read\_history
=======================

Reads the history

### Description

<span class="type">bool</span> <span
class="methodname">readline\_read\_history</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`<span class="initializer"> = **`null`**</span></span> \] )

This function reads a command history from a file.

### Parameters

`filename`  
Path to the filename containing the command history.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `filename` is nullable now. |

readline\_redisplay
===================

Redraws the display

### Description

<span class="type">void</span> <span
class="methodname">readline\_redisplay</span> ( <span
class="methodparam">void</span> )

Redraws readline to redraw the display.

### Return Values

No value is returned.

readline\_write\_history
========================

Writes the history

### Description

<span class="type">bool</span> <span
class="methodname">readline\_write\_history</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`<span class="initializer"> = **`null`**</span></span> \] )

This function writes the command history to a file.

### Parameters

`filename`  
Path to the saved file.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `filename` is nullable now. |

readline
========

Reads a line

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">readline</span> (\[ <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$prompt`<span class="initializer"> =
**`null`**</span></span> \] )

Reads a single line from the user. You must add this line to the history
yourself using <span class="function">readline\_add\_history</span>.

### Parameters

`prompt`  
You may specify a string with which to prompt the user.

### Return Values

Returns a single string from the user. The line returned has the ending
newline removed. If there is no more data to read, then **`false`** is
returned.

### Examples

**Example \#1 <span class="function">readline</span> Example**

``` php
<?php
//get 3 commands from user
for ($i=0; $i < 3; $i++) {
        $line = readline("Command: ");
        readline_add_history($line);
}

//dump history
print_r(readline_list_history());

//dump variables
print_r(readline_info());
?>
```

**Table of Contents**

-   [readline\_add\_history](/ref/readline.html#readline_add_history) —
    Adds a line to the history
-   [readline\_callback\_handler\_install](/ref/readline.html#readline_callback_handler_install)
    — Initializes the readline callback interface and terminal, prints
    the prompt and returns immediately
-   [readline\_callback\_handler\_remove](/ref/readline.html#readline_callback_handler_remove)
    — Removes a previously installed callback handler and restores
    terminal settings
-   [readline\_callback\_read\_char](/ref/readline.html#readline_callback_read_char)
    — Reads a character and informs the readline callback interface when
    a line is received
-   [readline\_clear\_history](/ref/readline.html#readline_clear_history)
    — Clears the history
-   [readline\_completion\_function](/ref/readline.html#readline_completion_function)
    — Registers a completion function
-   [readline\_info](/ref/readline.html#readline_info) — Gets/sets
    various internal readline variables
-   [readline\_list\_history](/ref/readline.html#readline_list_history)
    — Lists the history
-   [readline\_on\_new\_line](/ref/readline.html#readline_on_new_line) —
    Inform readline that the cursor has moved to a new line
-   [readline\_read\_history](/ref/readline.html#readline_read_history)
    — Reads the history
-   [readline\_redisplay](/ref/readline.html#readline_redisplay) —
    Redraws the display
-   [readline\_write\_history](/ref/readline.html#readline_write_history)
    — Writes the history
-   [readline](/ref/readline.html#readline) — Reads a line
