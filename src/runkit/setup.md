Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/runkit/setup.html#Requirements)
-   [Installation](/runkit/setup.html#Installation)
-   [Runtime Configuration](/runkit/setup.html#Runtime%20Configuration)
-   [Resource Types](/runkit/setup.html#Resource%20Types)

Requirements
------------

*Modifying Constants, Functions, Classes, and Methods* as well as
*Custom Superglobals* works with all releases of PHP 5. No special
requirements are necessary.

*Sandboxing* requires PHP 5.1.0 or later, or PHP 5.0.0 with a special
TSRM patch applied. Regardless of which version of PHP is in use it must
be compiled with the *--enable-maintainer-zts* option. See the *README*
file in the runkit package for additional information.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/runkit" class="link external">» https://pecl.php.net/package/runkit</a>.

Windows binaries (DLL files) for this PECL extension are available from
the PECL website.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                    | Default | Changeable       | Changelog |
|-------------------------------------------------------------------------|---------|------------------|-----------|
| <a href="/runkit/setup.html#" class="link">runkit.superglobal</a>       | ""      | PHP\_INI\_PERDIR |           |
| <a href="/runkit/setup.html#" class="link">runkit.internal_override</a> | "0"     | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`runkit.superglobal` <span class="type">string</span>  
<span class="simpara"> Comma-separated list of variable names to be
treated as superglobals. This value should be set in the systemwide
php.ini file, but may work in perdir configuration contexts depending on
your SAPI. </span>

**Example \#1 Custom Superglobals with runkit.superglobal=\_FOO,\_BAR in
php.ini**

``` php
<?php
function show_values() {
  echo "Foo is $_FOO\n";
  echo "Bar is $_BAR\n";
  echo "Baz is $_BAZ\n";
}

$_FOO = 'foo';
$_BAR = 'bar';
$_BAZ = 'baz';

/* Displays foo and bar, but not baz */
show_values();
?>
```

`runkit.internal_override` <span class="type">boolean</span>  
<span class="simpara"> Enables ability to modify/rename/remove internal
functions. </span>

Resource Types
--------------

This extension has no resource types defined.
