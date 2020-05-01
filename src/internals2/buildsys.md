The PHP 5 build system
======================

**Table of Contents**

-   [Building PHP for extension
    development](/internals2/buildsys/environment.html)
-   [The ext\_skel script](/internals2/buildsys/skeleton.html)
-   [Talking to the UNIX build system:
    config.m4](/internals2/buildsys/configunix.html)
-   [Talking to the Windows build system:
    config.w32](/internals2/buildsys/configwin.html)

With all the functionality and flexibility available in PHP 5, it is no
surprise that it consists of several thousand files and over one million
lines of source code. Equally unsurprising is the necessity of a build
system to manage so much data. This section describes how to set PHP up
for extension development, the layout of an extension within the PHP
source tree, and how to interface your extension with the build system.
