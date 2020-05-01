Building PHP for extension development
--------------------------------------

In a typical PHP installation, the need for high performance almost
always results in optimization at the cost of debugging facilities. This
is a reasonable tradeoff for production use, but when developing an
extension it falls short. What we need is a build of PHP which will give
us some hints what has gone wrong when something does.

The Zend Engine provides a memory manager which is capable of tracking
memory leaks in extensions and providing detailed debugging information.
This tracking is disabled by default, as is thread-safety. To turn them
on, pass the **--enable-debug** and *--enable-maintainer-zts* options to
`configure`, along with whatever options you typically use. For
instructions on building PHP from source, see the instructions at
<a href="/install/general.html" class="xref">General Installation Considerations</a>.
A typical `configure` line might look like this:

``` shell
$ ./configure --prefix=/where/to/install/php --enable-debug --enable-maintainer-zts --enable-cgi --enable-cli --with-mysql=/path/to/mysql
```
