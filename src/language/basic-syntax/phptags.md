PHP tags
--------

When PHP parses a file, it looks for opening and closing tags, which are
*\<?php* and *?\>* which tell PHP to start and stop interpreting the
code between them. Parsing in this manner allows PHP to be embedded in
all sorts of different documents, as everything outside of a pair of
opening and closing tags is ignored by the PHP parser.

PHP includes a short echo tag *\<?=* which is a short-hand to the more
verbose `<?php echo`.

**Example \#1 PHP Opening and Closing Tags**

``` php
1.  <?php echo 'if you want to serve PHP code in XHTML or XML documents,
                use these tags'; ?>

2.  You can use the short echo tag to <?= 'print this string' ?>.
    It's equivalent to <?php echo 'print this string' ?>.

3.  <? echo 'this code is within short tags, but will only work '.
            'if short_open_tag is enabled'; ?>
```

Short tags (example three) are available by default but can be disabled
either via the
<a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
`php.ini` configuration file directive, or are disabled by default if
PHP is built with the **--disable-short-tags** configuration.

> **Note**:
>
> As short tags can be disabled it is recommened to only use the normal
> tags (`<?php ?>` and `<?= ?>`) to maximise compatibility.

If a file contains only PHP code, it is preferable to omit the PHP
closing tag at the end of the file. This prevents accidental whitespace
or new lines being added after the PHP closing tag, which may cause
unwanted effects because PHP will start output buffering when there is
no intention from the programmer to send any output at that point in the
script.

``` php
<?php
echo "Hello world";

// ... more code

echo "Last statement";

// the script ends here with no PHP closing tag
```
