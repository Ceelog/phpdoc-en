Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/stomp/setup.html#Requirements)
-   [Installation](/stomp/setup.html#Installation)
-   [Runtime Configuration](/stomp/setup.html#Runtime%20Configuration)
-   [Resource Types](/stomp/setup.html#Resource%20Types)

Requirements
------------

PECL/stomp requires PHP 5.2.2 or newer.

The
<a href="http://www.openssl.org/" class="link external">» OpenSSL</a>
package \>= 0.9.6 and the
<a href="/book/openssl.html" class="link">openssl</a> extension may also
be required to use stomp over SSL.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/stomp" class="link external">» https://pecl.php.net/package/stomp</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                | Default               | Changeable    | Changelog |
|-------------------------------------------------------------------------------------|-----------------------|---------------|-----------|
| <a href="/stomp/setup.html#" class="link">stomp.default_broker</a>                  | tcp://localhost:61613 | PHP\_INI\_ALL |           |
| <a href="/stomp/setup.html#" class="link">stomp.default_connection_timeout_sec</a>  | 2                     | PHP\_INI\_ALL |           |
| <a href="/stomp/setup.html#" class="link">stomp.default_connection_timeout_usec</a> | 0                     | PHP\_INI\_ALL |           |
| <a href="/stomp/setup.html#" class="link">stomp.default_read_timeout_sec</a>        | 2                     | PHP\_INI\_ALL |           |
| <a href="/stomp/setup.html#" class="link">stomp.default_read_timeout_usec</a>       | 0                     | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`stomp.default_broker` <span class="type">string</span>  
The default broker URI to use when connecting to the message broker if
no other URI is specified.

`stomp.default_connection_timeout_sec` <span class="type">int</span>  
The seconds part of the default connection timeout.

`stomp.default_connection_timeout_usec` <span class="type">int</span>  
The microseconds part of the default connection timeout.

`stomp.default_read_timeout_sec` <span class="type">int</span>  
The seconds part of the default reading timeout.

`stomp.default_read_timeout_usec` <span class="type">int</span>  
The microseconds part of the default reading timeout.

Resource Types
--------------

There is only one resource type used in the stomp extension - it's the
link identifier for a stomp connection.
