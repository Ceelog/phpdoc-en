Internal (built-in) functions
-----------------------------

PHP comes standard with many functions and constructs. There are also
functions that require specific PHP extensions compiled in, otherwise
fatal "undefined function" errors will appear. For example, to use
<a href="/ref/image.html" class="link">image</a> functions such as <span
class="function">imagecreatetruecolor</span>, PHP must be compiled with
<span class="productname">GD</span> support. Or, to use <span
class="function">mysqli\_connect</span>, PHP must be compiled with
<a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a> support.
There are many core functions that are included in every version of PHP,
such as the <a href="/ref/strings.html" class="link">string</a> and
<a href="/ref/var.html" class="link">variable</a> functions. A call to
<span class="function">phpinfo</span> or <span
class="function">get\_loaded\_extensions</span> will show which
extensions are loaded into PHP. Also note that many extensions are
enabled by default and that the PHP manual is split up by extension. See
the <a href="/configuration.html" class="link">configuration</a>,
<a href="/install.html" class="link">installation</a>, and individual
extension chapters, for information on how to set up PHP.

Reading and understanding a function's prototype is explained within the
manual section titled
<a href="/about/prototypes.html" class="link">how to read a function definition</a>.
It's important to realize what a function returns or if a function works
directly on a passed in value. For example, <span
class="function">str\_replace</span> will return the modified string
while <span class="function">usort</span> works on the actual passed in
variable itself. Each manual page also has specific information for each
function like information on function parameters, behavior changes,
return values for both success and failure, and availability
information. Knowing these important (yet often subtle) differences is
crucial for writing correct PHP code.

> **Note**: <span class="simpara"> If the parameters given to a function
> are not what it expects, such as passing an <span
> class="type">array</span> where a <span class="type">string</span> is
> expected, the return value of the function is undefined. In this case
> it will likely return **`NULL`** but this is just a convention, and
> cannot be relied upon. </span>

### See Also

-   <span class="function">function\_exists</span>
-   <a href="/funcref.html" class="link">the function reference</a>
-   <span class="function">get\_extension\_funcs</span>
-   <span class="function">dl</span>
