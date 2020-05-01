Changes in SAPI Modules
-----------------------

### <a href="/book/fpm.html" class="link">FPM</a>

#### Unqualified <a href="/install/fpm/configuration.html#listen" class="link">listen</a> ports now listen on both IPv4 and IPv6

In PHP 5, a
<a href="/install/fpm/configuration.html#listen" class="link">listen</a>
directive with only a port number would listen on all interfaces, but
only on IPv4. PHP 7 will now accept requests made via both IPv4 and
IPv6.

This does not affect directives which include specific IP addresses;
these will continue to only listen on that address and protocol.
