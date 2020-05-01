User Submitted Data
===================

The greatest weakness in many PHP programs is not inherent in the
language itself, but merely an issue of code not being written with
security in mind. For this reason, you should always take the time to
consider the implications of a given piece of code, to ascertain the
possible damage if an unexpected variable is submitted to it.

**Example \#1 Dangerous Variable Usage**

``` php
<?php
// remove a file from the user's home directory... or maybe
// somebody else's?
unlink ($evil_var);

// Write logging of their access... or maybe an /etc/passwd entry?
fwrite ($fp, $evil_var);

// Execute something trivial.. or rm -rf *?
system ($evil_var);
exec ($evil_var);

?>
```

You should always carefully examine your code to make sure that any
variables being submitted from a web browser are being properly checked,
and ask yourself the following questions:

-   <span class="simpara"> Will this script only affect the intended
    files? </span>
-   <span class="simpara"> Can unusual or undesirable data be acted
    upon? </span>
-   <span class="simpara"> Can this script be used in unintended ways?
    </span>
-   <span class="simpara"> Can this be used in conjunction with other
    scripts in a negative manner? </span>
-   <span class="simpara"> Will any transactions be adequately logged?
    </span>

By adequately asking these questions while writing the script, rather
than later, you prevent an unfortunate re-write when you need to
increase your security. By starting out with this mindset, you won't
guarantee the security of your system, but you can help improve it.

You may also want to consider turning off register\_globals,
magic\_quotes, or other convenience settings which may confuse you as to
the validity, source, or value of a given variable. Working with PHP in
error\_reporting(E\_ALL) mode can also help warn you about variables
being used before they are checked or initialized (so you can prevent
unusual data from being operated upon).
