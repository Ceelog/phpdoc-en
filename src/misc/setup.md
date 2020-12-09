Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/misc/setup.html#Requirements)
-   [Installation](/misc/setup.html#Installation)
-   [Runtime Configuration](/misc/setup.html#Runtime%20Configuration)
-   [Resource Types](/misc/setup.html#Resource%20Types)

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

| Name                                                           | Default    | Changeable       | Changelog             |
|----------------------------------------------------------------|------------|------------------|-----------------------|
| <a href="/misc/setup.html#" class="link">ignore_user_abort</a> | "0"        | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">highlight.string</a>  | "\#DD0000" | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">highlight.comment</a> | "\#FF8000" | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">highlight.keyword</a> | "\#007700" | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">highlight.bg</a>      | "\#FFFFFF" | PHP\_INI\_ALL    | Removed in PHP 5.4.0. |
| <a href="/misc/setup.html#" class="link">highlight.default</a> | "\#0000BB" | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">highlight.html</a>    | "\#000000" | PHP\_INI\_ALL    |                       |
| <a href="/misc/setup.html#" class="link">browscap</a>          | NULL       | PHP\_INI\_SYSTEM |                       |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`ignore_user_abort` <span class="type">bool</span>  
**`false`** by default. If changed to **`true`** scripts will not be
terminated after a client has aborted their connection.

See also <span class="function">ignore\_user\_abort</span>.

`highlight.bg` <span class="type">string</span>  
`highlight.comment` <span class="type">string</span>  
`highlight.default` <span class="type">string</span>  
`highlight.html` <span class="type">string</span>  
`highlight.keyword` <span class="type">string</span>  
`highlight.string` <span class="type">string</span>  
Colors for Syntax Highlighting mode. Anything that's acceptable in
\<font color="??????"\> would work.

`browscap` <span class="type">string</span>  
Name (e.g.: `browscap.ini`) and location of browser capabilities file.
See also <span class="function">get\_browser</span>.

Resource Types
--------------

This extension has no resource types defined.
