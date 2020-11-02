Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yaml/setup.html#Requirements)
-   [Installation](/yaml/setup.html#Installation)
-   [Runtime Configuration](/yaml/setup.html#Runtime%20Configuration)
-   [Resource Types](/yaml/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="http://pyyaml.org/wiki/LibYAML" class="link external">» LibYAML C library</a>
version 0.1.0 or higher to be installed.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yaml" class="link external">» https://pecl.php.net/package/yaml</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                               | Default | Changeable    | Changelog                                      |
|--------------------------------------------------------------------|---------|---------------|------------------------------------------------|
| <a href="/yaml/setup.html#" class="link">yaml.decode_binary</a>    | 0       | PHP\_INI\_ALL |                                                |
| <a href="/yaml/setup.html#" class="link">yaml.decode_php</a>       | 0       | PHP\_INI\_ALL | Added in 1.2.0, before 2.0.0 the default was 1 |
| <a href="/yaml/setup.html#" class="link">yaml.decode_timestamp</a> | 0       | PHP\_INI\_ALL |                                                |
| <a href="/yaml/setup.html#" class="link">yaml.output_canonical</a> | 0       | PHP\_INI\_ALL |                                                |
| <a href="/yaml/setup.html#" class="link">yaml.output_indent</a>    | 2       | PHP\_INI\_ALL |                                                |
| <a href="/yaml/setup.html#" class="link">yaml.output_width</a>     | 80      | PHP\_INI\_ALL |                                                |

Here's a short explanation of the configuration directives.

`yaml.decode_binary` <span class="type">bool</span>  
Off by default, but can be set to on to cause base64 binary encoded
entities which have the explicit tag "tag:yaml.org,2002:binary" to be
decoded.

`yaml.decode_php` <span class="type">bool</span>  
Off by default, but can be set to on to cause serialized php objects
which have the explicit tag "!php/object" to be unserialized.

`yaml.decode_timestamp` <span class="type">int</span>  
Controls the decoding of both implicit and explicit
"tag:yaml.org,2002:timestamp" scalars in the YAML document stream. The
default setting of *0* will not apply any decoding. A setting of *1*
will use <span class="function">strtotime</span> to parse the timestamp
value as a Unix timestamp. A setting of *2* will use <span
class="function">date\_create</span> to parse the timestamp value as
<span class="type">DateTime</span> object.

`yaml.output_canonical` <span class="type">bool</span>  
Off by default, but can be set to on to cause canonical form output.

`yaml.output_indent` <span class="type">int</span>  
Number of spaces to indent sections. Value should be between *1* and
*10*.

`yaml.output_width` <span class="type">int</span>  
Set the preferred line width. *-1* means unlimited.

Resource Types
--------------

This extension has no resource types defined.
