<span class="productname">Solaris</span> specific installation tips
-------------------------------------------------------------------

This section contains notes and hints specific to installing PHP on
<span class="productname">Solaris</span> systems.

### Required software

<span class="productname">Solaris</span> installs often lack C compilers
and their related tools. Read
<a href="/faq/build.html#faq.installation.needgnu" class="link">this FAQ</a>
for information on why using GNU versions for some of these tools is
necessary.

For unpacking the PHP distribution you need

-   <span class="simpara"> tar </span>
-   <span class="simpara"> gzip or </span>
-   <span class="simpara"> bzip2 </span>

For compiling PHP you need

-   <span class="simpara"> gcc (recommended, other C compilers may work)
    </span>
-   <span class="simpara"> make </span>
-   <span class="simpara"> GNU sed </span>

For building extra extensions or hacking the code of PHP you might also
need

-   <span class="simpara"> flex (up to PHP 5.2) </span>
-   <span class="simpara"> re2c </span>
-   <span class="simpara"> bison </span>
-   <span class="simpara"> m4 </span>
-   <span class="simpara"> autoconf </span>
-   <span class="simpara"> automake </span>

In addition, you will need to install (and possibly compile) any
additional software specific to your configuration, such as Oracle or
MySQL.

### Using Packages

You can simplify the <span class="productname">Solaris</span> install
process by using pkgadd to install most of your needed components. The
Image Packaging System (IPS) for <span class="productname">Solaris 11
Express</span> also contains most of the required components for
installation using the pkg command.
