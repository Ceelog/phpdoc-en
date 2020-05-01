Case 2: using *cgi.force\_redirect*
-----------------------------------

The configuration directive
<a href="/ini/core.html#ini.cgi.force-redirect" class="link">cgi.force_redirect</a>
prevents anyone from calling PHP directly with a URL like
`http://my.host/cgi-bin/php/secretdir/script.php`. Instead, PHP will
only parse in this mode if it has gone through a web server redirect
rule.

Usually the redirection in the Apache configuration is done with the
following directives:

``` apache-conf
Action php-script /cgi-bin/php
AddHandler php-script .php
```

This option has only been tested with the Apache web server, and relies
on Apache to set the non-standard CGI environment variable
`REDIRECT_STATUS` on redirected requests. If your web server does not
support any way of telling if the request is direct or redirected, you
cannot use this option and you must use one of the other ways of running
the CGI version documented here.
