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

In PHP 5, there are up to five different pairs of opening and closing
tags available in PHP, depending on how PHP is configured. Two of these,
`<?php ?>` and `<script language="php"> </script>`, are always
available. There is also the short echo tag `<?= ?>`, which is always
available in PHP 5.4.0 and later.

The other two are short tags and <span class="productname">ASP</span>
style tags. As such, while some people find short tags and <span
class="productname">ASP</span> style tags convenient, they are less
portable, and generally not recommended.

> **Note**:
>
> Also note that if you are embedding PHP within XML or XHTML you will
> need to use the \<?php ?\> tags to remain compliant with standards.

PHP 7 removes support for <span class="productname">ASP</span> tags and
`<script language="php">` tags. As such, we recommend only using
`<?php ?>` and `<?= ?>` when writing PHP code to maximise compatibility.

**Example \#2 PHP Opening and Closing Tags**

``` php
1.  <?php echo 'if you want to serve PHP code in XHTML or XML documents,
                use these tags'; ?>

2.  You can use the short echo tag to <?= 'print this string' ?>.
    It's always enabled in PHP 5.4.0 and later, and is equivalent to
    <?php echo 'print this string' ?>.

3.  <? echo 'this code is within short tags, but will only work '.
            'if short_open_tag is enabled'; ?>

4.  <script language="php">
        echo 'some editors (like FrontPage) don\'t
              like processing instructions within these tags';
    </script>
    This syntax is removed in PHP 7.0.0.

5.  <% echo 'You may optionally use ASP-style tags'; %>
    Code within these tags <%= $variable; %> is a shortcut for this code <% echo $variable; %>
    Both of these syntaxes are removed in PHP 7.0.0.
```

Short tags (example three) are only available when they are enabled via
the
<a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
`php.ini` configuration file directive, or if PHP was configured with
the **--enable-short-tags** option.

<span class="productname">ASP</span> style tags (example five) are only
available when they are enabled via the
<a href="/ini/core.html#ini.asp-tags" class="link">asp_tags</a>
`php.ini` configuration file directive, and have been removed in PHP
7.0.0.

> **Note**:
>
> Using short tags should be avoided when developing applications or
> libraries that are meant for redistribution, or deployment on PHP
> servers which are not under your control, because short tags may not
> be supported on the target server. For portable, redistributable code,
> be sure not to use short tags.

> **Note**:
>
> In PHP 5.2 and earlier, the parser does not allow the *\<?php* opening
> tag to be the only thing in a file. This is allowed as of PHP 5.3
> provided there are one or more whitespace characters after the opening
> tag.

> **Note**:
>
> Starting with PHP 5.4, short echo tag *\<?=* is always recognized and
> valid, regardless of the
> <a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
> setting.
