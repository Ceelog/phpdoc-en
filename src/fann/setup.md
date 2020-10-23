Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/fann/setup.html#Requirements)
-   [Installation](/fann/setup.html#Installation)
-   [Runtime Configuration](/fann/setup.html#Runtime%20Configuration)
-   [Resource Types](/fann/setup.html#Resource%20Types)

Requirements
------------

PHP \>= 5.2.0 and libfann \>= 2.1.0

Installation
------------

The FANN PHP extension should work on all Linux systems.

-   <a href="/fann/setup.html#FANN%20Library%20Installation" class="xref"></a>
-   <a href="/fann/setup.html#PECL%20Installation" class="xref"></a>
-   <a href="/fann/setup.html#Manual%20Installation" class="xref"></a>

FANN Library Installation
-------------------------

Before you start installation make sure that *libfann* is installed on
your system. It's part of the main repository in the most Linux
distributions (search for *fann*). You need a development version.

If it is not installed, you need to install it first. Either download it
from the
<a href="http://leenissen.dk/fann/wp/" class="link external">» official site</a>
or get it from your distro repository. For example on Fedora:


    $ sudo yum install fann-devel

or Ubuntu:


    $ sudo apt-get install libfann-dev

If the library is re-installed manually, then all old library file
should be removed before re-installing otherwise the old library version
could be linked.

PECL Installation
-----------------

This extension is available on PECL. The installation is very simple.
Just run:


    $ sudo pecl install fann

Manual Installation
-------------------

For developers and people interested in the latest changes, you can
compile the driver from the latest source code on
<a href="https://github.com/bukka/php-fann" class="link external">» Github</a>.
Go to Github and click the "Download ZIP" button. Then run:


    $ unzip php-fann-master.zip
    $ cd php-fann-master
    $ phpize
    $ ./configure
    $ make all
    $ sudo make install

Make the following changes to php.ini:

-   Make sure the *extension\_dir* variable is pointing to the directory
    containing *fann.so*. The build will display where it is installing
    the PHP driver with output that looks something like:


        Installing '/usr/lib/php/extensions/no-debug-non-zts-20060613/fann.so'

    Make sure that it is the same as the PHP extension directory by
    running:


        $ php -i | grep extension_dir
          extension_dir => /usr/lib/php/extensions/no-debug-non-zts-20060613 =>
                           /usr/lib/php/extensions/no-debug-non-zts-20060613

    If it's not, change the *extension\_dir* in php.ini or move
    *fann.so*.

-   To load the extension on PHP startup, add a line:


        extension=fann.so

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------
