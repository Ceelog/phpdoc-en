Error Reporting
===============

With PHP security, there are two sides to error reporting. One is
beneficial to increasing security, the other is detrimental.

A standard attack tactic involves profiling a system by feeding it
improper data, and checking for the kinds, and contexts, of the errors
which are returned. This allows the system cracker to probe for
information about the server, to determine possible weaknesses. For
example, if an attacker had gleaned information about a page based on a
prior form submission, they may attempt to override variables, or modify
them:

**Example \#1 Attacking Variables with a custom HTML page**

``` html
<form method="post" action="attacktarget?username=badfoo&amp;password=badfoo">
<input type="hidden" name="username" value="badfoo" />
<input type="hidden" name="password" value="badfoo" />
</form>
```

The PHP errors which are normally returned can be quite helpful to a
developer who is trying to debug a script, indicating such things as the
function or file that failed, the PHP file it failed in, and the line
number which the failure occurred in. This is all information that can
be exploited. It is not uncommon for a php developer to use <span
class="function">show\_source</span>, <span
class="function">highlight\_string</span>, or <span
class="function">highlight\_file</span> as a debugging measure, but in a
live site, this can expose hidden variables, unchecked syntax, and other
dangerous information. Especially dangerous is running code from known
sources with built-in debugging handlers, or using common debugging
techniques. If the attacker can determine what general technique you are
using, they may try to brute-force a page, by sending various common
debugging strings:

**Example \#2 Exploiting common debugging variables**

``` html
<form method="post" action="attacktarget?errors=Y&amp;showerrors=1&amp;debug=1">
<input type="hidden" name="errors" value="Y" />
<input type="hidden" name="showerrors" value="1" />
<input type="hidden" name="debug" value="1" />
</form>
```

Regardless of the method of error handling, the ability to probe a
system for errors leads to providing an attacker with more information.

For example, the very style of a generic PHP error indicates a system is
running PHP. If the attacker was looking at an .html page, and wanted to
probe for the back-end (to look for known weaknesses in the system), by
feeding it the wrong data they may be able to determine that a system
was built with PHP.

A function error can indicate whether a system may be running a specific
database engine, or give clues as to how a web page or programmed or
designed. This allows for deeper investigation into open database ports,
or to look for specific bugs or weaknesses in a web page. By feeding
different pieces of bad data, for example, an attacker can determine the
order of authentication in a script, (from the line number errors) as
well as probe for exploits that may be exploited in different locations
in the script.

A filesystem or general PHP error can indicate what permissions the web
server has, as well as the structure and organization of files on the
web server. Developer written error code can aggravate this problem,
leading to easy exploitation of formerly "hidden" information.

There are three major solutions to this issue. The first is to
scrutinize all functions, and attempt to compensate for the bulk of the
errors. The second is to disable error reporting entirely on the running
code. The third is to use PHP's custom error handling functions to
create your own error handler. Depending on your security policy, you
may find all three to be applicable to your situation.

One way of catching this issue ahead of time is to make use of PHP's own
<span class="function">error\_reporting</span>, to help you secure your
code and find variable usage that may be dangerous. By testing your
code, prior to deployment, with **`E_ALL`**, you can quickly find areas
where your variables may be open to poisoning or modification in other
ways. Once you are ready for deployment, you should either disable error
reporting completely by setting <span
class="function">error\_reporting</span> to 0, or turn off the error
display using the `php.ini` option *display\_errors*, to insulate your
code from probing. If you choose to do the latter, you should also
define the path to your log file using the *error\_log* ini directive,
and turn *log\_errors* on.

**Example \#3 Finding dangerous variables with E\_ALL**

``` php
<?php
if ($username) {  // Not initialized or checked before usage
    $good_login = 1;
}
if ($good_login == 1) { // If above test fails, not initialized or checked before usage
    readfile ("/highly/sensitive/data/index.html");
}
?>
```
