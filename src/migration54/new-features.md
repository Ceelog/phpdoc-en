New features
------------

PHP 5.4.0 offers a wide range of new features:

-   <span class="simpara"> Support for
    <a href="/language/oop5/traits.html" class="link">traits</a> has
    been added. </span>
-   <span class="simpara"> Short array syntax has been added, e.g. *$a =
    \[1, 2, 3, 4\];* or *$a = \['one' =\> 1, 'two' =\> 2, 'three' =\> 3,
    'four' =\> 4\];*. </span>
-   <span class="simpara"> Function array dereferencing has been added,
    e.g. *foo()\[0\]*. </span>
-   <span class="simpara">
    <a href="/functions/anonymous.html" class="link">Closures</a> now
    support *$this*. </span>
-   <span class="simpara"> *\<?=* is now always available, regardless of
    the
    <a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
    `php.ini` option. </span>
-   <span class="simpara"> Class member access on instantiation has been
    added, e.g. *(new Foo)-\>bar()*. </span>
-   <span class="simpara"> *Class::{expr}()* syntax is now supported.
    </span>
-   <span class="simpara"> Binary number format has been added, e.g.
    *0b001001101*. </span>
-   <span class="simpara"> Improved parse error messages and improved
    incompatible arguments warnings. </span>
-   <span class="simpara"> The session extension can now track the
    <a href="/session/upload-progress.html" class="link">upload progress</a>
    of files. </span>
-   <span class="simpara"> Built-in development
    <a href="/features/commandline/webserver.html" class="link">web server in CLI mode</a>.
    </span>
-   <span class="simpara"> The GD extension now supports reading and
    writing of WebP images via <span
    class="function">imagecreatefromwebp</span> and <span
    class="function">imagewebp</span>, respectively. </span>
