Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/wkhtmltox/setup.html#Requirements)
-   [Installation](/wkhtmltox/setup.html#Installation)
-   [Runtime
    Configuration](/wkhtmltox/setup.html#Runtime%20Configuration)

Requirements
------------

libwkhtmltox source and binary releases are distributed at
<a href="http://wkhtmltopdf.org" class="link external">» wkhtmltopdf.org</a>.

**Caution**

Windows users need to take the additional step of adding `wkhtmltox.dll`
to their `PATH`.

Installation
------------

The source code of this extension, and binaries for Windows are hosted
by
<a href="https://github.com/krakjoe/wkhtmltox" class="link external">» github</a>,

Fetching the source code and building the extension:

    git clone https://github.com/krakjoe/wkhtmltox
    cd wkhtmltox
    phpize
    ./configure --with-wkhtmltox=/path/to/wkhtmltox/installation
    make
    sudo make install
       

Fetching updates and rebuilding the extension:

    cd wkhtmltox
    phpize --clean
    git pull origin master
    phpize
    ./configure --with-wkhtmltox=/path/to/wkhtmltox/installation
    make
    sudo make install
       

Runtime Configuration
---------------------

| Name               | Description                        | Default | Stage                                | Changelog |
|--------------------|------------------------------------|---------|--------------------------------------|-----------|
| wkhtmltox.graphics | allow libwkhtmltox to use graphics | Off     | PHP\_INI\_SYSTEM \| PHP\_INI\_PERDIR | \>= 0.3.2 |
