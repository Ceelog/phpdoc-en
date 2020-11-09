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
the immediately following newline - see
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

> **Note**:
>
> If PHP is embeded within XML or XHTML the normal PHP `<?php ?>` must
> be used to remain compliant with the standards.
