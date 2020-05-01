Compiling shared PECL extensions with phpize
--------------------------------------------

Sometimes, using the *pecl* installer is not an option. This could be
because you're behind a firewall, or it could be because the extension
you want to install is not available as a PECL compatible package, such
as unreleased extensions from SVN. If you need to build such an
extension, you can use the lower-level build tools to perform the build
manually.

The *phpize* command is used to prepare the build environment for a PHP
extension. In the following sample, the sources for an extension are in
a directory named `extname`:

    $ cd extname
    $ phpize
    $ ./configure
    $ make
    # make install

A successful install will have created `extname.so` and put it into the
PHP
<a href="/ini/core.html#ini.extension-dir" class="link">extensions directory</a>.
You'll need to and adjust `php.ini` and add an *extension=extname.so*
line before you can use the extension.

If the system is missing the *phpize* command, and precompiled packages
(like RPM's) are used, be sure to also install the appropriate devel
version of the PHP package as they often include the *phpize* command
along with the appropriate header files to build PHP and its extensions.

Execute **phpize --help** to display additional usage information.
