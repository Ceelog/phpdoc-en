Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/readline/setup.html#Requirements)
-   [Installation](/readline/setup.html#Installation)
-   [Runtime
    Configuration](/readline/setup.html#Runtime%20Configuration)
-   [Resource Types](/readline/setup.html#Resource%20Types)

Requirements
------------

To use the readline functions, you need to install libreadline. You can
find libreadline on the home page of the GNU Readline project, at
<a href="http://cnswww.cns.cwru.edu/~chet/readline/rltop.html" class="link external">» http://cnswww.cns.cwru.edu/~chet/readline/rltop.html</a>.
It's maintained by Chet Ramey, who's also the author of Bash.

You can also use these functions with the libedit library, a non-GPL
replacement for the readline library. The libedit library is BSD
licensed and available for download from
<a href="http://www.thrysoee.dk/editline/" class="link external">» http://www.thrysoee.dk/editline/</a>.

Installation
------------

To use these functions you must compile the CGI or CLI version of PHP
with readline support. You need to configure PHP
**--with-readline\[=DIR\]**. If you want to use the libedit readline
replacement, configure PHP **--with-libedit\[=DIR\]**.

On Windows this extension is available by default as of PHP 7.1.0.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                        | Default         | Changeable    | Changelog                  |
|-------------------------------------------------------------|-----------------|---------------|----------------------------|
| <a href="/readline/setup.html#" class="link">cli.pager</a>  | ""              | PHP\_INI\_ALL | Available since PHP 5.4.0. |
| <a href="/readline/setup.html#" class="link">cli.prompt</a> | "\\\\b \\\\\> " | PHP\_INI\_ALL | Available since PHP 5.4.0. |

Here's a short explanation of the configuration directives.

`cli.pager` <span class="type">string</span>  
External tool to display output from
<a href="/features/commandline.html" class="link">command line</a>.

`cli.prompt` <span class="type">string</span>  
<a href="/features/commandline.html" class="link">Command line</a>
prompt.

Resource Types
--------------

This extension has no resource types defined.
