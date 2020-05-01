Case 4: PHP parser outside of web tree
--------------------------------------

A very secure option is to put the PHP parser binary somewhere outside
of the web tree of files. In `/usr/local/bin`, for example. The only
real downside to this option is that you will now have to put a line
similar to:

    #!/usr/local/bin/php

as the first line of any file containing PHP tags. You will also need to
make the file executable. That is, treat it exactly as you would treat
any other CGI script written in Perl or sh or any other common scripting
language which uses the *\#!* shell-escape mechanism for launching
itself.

To get PHP to handle `PATH_INFO` and `PATH_TRANSLATED` information
correctly with this setup, the PHP parser should be compiled with the
<a href="/configure/about.html#configure.enable-discard-path" class="link">--enable-discard-path</a>
configure option.
