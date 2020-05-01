Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mail/setup.html#Requirements)
-   [Installation](/mail/setup.html#Installation)
-   [Runtime Configuration](/mail/setup.html#Runtime%20Configuration)
-   [Resource Types](/mail/setup.html#Resource%20Types)

Requirements
------------

For the Mail functions to be available, PHP must have access to the
*sendmail* binary on your system during compile time. If you use another
mail program, such as <span class="productname">qmail</span> or <span
class="productname">postfix</span>, be sure to use the appropriate
sendmail wrappers that come with them. PHP will first look for sendmail
in your `PATH`, and then in the following:
*/usr/bin:/usr/sbin:/usr/etc:/etc:/usr/ucblib:/usr/lib*. It's highly
recommended to have sendmail available from your `PATH`. Also, the user
that compiled PHP must have permission to access the sendmail binary.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                     | Default                    | Changeable       | Changelog                                                       |
|--------------------------------------------------------------------------|----------------------------|------------------|-----------------------------------------------------------------|
| <a href="/mail/setup.html#" class="link">mail.add_x_header</a>           | "0"                        | PHP\_INI\_PERDIR | Available since PHP 5.3.0.                                      |
| <a href="/mail/setup.html#" class="link">mail.log</a>                    | NULL                       | PHP\_INI\_PERDIR | Available since PHP 5.3.0. (PHP\_INI\_SYSTEM\|PHP\_INI\_PERDIR) |
| <a href="/mail/setup.html#" class="link">mail.force_extra_parameters</a> | NULL                       | PHP\_INI\_PERDIR | Available since PHP 5.0.0. (PHP\_INI\_SYSTEM\|PHP\_INI\_PERDIR) |
| <a href="/mail/setup.html#" class="link">SMTP</a>                        | "localhost"                | PHP\_INI\_ALL    |                                                                 |
| <a href="/mail/setup.html#" class="link">smtp_port</a>                   | "25"                       | PHP\_INI\_ALL    |                                                                 |
| <a href="/mail/setup.html#" class="link">sendmail_from</a>               | NULL                       | PHP\_INI\_ALL    |                                                                 |
| <a href="/mail/setup.html#" class="link">sendmail_path</a>               | "/usr/sbin/sendmail -t -i" | PHP\_INI\_SYSTEM |                                                                 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`mail.add_x_header` <span class="type">bool</span>  
Add *X-PHP-Originating-Script* that will include UID of the script
followed by the filename.

`mail.log` <span class="type">string</span>  
The path to a log file that will log all <span
class="function">mail</span> calls. Log entries include the full path of
the script, line number, *To* address and headers.

`mail.force_extra_parameters` <span class="type">string</span>  
Force the addition of the specified parameters to be passed as extra
parameters to the sendmail binary. These parameters will always replace
the value of the 5th parameter to <span class="function">mail</span>,
even in safe mode.

`SMTP` <span class="type">string</span>  
Used under Windows only: host name or IP address of the SMTP server PHP
should use for mail sent with the <span class="function">mail</span>
function.

`smtp_port` <span class="type">int</span>  
Used under Windows only: Number of the port to connect to the server
specified with the *SMTP* setting when sending mail with <span
class="function">mail</span>; defaults to 25.

`sendmail_from` <span class="type">string</span>  
Which *"From:"* mail address should be used in mail sent from PHP under
Windows. This directive also sets the *"Return-Path:"* header.

`sendmail_path` <span class="type">string</span>  
Where the **sendmail** program can be found, usually
`/usr/sbin/sendmail` or `/usr/lib/sendmail`. **configure** does an
honest attempt of locating this one for you and set a default, but if it
fails, you can set it here.

Systems not using **sendmail** should set this directive to the sendmail
wrapper/replacement their mail system offers, if any. For example,
<a href="http://cr.yp.to/qmail.html" class="link external">» Qmail</a>
users can normally set it to `/var/qmail/bin/sendmail` or
`      /var/qmail/bin/qmail-inject`.

**qmail-inject** does not require any option to process mail correctly.

This directive works also under Windows. If set, `smtp`, `smtp_port` and
`sendmail_from` are ignored and the specified command is executed.

Resource Types
--------------

This extension has no resource types defined.
