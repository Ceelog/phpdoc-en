Installing/Configuring
======================

**Table of Contents**

-   [Runtime Configuration](/phpdbg/setup.html#Runtime%20Configuration)

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                       | Default | Changeable    | Changelog                 |
|------------------------------------------------------------|---------|---------------|---------------------------|
| <a href="/phpdbg/setup.html#" class="link">phpdbg.eol</a>  | 2       | PHP\_INI\_ALL | Available as of PHP 7.0.0 |
| <a href="/phpdbg/setup.html#" class="link">phpdbg.path</a> |         | 6             | Available as of PHP 5.6.3 |

Here's a short explanation of the configuration directives.

`phpdbg.eol` <span class="type">mixed</span>  
The kind of line ending to use for output. For setting the value, one of
the string aliases must be used.

| <span class="type">int</span> Value | <span class="type">string</span> Alias |
|-------------------------------------|----------------------------------------|
| *0*                                 | *CRLF*, *crlf*, *DOS*, *dos*           |
| *1*                                 | *LF*, *lf*, *UNIX*, *unix*             |
| *2*                                 | *CR*, *cr*, *MAC*, *mac*               |

`phpdbg.path` <span class="type">string</span>  
