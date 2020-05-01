Execution Operators
-------------------

PHP supports one execution operator: backticks (\`\`). Note that these
are not single-quotes! PHP will attempt to execute the contents of the
backticks as a shell command; the output will be returned (i.e., it
won't simply be dumped to output; it can be assigned to a variable). Use
of the backtick operator is identical to <span
class="function">shell\_exec</span>.

``` php
<?php
$output = `ls -al`;
echo "<pre>$output</pre>";
?>
```

> **Note**:
>
> The backtick operator is disabled when
> <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
> is enabled or <span class="function">shell\_exec</span> is disabled.

> **Note**:
>
> Unlike some other languages, backticks have no special meaning within
> double-quoted strings.

See also the manual section on
<a href="/ref/exec.html" class="link">Program Execution functions</a>,
<span class="function">popen</span> <span
class="function">proc\_open</span>, and
<a href="/features/commandline.html" class="link">Using PHP from the commandline</a>.
