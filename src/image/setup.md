Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/image/setup.html#Requirements)
-   [Installation](/image/setup.html#Installation)
-   [Runtime Configuration](/image/setup.html#Runtime%20Configuration)
-   [Resource Types](/image/setup.html#Resource%20Types)

Requirements
------------

If you have the GD library (available at
<a href="http://www.libgd.org/" class="link external">» http://www.libgd.org/</a>)
you will also be able to create and manipulate images.

The format of images you are able to manipulate depend on the version of
GD you install, and any other libraries GD might need to access those
image formats. GIF support is available as of gd-2.0.28.

> **Note**: <span class="simpara"> libgd-2.0.4 or higher is required. As
> of PHP 5.5 libgd-2.1.0 or higher is required. Alternatively, use the
> bundled GD library that ships with PHP. </span>

You may wish to enhance GD to handle more image formats.

| Image format | Library to download                                                                                                                         | Notes                                                                                                                                                                                                                                                     |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *gif*        |                                                                                                                                             | Only supported in GD versions newer than gd-2.0.28. *Write* support is available as of PHP 5.0.1.                                                                                                                                                         |
| *jpeg*       | <a href="http://www.ijg.org/" class="link external">» http://www.ijg.org/</a>                                                               | When building the jpeg library (prior to building PHP) you must use the **--enable-shared** option in the configure step. If you do not, you will receive an error saying *libjpeg.(a\|so) not found* when you get to the configure step of building PHP. |
| *png*        | <a href="http://www.libpng.org/pub/png/libpng.html" class="link external">» http://www.libpng.org/pub/png/libpng.html</a>                   |                                                                                                                                                                                                                                                           |
| *xpm*        | <a href="ftp://metalab.unc.edu/pub/Linux/libs/X/!INDEX.html" class="link external">» ftp://metalab.unc.edu/pub/Linux/libs/X/!INDEX.html</a> | It's likely you have this library already available, if your system has an installed X-Environment.                                                                                                                                                       |

You may wish to enhance GD to deal with different fonts. The following
font libraries are supported:

| Font library   | Download                                                                                                                             | Notes                                                          |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| *FreeType 1.x* | <a href="http://www.freetype.org/" class="link external">» http://www.freetype.org/</a>                                              | Support for FreeType 1.x has been removed as of PHP 5.3.0.     |
| *FreeType 2*   | <a href="http://www.freetype.org/" class="link external">» http://www.freetype.org/</a>                                              |                                                                |
| *T1lib*        | <a href="ftp://sunsite.unc.edu/pub/Linux/libs/graphics/" class="link external">» ftp://sunsite.unc.edu/pub/Linux/libs/graphics/</a>) | Support for Postscript Type 1 fonts (Removed as of PHP 7.0.0). |

Installation
------------

To enable GD-support configure PHP **--with-gd\[=DIR\]**, where DIR is
the GD base install directory. To use the recommended bundled version of
the GD library, use the configure option **--with-gd**. GD library
requires <span class="productname">libpng</span> and <span
class="productname">libjpeg</span> to compile.

In Windows, you'll include the GD2 DLL `php_gd2.dll` as an extension in
`php.ini`.

Enhance the capabilities of GD to handle more image formats by
specifying the *--with-XXXX* configure switch to your PHP configure
line.

| Image Format | Configure Switch                                                                                                                                                                                                         |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *jpeg*       | To enable support for jpeg add **--with-jpeg-dir=DIR**. Jpeg 6b, 7 or 8 are supported.                                                                                                                                   |
| *png*        | To enable support for png add **--with-png-dir=DIR**. Note, libpng requires the <a href="/zlib/setup.html#Requirements" class="link">zlib library</a>, therefore add **--with-zlib-dir\[=DIR\]** to your configure line. |
| *xpm*        | To enable support for xpm add **--with-xpm-dir=DIR**. If configure is not able to find the required libraries, you may add the path to your X11 libraries.                                                               |
| *webp*       | To enable support for webp add **--with-vpx-dir=DIR**. Available as of PHP 5.4.0. As of PHP 7.0.0 **--with-webp-dir=DIR** has to be added, i.e. support for libvpx has been removed in favor of libwebp.                 |

> **Note**: <span class="simpara"> When compiling PHP with libpng, you
> must use the same version that was linked with the GD library. </span>

Enhance the capabilities of GD to deal with different fonts by
specifying the *--with-XXXX* configure switch to your PHP configure
line.

| Font library                      | Configure Switch                                                                                                                                                                |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *FreeType 2*                      | To enable support for FreeType 2 add **--with-freetype-dir=DIR**. As of PHP 7.4.0 use **--with-freetype** instead, which relies on <span class="productname">pkg-config</span>. |
| *T1lib*                           | To enable support for T1lib (Postscript Type 1 fonts) add **--with-t1lib\[=DIR\]** (Removed as of PHP 7.0.0).                                                                   |
| *Native TrueType string function* | To enable support for native TrueType string function add **--enable-gd-native-ttf**. (Effectless as of PHP 5.5.0; removed as of PHP 7.2.0.)                                    |

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                 | Default | Changeable    | Changelog                  |
|----------------------------------------------------------------------|---------|---------------|----------------------------|
| <a href="/image/setup.html#" class="link">gd.jpeg_ignore_warning</a> | "1"     | PHP\_INI\_ALL | Available since PHP 5.1.3. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`gd.jpeg_ignore_warning` <span class="type">bool</span>  
Ignore warnings (but not errors) created by libjpeg(-turbo).

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.1.0   | The default of gd.jpeg\_ignore\_warning has been changed from 0 to 1. |

See also the
<a href="/exif/setup.html#Runtime%20Configuration" class="link">exif</a>
configuration directives.

**Warning**

Image functions are very memory intensive. Be sure to set
<a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>
high enough, if you are using the bundled version of the GD library.

Resource Types
--------------

This extension defines the following resource types:

| Name             | Description                                                                                      | Notes                    |
|------------------|--------------------------------------------------------------------------------------------------|--------------------------|
| *gd*             | Image resource, used by functions like <span class="function">imagecreatefrompng</span>          |                          |
| *gd font*        | Font resource internally created by <span class="function">imageloadfont</span>                  |                          |
| *gd PS font*     | PostScript Type 1 font resource, returned by <span class="function">imagepsloadfont</span>       | Removed as of PHP 7.0.0. |
| *gd PS encoding* | PostScript Type 1 encoding resource, returned by <span class="function">imagepsencodefont</span> | Removed as of PHP 7.0.0. |
