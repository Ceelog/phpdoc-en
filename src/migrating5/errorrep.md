Error Reporting
---------------

As of PHP 5 the error reporting constant **`E_STRICT`** is available,
with the value *2048*. When enabled, messages will be issued to warn you
about code usage which is deprecated or which may not be future-proof.

> **Note**: <span class="simpara"> **`E_ALL`** does not include
> **`E_STRICT`**, so it's not enabled by default. You must explicitly
> set the error reporting level to include **`E_STRICT`** in order to
> see these messages. </span>

See
<a href="/errorfunc/constants.html" class="link">Predefined Constants</a>
for more information.
