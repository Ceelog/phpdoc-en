include
-------

The *include* statement includes and evaluates the specified file.

The documentation below also applies to <span
class="function">require</span>.

Files are included based on the file path given or, if none is given,
the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
specified. If the file isn't found in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>,
*include* will finally check in the calling script's own directory and
the current working directory before failing. The *include* construct
will emit an **`E_WARNING`** if it cannot find a file; this is different
behavior from <span class="function">require</span>, which will emit an
**`E_ERROR`**.

Note that both *include* and *require* raise additional
**`E_WARNING`**s, if the file cannot be accessed, before raising the
final **`E_WARNING`** or **`E_ERROR`**, respectively.

If a path is defined — whether absolute (starting with a drive letter or
*\\* on Windows, or */* on Unix/Linux systems) or relative to the
current directory (starting with *.* or *..*) — the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
will be ignored altogether. For example, if a filename begins with
*../*, the parser will look in the parent directory to find the
requested file.

For more information on how PHP handles including files and the include
path, see the documentation for
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.

When a file is included, the code it contains inherits the
<a href="/language/variables/scope.html" class="link">variable scope</a>
of the line on which the include occurs. Any variables available at that
line in the calling file will be available within the called file, from
that point forward. However, all functions and classes defined in the
included file have the global scope.

**Example \#1 Basic *include* example**

``` php
vars.php
<?php

$color = 'green';
$fruit = 'apple';

?>

test.php
<?php

echo "A $color $fruit"; // A

include 'vars.php';

echo "A $color $fruit"; // A green apple

?>
```

If the include occurs inside a function within the calling file, then
all of the code contained in the called file will behave as though it
had been defined inside that function. So, it will follow the variable
scope of that function. An exception to this rule are
<a href="/language/constants/predefined.html" class="link">magic constants</a>
which are evaluated by the parser before the include occurs.

**Example \#2 Including within functions**

``` php
<?php

function foo()
{
    global $color;

    include 'vars.php';

    echo "A $color $fruit";
}

/* vars.php is in the scope of foo() so     *
* $fruit is NOT available outside of this  *
* scope.  $color is because we declared it *
* as global.                               */

foo();                    // A green apple
echo "A $color $fruit";   // A green

?>
```

When a file is included, parsing drops out of PHP mode and into HTML
mode at the beginning of the target file, and resumes again at the end.
For this reason, any code inside the target file which should be
executed as PHP code must be enclosed within
<a href="/language/basic-syntax/phpmode.html" class="link">valid PHP start and end tags</a>.

If
"<a href="/filesystem/setup.html#" class="link">URL include wrappers</a>"
are enabled in PHP, you can specify the file to be included using a URL
(via HTTP or other supported wrapper - see
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for a list of protocols) instead of a local pathname. If the target
server interprets the target file as PHP code, variables may be passed
to the included file using a URL request string as used with HTTP GET.
This is not strictly speaking the same thing as including the file and
having it inherit the parent file's variable scope; the script is
actually being run on the remote server and the result is then being
included into the local script.

**Example \#3 *include* through HTTP**

``` php
<?php

/* This example assumes that www.example.com is configured to parse .php
* files and not .txt files. Also, 'Works' here means that the variables
* $foo and $bar are available within the included file. */

// Won't work; file.txt wasn't handled by www.example.com as PHP
include 'http://www.example.com/file.txt?foo=1&bar=2';

// Won't work; looks for a file named 'file.php?foo=1&bar=2' on the
// local filesystem.
include 'file.php?foo=1&bar=2';

// Works.
include 'http://www.example.com/file.php?foo=1&bar=2';
?>
```

**Warning**

Remote file may be processed at the remote server (depending on the file
extension and the fact if the remote server runs PHP or not) but it
still has to produce a valid PHP script because it will be processed at
the local server. If the file from the remote server should be processed
there and outputted only, <span class="function">readfile</span> is much
better function to use. Otherwise, special care should be taken to
secure the remote script to produce a valid and desired code.

See also
<a href="/features/remote-files.html" class="link">Remote files</a>,
<span class="function">fopen</span> and <span
class="function">file</span> for related information.

Handling Returns: *include* returns *FALSE* on failure and raises a
warning. Successful includes, unless overridden by the included file,
return *1*. It is possible to execute a <span
class="function">return</span> statement inside an included file in
order to terminate processing in that file and return to the script
which called it. Also, it's possible to return values from included
files. You can take the value of the include call as you would for a
normal function. This is not, however, possible when including remote
files unless the output of the remote file has
<a href="/language/basic-syntax/phpmode.html" class="link">valid PHP start and end tags</a>
(as with any local file). You can declare the needed variables within
those tags and they will be introduced at whichever point the file was
included.

Because *include* is a special language construct, parentheses are not
needed around its argument. Take care when comparing return value.

**Example \#4 Comparing return value of include**

``` php
<?php
// won't work, evaluated as include(('vars.php') == TRUE), i.e. include('1')
if (include('vars.php') == TRUE) {
    echo 'OK';
}

// works
if ((include 'vars.php') == TRUE) {
    echo 'OK';
}
?>
```

**Example \#5 *include* and the <span class="function">return</span>
statement**

``` php
return.php
<?php

$var = 'PHP';

return $var;

?>

noreturn.php
<?php

$var = 'PHP';

?>

testreturns.php
<?php

$foo = include 'return.php';

echo $foo; // prints 'PHP'

$bar = include 'noreturn.php';

echo $bar; // prints 1

?>
```

*$bar* is the value *1* because the include was successful. Notice the
difference between the above examples. The first uses <span
class="function">return</span> within the included file while the other
does not. If the file can't be included, **`false`** is returned and
**`E_WARNING`** is issued.

If there are functions defined in the included file, they can be used in
the main file independent if they are before <span
class="function">return</span> or after. If the file is included twice,
PHP will raise a fatal error because the functions were already
declared. It is recommended to use <span
class="function">include\_once</span> instead of checking if the file
was already included and conditionally return inside the included file.

Another way to "include" a PHP file into a variable is to capture the
output by using the
<a href="/ref/outcontrol.html" class="link">Output Control Functions</a>
with *include*. For example:

**Example \#6 Using output buffering to include a PHP file into a
string**

``` php
<?php
$string = get_include_contents('somefile.php');

function get_include_contents($filename) {
    if (is_file($filename)) {
        ob_start();
        include $filename;
        return ob_get_clean();
    }
    return false;
}

?>
```

In order to automatically include files within scripts, see also the
<a href="/ini/core.html#ini.auto-prepend-file" class="link">auto_prepend_file</a>
and
<a href="/ini/core.html#ini.auto-append-file" class="link">auto_append_file</a>
configuration options in `php.ini`.

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

See also <span class="function">require</span>, <span
class="function">require\_once</span>, <span
class="function">include\_once</span>, <span
class="function">get\_included\_files</span>, <span
class="function">readfile</span>, <span class="function">virtual</span>,
and
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.
