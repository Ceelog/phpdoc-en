Escaping from HTML
------------------

Everything outside of a pair of opening and closing tags is ignored by
the PHP parser which allows PHP files to have mixed content. This allows
PHP to be embedded in HTML documents, for example to create templates.

``` php
<p>This is going to be ignored by PHP and displayed by the browser.</p>
<?php echo 'While this is going to be parsed.'; ?>
<p>This will also be ignored by PHP and displayed by the browser.</p>
```

This works as expected, because when the PHP interpreter hits the ?\>
closing tags, it simply starts outputting whatever it finds (except for
an immediately following newline - see
<a href="/language/basic-syntax/instruction-separation.html" class="link">instruction separation</a>)
until it hits another opening tag unless in the middle of a conditional
statement in which case the interpreter will determine the outcome of
the conditional before making a decision of what to skip over. See the
next example.

Using structures with conditions

**Example \#1 Advanced escaping using conditions**

``` php
<?php if ($expression == true): ?>
  This will show if the expression is true.
<?php else: ?>
  Otherwise this will show.
<?php endif; ?>
```

In this example PHP will skip the blocks where the condition is not met,
even though they are outside of the PHP open/close tags; PHP skips them
according to the condition since the PHP interpreter will jump over
blocks contained within a condition that is not met.

For outputting large blocks of text, dropping out of PHP parsing mode is
generally more efficient than sending all of the text through <span
class="function">echo</span> or <span class="function">print</span>.

There is also the short echo tag `<?= ?>`.

> **Note**:
>
> Also note that if you are embedding PHP within XML or XHTML you will
> need to use the \<?php ?\> tags to remain compliant with standards.

**Example \#2 PHP Opening and Closing Tags**

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
