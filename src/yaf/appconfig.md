Application Configuration
=========================

You should give an array of config or an ini config file(see <span
class="classname">Yaf\_Config\_Ini</span>) path to <span
class="methodname">Yaf\_Application::\_\_construct</span>.

Yaf will merge the application configurations and user configurations
automatically. The application configurations have prefix "yaf." or
"application.". If both "yaf." and "application." exist, "application."
will be accepted preferentially.

**Example \#1 An PHP array example**

``` php
<?php
    $configs = array(
            "application" => array(
                "directory" => dirname(__FILE__),
                "dispatcher" => array(
                      "catchException" => 0,
                    ),
                "view" => array(
                       "ext" => "phtml",
                    ),
                ),
           );
    $app = new Yaf_Application($configs);
?>
```

**Example \#2 An ini file example**

``` ini
[yaf]
yaf.directory = APPLICATION_PATH "/appliation"
yaf.dispatcher.catchException = 0

[product : yaf]
; user configuration list here
```

| Name                                     | Default                                                | Changelog |
|------------------------------------------|--------------------------------------------------------|-----------|
| application.directory                    |                                                        |           |
| application.ext                          | "php"                                                  |           |
| application.view.ext                     | "phtml"                                                |           |
| application.modules                      | "index"                                                |           |
| application.library                      | application.directory . "/library"                     |           |
| application.library.directory            | application.directory . "/library"                     |           |
| application.library.namespace            | ""                                                     |           |
| application.bootstrap                    | application.directory . "/Bootstrap" . application.ext |           |
| application.baseUri                      | ""                                                     |           |
| application.dispatcher.defaultRoute      |                                                        |           |
| application.dispatcher.throwException    | 1                                                      |           |
| application.dispatcher.catchException    | 0                                                      |           |
| application.dispatcher.defaultModule     | "index"                                                |           |
| application.dispatcher.defaultController | "index"                                                |           |
| application.dispatcher.defaultAction     | "index"                                                |           |
| application.system                       |                                                        |           |

Here's a short explanation of the configuration directives.

`application.directory` <span class="type">string</span>  
The directory of the application, that is the folder which contains the
"controllers", "views", "models", "plugins" folders.

> **Note**:
>
> This config entry is the only one which doesn't has a default value.
> You should always define it manually.

`application.ext` <span class="type">string</span>  
The file ext of the PHP script, used in class autoloading( <span
class="classname">Yaf\_Loader</span>).

`application.view.ext` <span class="type">string</span>  
The file ext of the view template scripts.

`application.modules` <span class="type">string</span>  
A comma-separated list of the registered modules, used in the route
process, especially while there are more than three segments in the
PATH\_INFO,

Yaf need a way to find out whether the first segment is a module name or
not.

`application.library` <span class="type">string</span>  
The local library directory, see <span
class="classname">Yaf\_Loader</span> and
<a href="/yaf/setup.html#" class="link">yaf.library</a>.

> **Note**:
>
> After Yaf 2.1.6, this config entry can be an array. The library path
> will try to use the items setted in
> <a href="/yaf/appconfig.html#" class="link">application.library.directory</a>

`application.library.directory` <span class="type">string</span>  
Alias of
<a href="/yaf/appconfig.html#" class="link">application.library</a>.
Introduced in Yaf 2.1.6

`application.library.namespace` <span class="type">string</span>  
A comma-separated prefix of local library namespace.

Introduced in Yaf 2.1.6

`application.bootstrap` <span class="type">string</span>  
A absolute path of the Bootstrap class script.

`application.baseUri` <span class="type">string</span>  
Used to remove a fixed prefix of request uri in route process. Take a
example, comes a request with request uri "/prefix/controller/action".
if you set application.baseUri to "/prefix", then only
"/controller/action" will take as the PATH\_INFO in route process.

In generally, there is no need to set this value.

`application.dispatcher.throwException` <span class="type">bool</span>  
If it set to On, Yaf will throw an exception while some error occurring.
See also <span
class="methodname">Yaf\_Dispatcher::throwException</span>.

`application.dispatcher.catchException` <span class="type">bool</span>  
If it set to On, Yaf will forward to Error controller/Action while there
is an unhandled exception. See also <span
class="methodname">Yaf\_Dispatcher::catchException</span>.

`application.dispatcher.defaultRoute` <span class="type">string</span>  
The default Route, if it is not specificed, Static route will be used as
default. See: <span class="methodname">Yaf\_Router::addRoute</span>.

`application.dispatcher.defaultModule` <span class="type">string</span>  
The default module name, see also <span
class="methodname">Yaf\_Dispatcher::setDefaultModule</span>.

`application.dispatcher.defaultController` <span class="type">string</span>  
The default controller name, see also <span
class="methodname">Yaf\_Dispatcher::setDefaultController</span>.

`application.dispatcher.defaultAction` <span class="type">string</span>  
The default action name, see also <span
class="methodname">Yaf\_Dispatcher::setDefaultAction</span>.

`application.system` <span class="type">string</span>  
Set yaf runtime configure in application.ini, like:
<a href="/yaf/setup.html#" class="link">application.system.lowcase_path</a>

> **Note**:
>
> only those PHP\_INI\_ALL configures can be set in this way
