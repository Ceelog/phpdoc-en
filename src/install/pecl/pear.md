Compiling shared PECL extensions with the pecl command
------------------------------------------------------

PECL makes it easy to create shared PHP extensions. Using the
<a href="https://pear.php.net/manual/en/guide.users.commandline.cli.php" class="link external">» pecl command</a>,
do the following:

  
$ pecl install extname  

This will download the source for *extname*, compile, and install
`extname.so` into your
<a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>.
`extname.so` may then be loaded via `php.ini`

By default, the *pecl* command will not install packages that are marked
with the *alpha* or *beta* state. If no *stable* packages are available,
you may install a *beta* package using the following command:

  
$ pecl install extname-beta  

You may also install a specific version using this variant:

  
$ pecl install extname-0.1  

> **Note**:
>
> After enabling the extension in `php.ini`, restarting the web service
> is required for the changes to be picked up.
