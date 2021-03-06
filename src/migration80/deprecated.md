Deprecated Features
-------------------

### PHP Core

-   If a parameter with a default value is followed by a required
    parameter, the default value has no effect. This is deprecated as of
    PHP 8.0.0 and can generally be resolved by dropping the default
    value, without a change in functionality:

    ``` php
    <?php
    function test($a = [], $b) {} // Before
    function test($a, $b) {}      // After
    ?>
    ```

    One exception to this rule are parameters of the form
    `Type $param = null`, where the null default makes the type
    implicitly nullable. This usage remains allowed, but it is
    recommended to use an explicit nullable type instead:

    ``` php
    <?php
    function test(A $a = null, $b) {} // Still allowed
    function test(?A $a, $b) {}       // Recommended
    ?>
    ```

-   Calling <span class="function">get\_defined\_functions</span> with
    `exclude_disabled` explicitly set to **`false`** is deprecated and
    no longer has an effect. <span
    class="function">get\_defined\_functions</span> will never include
    disabled functions.

### Enchant

-   <span class="function">enchant\_broker\_set\_dict\_path</span> and
    <span class="function">enchant\_broker\_get\_dict\_path</span> are
    deprecated, because that functionality is neither available in
    libenchant \< 1.5 nor in libenchant-2.

-   <span class="function">enchant\_dict\_add\_to\_personal</span> is
    deprecated; use <span class="function">enchant\_dict\_add</span>
    instead.

-   <span class="function">enchant\_dict\_is\_in\_session</span> is
    deprecated; use <span
    class="function">enchant\_dict\_is\_added</span> instead.

-   <span class="function">enchant\_broker\_free</span> and <span
    class="function">enchant\_broker\_free\_dict</span> are deprecated;
    unset the object instead.

-   The **`ENCHANT_MYSPELL`** and **`ENCHANT_ISPELL`** constants are
    deprecated.

### LibXML

<span class="function">libxml\_disable\_entity\_loader</span> has been
deprecated. As libxml 2.9.0 is now required, external entity loading is
guaranteed to be disabled by default, and this function is no longer
needed to protect against XXE attacks.

### PGSQL / PDO PGSQL

-   The constant **`PG_VERSION_STR`** now has the same value as
    **`PG_VERSION`**, and thus is deprecated.

-   Function aliases in the pgsql extension have been deprecated. See
    the following list for which functions should be used instead:

    -   <span class="function">pg\_errormessage</span> → <span
        class="function">pg\_last\_error</span>
    -   <span class="function">pg\_numrows</span> → <span
        class="function">pg\_num\_rows</span>
    -   <span class="function">pg\_numfields</span> → <span
        class="function">pg\_num\_fields</span>
    -   <span class="function">pg\_cmdtuples</span> → <span
        class="function">pg\_affected\_rows</span>
    -   <span class="function">pg\_fieldname</span> → <span
        class="function">pg\_field\_name</span>
    -   <span class="function">pg\_fieldsize</span> → <span
        class="function">pg\_field\_size</span>
    -   <span class="function">pg\_fieldtype</span> → <span
        class="function">pg\_field\_type</span>
    -   <span class="function">pg\_fieldnum</span> → <span
        class="function">pg\_field\_num</span>
    -   <span class="function">pg\_result</span> → <span
        class="function">pg\_fetch\_result</span>
    -   <span class="function">pg\_fieldprtlen</span> → <span
        class="function">pg\_field\_prtlen</span>
    -   <span class="function">pg\_fieldisnull</span> → <span
        class="function">pg\_field\_is\_null</span>
    -   <span class="function">pg\_freeresult</span> → <span
        class="function">pg\_free\_result</span>
    -   <span class="function">pg\_getlastoid</span> → <span
        class="function">pg\_last\_oid</span>
    -   <span class="function">pg\_locreate</span> → <span
        class="function">pg\_lo\_create</span>
    -   <span class="function">pg\_lounlink</span> → <span
        class="function">pg\_lo\_unlink</span>
    -   <span class="function">pg\_loopen</span> → <span
        class="function">pg\_lo\_open</span>
    -   <span class="function">pg\_loclose</span> → <span
        class="function">pg\_lo\_close</span>
    -   <span class="function">pg\_loread</span> → <span
        class="function">pg\_lo\_read</span>
    -   <span class="function">pg\_lowrite</span> → <span
        class="function">pg\_lo\_write</span>
    -   <span class="function">pg\_loreadall</span> → <span
        class="function">pg\_lo\_read\_all</span>
    -   <span class="function">pg\_loimport</span> → <span
        class="function">pg\_lo\_import</span>
    -   <span class="function">pg\_loexport</span> → <span
        class="function">pg\_lo\_export</span>
    -   <span class="function">pg\_setclientencoding</span> → <span
        class="function">pg\_set\_client\_encoding</span>
    -   <span class="function">pg\_clientencoding</span> -\> <span
        class="function">pg\_client\_encoding</span>

### Standard Library

-   Sort comparison functions that return **`true`** or **`false`** will
    now throw a deprecation warning, and should be replaced with an
    implementation that returns an integer less than, equal to, or
    greater than zero.

    ``` php
    <?php
    // Replace
    usort($array, fn($a, $b) => $a > $b);
    // With
    usort($array, fn($a, $b) => $a <=> $b);
    ?>
    ```

### Zip

-   Using an empty file as ZipArchive is deprecated. Libzip 1.6.0 does
    not accept empty files as valid zip archives any longer. The
    existing workaround will be removed in the next version.

-   The procedural API of Zip is deprecated. Use <span
    class="classname">ZipArchive</span> instead. Iteration over all
    entries can be accomplished using <span
    class="methodname">ZipArchive::statIndex</span> and a
    <a href="/control-structures/for.html" class="link">for</a> loop:

    ``` php
    <?php
    // iterate using the procedural API
    assert(is_resource($zip));
    while ($entry = zip_read($zip)) {
        echo zip_entry_name($entry);
    }

    // iterate using the object-oriented API
    assert($zip instanceof ZipArchive);
    for ($i = 0; $entry = $zip->statIndex($i); $i++) {
        echo $entry['name'];
    }
    ?>
    ```

### Reflection

-   <span class="methodname">ReflectionFunction::isDisabled</span> is
    deprecated, as it is no longer possible to create a <span
    class="classname">ReflectionFunction</span> for a disabled function.
    This method now always returns **`false`**.

-   <span class="methodname">ReflectionParameter::getClass</span>, <span
    class="methodname">ReflectionParameter::isArray</span>, and <span
    class="methodname">ReflectionParameter::isCallable</span> are
    deprecated. <span
    class="methodname">ReflectionParameter::getType</span> and the <span
    class="classname">ReflectionType</span> APIs should be used instead.
