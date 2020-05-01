Changed functions
-----------------

### PHP Core

-   <span class="simpara"> <span
    class="function">debug\_zval\_dump</span> now prints "int" instead
    of "long", and "float" instead of "double" </span>
-   <span class="simpara"> <span class="function">dirname</span> now
    optionally takes a second parameter, `depth`, to get the name of the
    directory `depth` levels up from the current directory. </span>
-   <span class="simpara"> <span class="function">getrusage</span> is
    now supported on Windows. </span>
-   <span class="simpara"> <span class="function">mktime</span> and
    <span class="function">gmmktime</span> functions no longer accept
    `is_dst` parameter. </span>
-   <span class="simpara"> <span class="function">preg\_replace</span>
    function no longer supports "\\e" (**`PREG_REPLACE_EVAL`**). <span
    class="function">preg\_replace\_callback</span> should be used
    instead. </span>
-   <span class="simpara"> <span class="function">setlocale</span>
    function no longer accepts `category` passed as string. **`LC_*`**
    constants must be used instead. </span>
-   <span class="simpara"> <span class="function">exec</span>, <span
    class="function">system</span> and <span
    class="function">passthru</span> functions have NULL byte protection
    now. </span>
-   <span class="simpara"> <span class="function">shmop\_open</span> now
    returns a resource instead of an int, which has to be passed to
    <span class="function">shmop\_size</span>, <span
    class="function">shmop\_write</span>, <span
    class="function">shmop\_read</span>, <span
    class="function">shmop\_close</span> and <span
    class="function">shmop\_delete</span>. </span>
-   <span class="simpara"> <span class="function">substr</span> and
    <span class="function">iconv\_substr</span> now return an empty
    string, if string is equal to start characters long. </span>
-   <span class="simpara"> <span
    class="function">xml\_parser\_free</span> is no longer sufficient to
    free the parser resource, if it references an object and this object
    references that parser resource. In this case it is necessary to
    additionally unset the $parser. </span>
