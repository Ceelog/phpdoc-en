Backward Incompatible Changes
-----------------------------

Although most existing PHP 5 code should work without changes, please
take note of some backward incompatible changes:

### Windows XP and 2003 support dropped

Support for Windows XP and 2003 has been dropped. Windows builds of PHP
now require Windows Vista or newer.

### Case insensitivity no longer locale specific

All case insensitive matching for function, class and constant names is
now performed in a locale independent manner according to ASCII rules.
This improves support for languages using the Latin alphabet with
unusual collating rules, such as Turkish and Azeri.

This may cause issues for code that uses case insensitive matches for
non-ASCII characters in multibyte character sets (including UTF-8), such
as accented characters in many European languages. If you have a
non-English, non-ASCII code base, then you will need to test that you
are not inadvertently relying on this behaviour before deploying PHP 5.5
to production systems.

### <span class="function">pack</span> and <span class="function">unpack</span> changes

Changes were made to <span class="function">pack</span> and <span
class="function">unpack</span> to make them more compatible with Perl:

-   <span class="simpara"> <span class="function">pack</span> now
    supports the "Z" format code, which behaves identically to "a".
    </span>
-   <span class="simpara"> <span class="function">unpack</span> now
    support the "Z" format code for NULL padded strings, and behaves as
    "a" did in previous versions: it will strip trailing NULL bytes.
    </span>
-   <span class="simpara"> <span class="function">unpack</span> now
    keeps trailing NULL bytes when the "a" format code is used. </span>
-   <span class="simpara"> <span class="function">unpack</span> now
    strips all trailing ASCII whitespace when the "A" format code is
    used. </span>

Writing backward compatible code that uses the "a" format code with
<span class="function">unpack</span> requires the use of <span
class="function">version\_compare</span>, due to the backward
compatibility break.

For example:

``` php
<?php
// Old code:
$data = unpack('a5', $packed);

// New code:
if (version_compare(PHP_VERSION, '5.5.0-dev', '>=')) {
  $data = unpack('Z5', $packed);
} else {
  $data = unpack('a5', $packed);
}
?>
```

### <span class="function">json\_encode</span> changes

When the `value` passed to <span class="function">json\_encode</span>
triggers a JSON encoding error, **`FALSE`** is returned instead of
partial output, unless `options` contains
**`JSON_PARTIAL_OUTPUT_ON_ERROR`**. See <span
class="function">json\_last\_error</span> for the full list of reasons
that can cause JSON encoding to fail. One of the potential failure
reasons is that `value` contains strings containing invalid UTF-8.

### *self*, *parent* and *static* are now always case insensitive

Prior to PHP 5.5, cases existed where the
<a href="/language/oop5/paamayim-nekudotayim.html" class="link">self</a>,
<a href="/language/oop5/paamayim-nekudotayim.html" class="link">parent</a>,
and
<a href="/language/oop5/late-static-bindings.html" class="link">static</a>
keywords were treated in a case sensitive fashion. These have now been
resolved, and these keywords are always handled case insensitively:
*SELF::CONSTANT* is now treated identically to *self::CONSTANT*.

### PHP logo GUIDs removed

The GUIDs that previously resulted in PHP outputting various logos have
been removed. This includes the removal of the functions to return those
GUIDs. The removed functions are:

-   <span class="simpara"> <span class="function">php\_logo\_guid</span>
    </span>
-   <span class="simpara"> <span
    class="function">php\_egg\_logo\_guid</span> </span>
-   <span class="simpara"> <span
    class="function">php\_real\_logo\_guid</span> </span>
-   <span class="simpara"> <span
    class="function">zend\_logo\_guid</span> </span>

### Internal execution changes

Extension authors should note that the **zend\_execute()** function can
no longer be overridden, and that numerous changes have been made to the
*execute\_data* struct and related function and method handling opcodes.

Most extension authors are unlikely to be affected, but those writing
extensions that hook deeply into the Zend Engine should read
<a href="/migration55/internals.html" class="link">the notes on these changes</a>.
