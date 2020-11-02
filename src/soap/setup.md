Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/soap/setup.html#Requirements)
-   [Installation](/soap/setup.html#Installation)
-   [Runtime Configuration](/soap/setup.html#Runtime%20Configuration)
-   [Resource Types](/soap/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

Installation
------------

To enable SOAP support, configure PHP with **--enable-soap**.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                 | Default | Changeable    | Changelog |
|----------------------------------------------------------------------|---------|---------------|-----------|
| <a href="/soap/setup.html#" class="link">soap.wsdl_cache_enabled</a> | 1       | PHP\_INI\_ALL |           |
| <a href="/soap/setup.html#" class="link">soap.wsdl_cache_dir</a>     | /tmp    | PHP\_INI\_ALL |           |
| <a href="/soap/setup.html#" class="link">soap.wsdl_cache_ttl</a>     | 86400   | PHP\_INI\_ALL |           |
| <a href="/soap/setup.html#" class="link">soap.wsdl_cache</a>         | 1       | PHP\_INI\_ALL |           |
| <a href="/soap/setup.html#" class="link">soap.wsdl_cache_limit</a>   | 5       | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`soap.wsdl_cache_enabled` <span class="type">int</span>  
Enables or disables the WSDL caching feature.

`soap.wsdl_cache_dir` <span class="type">string</span>  
Sets the directory name where the SOAP extension will put cache files.

`soap.wsdl_cache_ttl` <span class="type">int</span>  
Sets the number of seconds (time to live) that cached files will be used
instead of the originals.

`soap.wsdl_cache` <span class="type">int</span>  
If `soap.wsdl_cache_enabled` is on, this setting determines the type of
caching. It can be any of: **`WSDL_CACHE_NONE`** (*0*),
**`WSDL_CACHE_DISK`** (*1*), **`WSDL_CACHE_MEMORY`** (*2*) or
**`WSDL_CACHE_BOTH`** (*3*). This can also be set via the `options`
array in the <span class="classname">SoapClient</span> or <span
class="classname">SoapServer</span> constructor.

`soap.wsdl_cache_limit` <span class="type">int</span>  
Maximum number of in-memory cached WSDL files. Adding further files into
a full memory cache will delete the oldest files from it.

Resource Types
--------------

This extension has no resource types defined.
