Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/expect/setup.html#Requirements)
-   [Installation](/expect/setup.html#Installation)
-   [Runtime Configuration](/expect/setup.html#Runtime%20Configuration)
-   [Resource Types](/expect/setup.html#Resource%20Types)

Requirements
------------

This module uses the functions of the
<a href="http://expect.nist.gov/" class="link external">» expect</a>
library. You need libexpect version \>= 5.43.0.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/expect" class="link external">» https://pecl.php.net/package/expect</a>.

In order to use these functions you must compile PHP with expect support
by using the **--with-expect\[=DIR\]** configure option.

Windows users will enable `php_expect.dll` inside of `php.ini` in order
to use these functions. A DLL for this PECL extension is currently
unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

In order to configure expect extension, there are configuration options
in the
<a href="/configuration/file.html" class="link">configuration file</a>
`php.ini`.

| Name                                                            | Default | Changeable    | Changelog |
|-----------------------------------------------------------------|---------|---------------|-----------|
| <a href="/expect/setup.html#" class="link">expect.timeout</a>   | "10"    | PHP\_INI\_ALL |           |
| <a href="/expect/setup.html#" class="link">expect.loguser</a>   | "1"     | PHP\_INI\_ALL |           |
| <a href="/expect/setup.html#" class="link">expect.logfile</a>   | ""      | PHP\_INI\_ALL |           |
| <a href="/expect/setup.html#" class="link">expect.match_max</a> | ""      | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`expect.timeout` <span class="type">int</span>  
The timeout period for waiting for the data, when using the <span
class="function">expect\_expectl</span> function.

A value of "-1" disables a timeout from occurring.

> **Note**:
>
> A value of "0" causes the <span
> class="function">expect\_expectl</span> function to return
> immediately.

`expect.loguser` <span class="type">bool</span>  
Whether expect should send any output from the spawned process to
stdout. Since interactive programs typically echo their input, this
usually suffices to show both sides of the conversation.

`expect.logfile` <span class="type">string</span>  
Name of the file, where the output from the spawned process will be
written. If this file doesn't exist, it will be created.

> **Note**:
>
> If this configuration is not empty, the output is written regardless
> of the value of
> <a href="/expect/setup.html#" class="link">expect.loguser</a>.

`expect.match_max` <span class="type">int</span>  
Changes default size (2000 bytes) of the buffer used to match asterisks
in patterns.

Resource Types
--------------

<span class="function">expect\_popen</span> returns an open PTY stream
used by <span class="function">expect\_expectl</span>.
