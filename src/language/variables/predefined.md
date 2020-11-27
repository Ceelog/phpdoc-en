Predefined Variables
--------------------

PHP provides a large number of predefined variables to any script which
it runs. Many of these variables, however, cannot be fully documented as
they are dependent upon which server is running, the version and setup
of the server, and other factors. Some of these variables will not be
available when PHP is run on the
<a href="/features/commandline.html" class="link">command line</a>.
Refer to the
<a href="/reserved/variables.html" class="link">list of predefined variables</a>
for details.

PHP also provides an additional set of predefined arrays containing
variables from the web server (if applicable), the environment, and user
input. These arrays are rather special in that they are automatically
global - i.e., automatically available in every scope. For this reason,
they are often known as "superglobals". (There is no mechanism in PHP
for user-defined superglobals.) Refer to the
<a href="/language/variables/superglobals.html" class="link">list of superglobals</a>
for details.

> **Note**: **Variable variables**  
>
> Superglobals cannot be used as
> <a href="/language/variables/variable.html" class="link">variable variables</a>
> inside functions or class methods.

If certain variables in
<a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
are not set, their appropriate PHP predefined arrays are also left
empty.
