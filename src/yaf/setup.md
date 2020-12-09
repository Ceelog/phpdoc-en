Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yaf/setup.html#Requirements)
-   [Installation](/yaf/setup.html#Installation)
-   [Runtime Configuration](/yaf/setup.html#Runtime%20Configuration)
-   [Resource Types](/yaf/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yaf" class="link external">» https://pecl.php.net/package/yaf</a>.

Windows binaries (DLL files) for this PECL extension are available from
the PECL website.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                             | Default | Changeable       | Changelog |
|------------------------------------------------------------------|---------|------------------|-----------|
| <a href="/yaf/setup.html#" class="link">yaf.library</a>          |         | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.action_prefer</a>    | 0       | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.lowcase_path</a>     | 0       | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.use_spl_autoload</a> | 0       | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.forward_limit</a>    | 5       | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.name_suffix</a>      | 1       | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.name_separator</a>   |         | PHP\_INI\_ALL    |           |
| <a href="/yaf/setup.html#" class="link">yaf.cache_config</a>     | 0       | PHP\_INI\_SYSTEM |           |
| <a href="/yaf/setup.html#" class="link">yaf.environ</a>          | product | PHP\_INI\_SYSTEM |           |
| <a href="/yaf/setup.html#" class="link">yaf.use_namespace</a>    | 0       | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`yaf.library` <span class="type">string</span>  
The global library path, Yaf\_loader will search global library in this
directory.

`yaf.action_prefer` <span class="type">int</span>  
If there is only one part in PATH\_INFO, should it consider as a
controller or action.

If this configure On, it will be considered as a Action name.

`yaf.lowcase_path` <span class="type">int</span>  
Whether lowercase all the path during the class autoloading.

`yaf.use_spl_autoload` <span class="type">int</span>  
When this value is On, if <span class="classname">Yaf\_Loader</span> can
not find a class, it will return **`false`**, then give chance to other
auto load function to be called.

When this value is Off, if <span class="classname">Yaf\_Loader</span>
can not find a class, it will return **`true`**, and make the class
autoloading failed immediately.

> **Note**:
>
> Yaf will register its loader during a instantiation of <span
> class="classname">Yaf\_Application</span>, so any other auto loaders
> which is register before the instantiation will be called before <span
> class="methodname">Yaf\_Loader::autoload</span>.

When this value is Off(default), <span
class="methodname">Yaf\_Loader::autoload</span> will always return
**`true`**.

`yaf.forward_limit` <span class="type">int</span>  
The max forward count, default is 5. that means you can have a max value
of 5 in the forward stack.

This is a protection for prevent recursive <span
class="methodname">Yaf\_Controller\_Abstract::forward</span>.

`yaf.name_suffix` <span class="type">int</span>  
When this On, Yaf\_Loader will identify a class by it's suffix to decide
whether it is a MVC Class.

When this Off, Yaf\_Loader will look at the prefix of the class name.

`yaf.name_separator` <span class="type">string</span>  
When this is not empty, Yaf\_Loader will identify the class suffix and
string value of this.

For example, when this value is "\_", Yaf\_Loader will take
Index\_Controller as a Controller Class, IndexController as a normal
class.

`yaf.cache_config` <span class="type">int</span>  
If this is On, and in the meantime you are using ini config file as the
parameter of <span class="methodname">Yaf\_Application</span>, the
compiling result of the ini config file will be cached in the PHP
process.

> **Note**:
>
> Yaf examine the mtime of the ini file, if it was changed since last
> compiling, Yaf will reload it.

**Warning**
Yaf use the ini file path as the cache entry key, so do use the absolute
path in ini file path, otherwise there might be some conflicts if two
application use the same relative path of ini config.

`yaf.environ` <span class="type">string</span>  
This value is "product" by default, used for Yaf to fetch the config
section of a ini config file.

That is, if this value is "product", Yaf will use the section named
"product" in the ini config file(the first parameter of the <span
class="classname">Yaf\_Application</span>) as the final config of the
<span class="classname">Yaf\_Application</span>.

`yaf.use_namespace` <span class="type">int</span>  
Only works as of PHP 5.3, if this value is On, All classes of Yaf will
named in namespace style.

For example:

    Yaf_Route_Rewrite => \Yaf\Route\Rewrite
    Yaf_Request_Http  => \Yaf\Request\Http
            

There is a exception, that is some classes like <span
class="classname">Yaf\_Controller\_Abstract</span>. The last component
is a keyword of PHP, could not be used as a class name, so for such
classes:

    Yaf_Controller_Abstract => \Yaf\Controller_Abstract
    Yaf_Route_Static => \Yaf\Route_Static
            

Resource Types
--------------

This extension has no resource types defined.
