Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/trader/setup.html#Requirements)
-   [Installation](/trader/setup.html#Installation)
-   [Runtime Configuration](/trader/setup.html#Runtime%20Configuration)

Requirements
------------

The trader extension is based on
<a href="http://www.ta-lib.org/" class="link external">» TA-Lib</a>.
TA-Lib is fully integrated into the extension, therefore no external
libraries are needed.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/trader" class="link external">» https://pecl.php.net/package/trader</a>.

A DLL for this PECL extension is available under
<a href="http://windows.php.net/downloads/pecl/releases/trader/" class="link external">» http://windows.php.net/downloads/pecl/releases/trader/</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default    | Changeable    | Changelog          |
|-----------------------------------------------------------------------|------------|---------------|--------------------|
| <a href="/trader/setup.html#" class="link">trader.real_precision</a>  | 3          | PHP\_INI\_ALL | Since trader 0.2.1 |
| <a href="/trader/setup.html#" class="link">trader.real_round_mode</a> | HALF\_DOWN | PHP\_INI\_ALL | Since trader 0.3.0 |

Here's a short explanation of the configuration directives.

`trader.real_precision` <span class="type">int</span>  
All the values in the returned arrays will be rounded to this precision.
However the calculations inside TA-Lib happen with unrounded values.

`trader.real_round_mode` <span class="type">string</span>  
Controls the trader real rounding policy. Valid values are *HALF\_UP*,
*HALF\_DOWN*, *HALF\_EVEN* and *HALF\_ODD*. The behaviour is identical
to the <a href="/ref/math.html#round" class="link">round()</a> function
used with the mode argument.
