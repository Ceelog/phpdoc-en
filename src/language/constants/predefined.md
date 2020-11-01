Magic constants
---------------

PHP provides a large number of
<a href="/reserved/constants.html" class="link">predefined constants</a>
to any script which it runs. Many of these constants, however, are
created by various extensions, and will only be present when those
extensions are available, either via dynamic loading or because they
have been compiled in.

There are nine magical constants that change depending on where they are
used. For example, the value of **`__LINE__`** depends on the line that
it's used on in your script. All these "magical" constants are resolved
at compile time, unlike regular constants, which are resolved at
runtime. These special constants are case-insensitive and are as
follows:

| Name                   | Description                                                                                                                                                                                                                              |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`__LINE__`**         | The current line number of the file.                                                                                                                                                                                                     |
| **`__FILE__`**         | The full path and filename of the file with symlinks resolved. If used inside an include, the name of the included file is returned.                                                                                                     |
| **`__DIR__`**          | The directory of the file. If used inside an include, the directory of the included file is returned. This is equivalent to *dirname(\_\_FILE\_\_)*. This directory name does not have a trailing slash unless it is the root directory. |
| **`__FUNCTION__`**     | The function name, or *{closure}* for anonymous functions.                                                                                                                                                                               |
| **`__CLASS__`**        | The class name. The class name includes the namespace it was declared in (e.g. *Foo\\Bar*). When used in a trait method, \_\_CLASS\_\_ is the name of the class the trait is used in.                                                    |
| **`__TRAIT__`**        | The trait name. The trait name includes the namespace it was declared in (e.g. *Foo\\Bar*).                                                                                                                                              |
| **`__METHOD__`**       | The class method name.                                                                                                                                                                                                                   |
| **`__NAMESPACE__`**    | The name of the current namespace.                                                                                                                                                                                                       |
| **`ClassName::class`** | The fully qualified class name. See also <a href="/language/oop5/basic.html#language.oop5.basic.class.class" class="link">::class</a>.                                                                                                   |

### See Also

-   <span class="function">get\_class</span>
-   <span class="function">get\_object\_vars</span>
-   <span class="function">file\_exists</span>
-   <span class="function">function\_exists</span>
