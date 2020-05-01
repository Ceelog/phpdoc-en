Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/fdf/setup.html#Requirements)
-   [Installation](/fdf/setup.html#Installation)
-   [Runtime Configuration](/fdf/setup.html#Runtime%20Configuration)
-   [Resource Types](/fdf/setup.html#Resource%20Types)

Requirements
------------

You need the FDF toolkit SDK available from
<a href="http://www.adobe.com/devnet/acrobat/fdftoolkit.html" class="link external">» http://www.adobe.com/devnet/acrobat/fdftoolkit.html</a>.
As of PHP 4.3.0 you need at least SDK version 5.0. The FDF toolkit
library is available in binary form only, platforms supported by Adobe
are Win32, Linux, Solaris and AIX.

Installation
------------

This extension is considered unmaintained and dead. However, the source
code for this extension is still available within PECL SVN here:
<a href="https://svn.php.net/viewvc/pecl/fdf" class="link external">» https://svn.php.net/viewvc/pecl/fdf</a>.

This extension is no longer bundled with PHP as of PHP 5.3.0.

> **Note**: <span class="simpara"> If you run into problems configuring
> PHP with fdftk support, check whether the header file `fdftk.h` and
> the library `libfdftk.so` are at the right place. The **configure**
> script supports both the directory structure of the FDF SDK
> distribution and the usual `DIR/include` / `DIR/lib` layout, so you
> can point it either directly to the unpacked distribution directory or
> put the header file and the appropriate library for your platform into
> e.g. `/usr/local/include` and `/usr/local/lib` and configure with
> **--with-fdftk=/usr/local**. </span>

> **Note**: **Note to Win32 Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `fdftk.dll`

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

Most fdf functions require a `fdf` resource as their first parameter. A
`fdf` resource is a handle to an opened fdf file. `fdf` resources may be
obtained using <span class="function">fdf\_create</span>, <span
class="function">fdf\_open</span> and <span
class="function">fdf\_open\_string</span>.
