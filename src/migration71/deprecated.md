Deprecated features in PHP 7.1.x
--------------------------------

### ext/mcrypt

The mcrypt extension has been abandonware for nearly a decade now, and
was also fairly complex to use. It has therefore been deprecated in
favour of OpenSSL, where it will be removed from the core and into PECL
in PHP 7.2.

### Eval option for <span class="function">mb\_ereg\_replace</span> and <span class="function">mb\_eregi\_replace</span>

The *e* pattern modifier has been deprecated for the <span
class="function">mb\_ereg\_replace</span> and <span
class="function">mb\_eregi\_replace</span> functions.
