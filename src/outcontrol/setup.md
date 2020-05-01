Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/outcontrol/setup.html#Requirements)
-   [Installation](/outcontrol/setup.html#Installation)
-   [Runtime
    Configuration](/outcontrol/setup.html#Runtime%20Configuration)
-   [Resource Types](/outcontrol/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default                                         | Changeable       | Changelog                                                                                                                                                       |
|-----------------------------------------------------------------------|-------------------------------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <a href="/outcontrol/setup.html#" class="link">output_buffering</a>   | "0"                                             | PHP\_INI\_PERDIR |                                                                                                                                                                 |
| <a href="/outcontrol/setup.html#" class="link">output_handler</a>     | NULL                                            | PHP\_INI\_PERDIR |                                                                                                                                                                 |
| <a href="/outcontrol/setup.html#" class="link">implicit_flush</a>     | "0"                                             | PHP\_INI\_ALL    |                                                                                                                                                                 |
| <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>  | "a=href,area=href,frame=src,form=,fieldset="    | PHP\_INI\_ALL    | Before PHP 7.1.0, this was used to set session's trans sid rewrite. From PHP 7.1.0, it is only used by <span class="function">output\_add\_rewrite\_var</span>. |
| <a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a> | *$\_SERVER\['HTTP\_HOST'\]* is used as default. | PHP\_INI\_ALL    | Available as of PHP 7.1.0                                                                                                                                       |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`output_buffering` <span class="type">boolean</span>/<span class="type">integer</span>  
You can enable output buffering for all files by setting this directive
to 'On'. If you wish to limit the size of the buffer to a certain size -
you can use a maximum number of bytes instead of 'On', as a value for
this directive (e.g., output\_buffering=4096). This directive is always
Off in PHP-CLI.

`output_handler` <span class="type">string</span>  
You can redirect all of the output of your scripts to a function. For
example, if you set output\_handler to <span
class="function">mb\_output\_handler</span>, character encoding will be
transparently converted to the specified encoding. Setting any output
handler automatically turns on output buffering.

> **Note**:
>
> You cannot use both <span class="function">mb\_output\_handler</span>
> with <span class="function">ob\_iconv\_handler</span> and you cannot
> use both <span class="function">ob\_gzhandler</span> and
> <a href="/zlib/setup.html#" class="link">zlib.output_compression</a>.

> **Note**:
>
> Only built-in functions can be used with this directive. For user
> defined functions, use <span class="function">ob\_start</span>.

`implicit_flush` <span class="type">boolean</span>  
**`FALSE`** by default. Changing this to **`TRUE`** tells PHP to tell
the output layer to flush itself automatically after every output block.
This is equivalent to calling the PHP function <span
class="function">flush</span> after each and every call to <span
class="function">print</span> or <span class="function">echo</span> and
each and every *HTML* block.

When using PHP within an web environment, turning this option on has
serious performance implications and is generally recommended for
debugging purposes only. This value defaults to **`TRUE`** when
operating under the *CLI SAPI*.

See also <span class="function">ob\_implicit\_flush</span>.

`url_rewriter.tags` <span class="type">string</span>  
<span class="simpara"> *url\_rewriter.tags* specifies which HTML tags
are rewritten by <span class="function">output\_add\_rewrite\_var</span>
values. Defaults to *a=href,area=href,frame=src,input=src,form=* </span>
<span class="simpara"> *form* is special tag. *\<input
hidden="session\_id" name="session\_name"\>* is added as form variable.
</span>

> **Note**: <span class="simpara"> Before PHP 7.1.0,
> <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>
> was used to specify
> <a href="/session/setup.html#" class="link">session.trans_sid_tags</a>.
> As of PHP 7.1.0, *fieldset* is no longer considered as special tag.
> </span>

`url_rewriter.hosts` <span class="type">string</span>  
<span class="simpara"> *url\_rewriter.hosts* specifies which hosts are
rewritten to include <span
class="function">output\_add\_rewrite\_var</span> values. Defaults to
*$\_SERVER\['HTTP\_HOST'\]*. Multiple hosts can be specified by ",", no
space is allowed between hosts. e.g. *php.net,wiki.php.net,bugs.php.net*
</span>

Resource Types
--------------

This extension has no resource types defined.
