Predefined Variables
--------------------

PHP provides a large number of predefined variables to any script which
it runs. Many of these variables, however, cannot be fully documented as
they are dependent upon which server is running, the version and setup
of the server, and other factors. Some of these variables will not be
available when PHP is run on the
<a href="/features/commandline.html" class="link">command line</a>. For
a listing of these variables, please see the section on
<a href="/reserved/variables.html" class="link">Reserved Predefined Variables</a>.

PHP also provides an additional set of predefined arrays containing
variables from the web server (if applicable), the environment, and user
input. These arrays are rather special in that they are automatically
global - i.e., automatically available in every scope. For this reason,
they are often known as "superglobals". (There is no mechanism in PHP
for user-defined superglobals.) The superglobals can be found
<a href="/language/variables/superglobals.html" class="link">here</a>;
however, for a listing of their contents and further discussion on PHP
predefined variables and their natures, please see the section
<a href="/reserved/variables.html" class="link">Reserved Predefined Variables</a>.

> **Note**:
>
> Prior to PHP 5.4, the old way of retrieving information related to the
> HTTP request with the *HTTP\_\*\_VARS* variables instead of
> superglobals was still possible. This feature could be disabled as of
> PHP 5.0.0 with the
> <a href="/ini/core.html#ini.register-long-arrays" class="link">register_long_arrays</a>
> directive.

> **Note**: **Variable variables**  
>
> Superglobals cannot be used as
> <a href="/language/variables/variable.html" class="link">variable variables</a>
> inside functions or class methods.

If certain variables in
<a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
are not set, their appropriate PHP predefined arrays are also left
empty.
