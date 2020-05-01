CGI and command line setups
---------------------------

By default, PHP is built as both a CLI and CGI program, which can be
used for CGI processing. If you are running a web server that PHP has
module support for, you should generally go for that solution for
performance reasons. However, the CGI version enables users to run
different PHP-enabled pages under different user-ids.

**Warning**

A server deployed in CGI mode is open to several possible
vulnerabilities. Please read our
<a href="/security/cgi-bin.html" class="link">CGI security section</a>
to learn how to defend yourself from such attacks.

### Testing

If you have built PHP as a CGI program, you may test your build by
typing **make test**. It is always a good idea to test your build. This
way you may catch a problem with PHP on your platform early instead of
having to struggle with it later.

### Using Variables

Some
<a href="/reserved/variables/server.html" class="link">server supplied environment variables</a>
are not defined in the current
<a href="http://www.faqs.org/rfcs/rfc3875" class="link external">» CGI/1.1 specification</a>.
Only the following variables are defined there: `AUTH_TYPE`,
`CONTENT_LENGTH`, `CONTENT_TYPE`, `GATEWAY_INTERFACE`, `PATH_INFO`,
`PATH_TRANSLATED`, `QUERY_STRING`, `REMOTE_ADDR`, `REMOTE_HOST`,
`REMOTE_IDENT`, `REMOTE_USER`, `REQUEST_METHOD`, `SCRIPT_NAME`,
`SERVER_NAME`, `SERVER_PORT`, `SERVER_PROTOCOL`, and `SERVER_SOFTWARE`.
Everything else should be treated as 'vendor extensions'.
