Miscellaneous Questions
=======================

There can be some questions we can't put into other categories. Here you
can find them.

1.  [How can I handle the bz2 compressed manuals on
    Windows?](#faq.misc.bz2)
2.  [What does & beside argument mean in function declaration of e.g.
    asort?](#faq.misc.arguments.references)
3.  [How do I deal with register\_globals?](#faq.misc.registerglobals)

**How can I handle the bz2 compressed manuals on Windows?**  
If you don't have an archiver-tool to handle bz2 files
<a href="https://www.sourceware.org/bzip2/" class="link external">» download</a>
the command line tool from Redhat (please find further information
below).

If you would not like to use a command line tool, you can try free tools
like
<a href="http://www.stuffit.com/" class="link external">» Stuffit Expander</a>,
<a href="http://www.ultimatezip.com/" class="link external">» UltimateZip</a>,
<a href="http://www.7-zip.org/" class="link external">» 7-Zip</a>, or
<a href="http://www.quickzip.org/" class="link external">» Quick Zip</a>.
If you have tools like
<a href="http://www.rarlab.com/" class="link external">» WinRAR</a> or
<a href="http://www.powerarchiver.com/" class="link external">» Power Archiver</a>,
you can easily decompress the bz2 files with it. If you use Total
Commander (formerly Windows Commander), a bz2 plugin for that program is
available freely from the
<a href="http://www.ghisler.com/" class="link external">» Total Commander</a>
site.

The bzip2 command line tool from Redhat:

Win2k Sp2 users grab the latest version 1.0.2, all other Windows user
should grab version 1.00. After downloading rename the executable to
bzip2.exe. For convenience put it into a directory in your path, e.g.
C:\\Windows where C represents your Windows installation drive.

Note: lang stands for your language and x for the desired format, e.g.:
pdf. To uncompress the php\_manual\_lang.x.bz2 follow these simple
instructions:

-   <span class="simpara">open a command prompt window</span>
-   <span class="simpara"> cd to the folder where you stored the
    downloaded php\_manual\_lang.x.bz2 </span>
-   <span class="simpara"> invoke bzip2 -d php\_manual\_lang.x.bz2,
    extracting php\_manual\_lang.x in the same folder </span>

In case you downloaded the php\_manual\_lang.tar.bz2 with many
html-files in it, the procedure is the same. The only difference is that
you got a file php\_manual\_lang.tar. The tar format is known to be
treated with most common archivers on Windows like e.g.
<a href="http://www.winzip.com/" class="link external">» WinZip</a>.

<!-- -->

**What does & beside argument mean in function declaration of e.g. <span class="function">asort</span>?**  
It means that the argument is
<a href="/language/references/pass.html" class="link">passed by reference</a>
and the function will likely modify it corresponding to the
documentation. You can pass only variables this way and you don't need
to pass them with & in function call (it's even
<a href="/ini/core.html#ini.allow-call-time-pass-reference" class="link">deprecated</a>).

<!-- -->

**How do I deal with *register\_globals*?**  
For information about the security implications of *register\_globals*,
read the security chapter on
<a href="/security/globals.html" class="link">Using register_globals</a>.

It's preferred to use
<a href="/language/variables/superglobals.html" class="link">superglobals</a>,
rather than relying upon *register\_globals* being on.

If you are on a shared host with *register\_globals* turned off and need
to use some legacy applications, which require this option to be turned
on, or you are on some hosting server, where this feature is turned on,
but you would like to eliminate security risks, you might need to
emulate the opposite setting with PHP. It is always a good idea to first
ask if it would be possible to change the option somehow in PHP's
configuration, but if it is not possible, then you can use these
compatibility snippets.

**Example \#1 Emulating Register Globals**

This will emulate register\_globals On. If you altered your
<a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
directive, consider changing the `$superglobals` accordingly.

``` php
<?php
// Emulate register_globals on
if (!ini_get('register_globals')) {
    $superglobals = array($_SERVER, $_ENV,
        $_FILES, $_COOKIE, $_POST, $_GET);
    if (isset($_SESSION)) {
        array_unshift($superglobals, $_SESSION);
    }
    foreach ($superglobals as $superglobal) {
        extract($superglobal, EXTR_SKIP);
    }
}
?>
```

This will emulate register\_globals Off. Keep in mind, that this code
should be called at the very beginning of your script, or after <span
class="function">session\_start</span> if you use it to start your
session.

``` php
<?php
// Emulate register_globals off
function unregister_GLOBALS()
{
    if (!ini_get('register_globals')) {
        return;
    }

    // Might want to change this perhaps to a nicer error
    if (isset($_REQUEST['GLOBALS']) || isset($_FILES['GLOBALS'])) {
        die('GLOBALS overwrite attempt detected');
    }

    // Variables that shouldn't be unset
    $noUnset = array('GLOBALS',  '_GET',
                     '_POST',    '_COOKIE',
                     '_REQUEST', '_SERVER',
                     '_ENV',     '_FILES');

    $input = array_merge($_GET,    $_POST,
                         $_COOKIE, $_SERVER,
                         $_ENV,    $_FILES,
                         isset($_SESSION) && is_array($_SESSION) ? $_SESSION : array());
    
    foreach ($input as $k => $v) {
        if (!in_array($k, $noUnset) && isset($GLOBALS[$k])) {
            unset($GLOBALS[$k]);
        }
    }
}

unregister_GLOBALS();

?>
```
