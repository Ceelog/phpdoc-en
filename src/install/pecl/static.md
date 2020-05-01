Compiling PECL extensions statically into PHP
---------------------------------------------

You might find that you need to build a PECL extension statically into
your PHP binary. To do this, you'll need to place the extension source
under the `/your/phpsrcdir/ext/` directory and tell the PHP build system
to regenerate its configure script.

    $ cd /your/phpsrcdir/ext
    $ pecl download extname
    $ gzip -d < extname.tgz | tar -xvf -
    $ mv extname-x.x.x extname

This will result in the following directory:

  
/your/phpsrcdir/ext/extname  

From here, force PHP to rebuild the configure script, and then build PHP
as normal:

  
$ cd /your/phpsrcdir  
$ rm configure  
$ ./buildconf --force  
$ ./configure --help  
$ ./configure --with-extname --enable-someotherext --with-foobar  
$ make  
$ make install  

> **Note**: <span class="simpara"> To run the 'buildconf' script you
> need autoconf 2.13 and automake 1.4+ (newer versions of autoconf may
> work, but are not supported). </span>

Whether *--enable-extname* or *--with-extname* is used depends on the
extension. Typically an extension that does not require external
libraries uses *--enable*. To be sure, run the following after
buildconf:

  
$ ./configure --help \| grep extname  
