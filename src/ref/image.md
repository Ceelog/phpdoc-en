gd\_info
========

Retrieve information about the currently installed GD library

### Description

<span class="type">array</span> <span class="methodname">gd\_info</span>
( <span class="methodparam">void</span> )

Gets information about the version and capabilities of the installed GD
library.

### Return Values

Returns an associative array.

| Attribute          | Meaning                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GD Version         | <span class="type">string</span> value describing the installed *libgd* version.                                                                                                                                                                               |
| FreeType Support   | <span class="type">bool</span> value. **`true`** if FreeType Support is installed.                                                                                                                                                                             |
| FreeType Linkage   | <span class="type">string</span> value describing the way in which FreeType was linked. Expected values are: 'with freetype', 'with TTF library', and 'with unknown library'. This element will only be defined if *FreeType Support* evaluated to **`true`**. |
| GIF Read Support   | <span class="type">bool</span> value. **`true`** if support for *reading* *GIF* images is included.                                                                                                                                                            |
| GIF Create Support | <span class="type">bool</span> value. **`true`** if support for *creating* *GIF* images is included.                                                                                                                                                           |
| JPEG Support       | <span class="type">bool</span> value. **`true`** if *JPEG* support is included.                                                                                                                                                                                |
| PNG Support        | <span class="type">bool</span> value. **`true`** if *PNG* support is included.                                                                                                                                                                                 |
| WBMP Support       | <span class="type">bool</span> value. **`true`** if *WBMP* support is included.                                                                                                                                                                                |
| XBM Support        | <span class="type">bool</span> value. **`true`** if *XBM* support is included.                                                                                                                                                                                 |
| WebP Support       | <span class="type">bool</span> value. **`true`** if *WebP* support is included.                                                                                                                                                                                |

### Examples

**Example \#1 Using <span class="function">gd\_info</span>**

``` php
<?php
var_dump(gd_info());
?>
```

The above example will output something similar to:

    array(10) {
      ["GD Version"]=>
      string(24) "bundled (2.1.0 compatible)"
      ["FreeType Support"]=>
      bool(false)
      ["GIF Read Support"]=>
      bool(true)
      ["GIF Create Support"]=>
      bool(false)
      ["JPEG Support"]=>
      bool(false)
      ["PNG Support"]=>
      bool(true)
      ["WBMP Support"]=>
      bool(true)
      ["XBM Support"]=>
      bool(false)
      ["WebP Support"]=>
      bool(false)
    }

### See Also

-   <span class="function">imagepng</span>
-   <span class="function">imagejpeg</span>
-   <span class="function">imagegif</span>
-   <span class="function">imagewbmp</span>
-   <span class="function">imagewebp</span>
-   <span class="function">imagetypes</span>

getimagesize
============

Get the size of an image

### Description

<span class="type">array</span> <span
class="methodname">getimagesize</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$imageinfo`</span>
\] )

The <span class="function">getimagesize</span> function will determine
the size of any supported given image file and return the dimensions
along with the file type and a *height/width* text string to be used
inside a normal HTML `IMG` tag and the correspondent HTTP content type.

<span class="function">getimagesize</span> can also return some more
information in `imageinfo` parameter.

**Caution**

This function expects `filename` to be a valid image file. If a
non-image file is supplied, it may be incorrectly detected as an image
and the function will return successfully, but the array may contain
nonsensical values.

Do not use <span class="function">getimagesize</span> to check that a
given file is a valid image. Use a purpose-built solution such as the
<a href="/book/fileinfo.html" class="link">Fileinfo</a> extension
instead.

> **Note**: <span class="simpara"> Note that JPC and JP2 are capable of
> having components with different bit depths. In this case, the value
> for "bits" is the highest bit depth encountered. Also, JP2 files may
> contain *multiple JPEG 2000 codestreams*. In this case, <span
> class="function">getimagesize</span> returns the values for the first
> codestream it encounters in the root of the file. </span>

> **Note**: <span class="simpara"> The information about icons are
> retrieved from the icon with the highest bitrate. </span>

> **Note**: <span class="simpara"> GIF images consist of one or more
> frames, where each frame may only occupy part of the image. The size
> of the image which is reported by <span
> class="function">getimagesize</span> is the overall size (read from
> the logical screen descriptor). </span>

### Parameters

`filename`  
This parameter specifies the file you wish to retrieve information
about. It can reference a local file or (configuration permitting) a
remote file using one of the
<a href="/wrappers.html" class="link">supported streams</a>.

`imageinfo`  
This optional parameter allows you to extract some extended information
from the image file. Currently, this will return the different JPG APP
markers as an associative array. Some programs use these APP markers to
embed text information in images. A very common one is to embed
<a href="http://www.iptc.org/" class="link external">» IPTC</a>
information in the APP13 marker. You can use the <span
class="function">iptcparse</span> function to parse the binary APP13
marker into something readable.

> **Note**:
>
> The `imageinfo` only supports JFIF files.

### Return Values

Returns an array with up to 7 elements. Not all image types will include
the *channels* and *bits* elements.

Index 0 and 1 contains respectively the width and the height of the
image.

> **Note**:
>
> Some formats may contain no image or may contain multiple images. In
> these cases, <span class="function">getimagesize</span> might not be
> able to properly determine the image size. <span
> class="function">getimagesize</span> will return zero for width and
> height in these cases.

Index 2 is one of the
<a href="/image/constants.html" class="link">IMAGETYPE_XXX constants</a>
indicating the type of the image.

Index 3 is a text string with the correct *height="yyy" width="xxx"*
string that can be used directly in an IMG tag.

*mime* is the correspondant MIME type of the image. This information can
be used to deliver images with the correct HTTP *Content-type* header:

**Example \#1 <span class="function">getimagesize</span> and MIME
types**

``` php
<?php
$size = getimagesize($filename);
$fp = fopen($filename, "rb");
if ($size && $fp) {
    header("Content-type: {$size['mime']}");
    fpassthru($fp);
    exit;
} else {
    // error
}
?>
```

*channels* will be 3 for RGB pictures and 4 for CMYK pictures.

*bits* is the number of bits for each color.

For some image types, the presence of *channels* and *bits* values can
be a bit confusing. As an example, GIF always uses 3 channels per pixel,
but the number of bits per pixel cannot be calculated for an animated
GIF with a global color table.

On failure, **`false`** is returned.

### Errors/Exceptions

If accessing the `filename` image is impossible <span
class="function">getimagesize</span> will generate an error of level
**`E_WARNING`**. On read error, <span
class="function">getimagesize</span> will generate an error of level
**`E_NOTICE`**.

### Changelog

| Version | Description         |
|---------|---------------------|
| 7.1.0   | Added WebP support. |

### Examples

**Example \#2 <span class="function">getimagesize</span> example**

``` php
<?php
list($width, $height, $type, $attr) = getimagesize("img/flag.jpg");
echo "<img src=\"img/flag.jpg\" $attr alt=\"getimagesize() example\" />";
?>
```

**Example \#3 getimagesize (URL)**

``` php
<?php
$size = getimagesize("http://www.example.com/gifs/logo.gif");

// if the file name has space in it, encode it properly
$size = getimagesize("http://www.example.com/gifs/lo%20go.gif");

?>
```

**Example \#4 getimagesize() returning IPTC**

``` php
<?php
$size = getimagesize("testimg.jpg", $info);
if (isset($info["APP13"])) {
    $iptc = iptcparse($info["APP13"]);
    var_dump($iptc);
}
?>
```

### Notes

> **Note**:
>
> This function does not require the GD image library.

### See Also

-   <span class="function">image\_type\_to\_mime\_type</span>
-   <span class="function">exif\_imagetype</span>
-   <span class="function">exif\_read\_data</span>
-   <span class="function">exif\_thumbnail</span>
-   <span class="function">imagesx</span>
-   <span class="function">imagesy</span>

getimagesizefromstring
======================

Get the size of an image from a string

### Description

<span class="type">array</span> <span
class="methodname">getimagesizefromstring</span> ( <span
class="methodparam"><span class="type">string</span> `$imagedata`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$imageinfo`</span> \] )

Identical to <span class="function">getimagesize</span> except that
<span class="function">getimagesizefromstring</span> accepts a string
instead of a file name as the first parameter.

See the <span class="function">getimagesize</span> documentation for
details on how this function works.

### Parameters

`imagedata`  
The image data, as a string.

`imageinfo`  
See <span class="function">getimagesize</span>.

### Return Values

See <span class="function">getimagesize</span>.

### Examples

**Example \#1 <span class="function">getimagesizefromstring</span>
example**

``` php
<?php
$img = '/path/to/test.png';

// Open as a file
$size_info1 = getimagesize($img);

// Or open as a string
$data       = file_get_contents($img);
$size_info2 = getimagesizefromstring($data);
?>
```

### See Also

-   <span class="function">getimagesize</span>

image\_type\_to\_extension
==========================

Get file extension for image type

### Description

<span class="type">string</span> <span
class="methodname">image\_type\_to\_extension</span> ( <span
class="methodparam"><span class="type">int</span> `$imagetype`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$include_dot`<span class="initializer"> = **`true`**</span></span> \] )

Returns the extension for the given *IMAGETYPE\_XXX* constant.

### Parameters

`imagetype`  
One of the *IMAGETYPE\_XXX* constant.

`include_dot`  
Whether to prepend a dot to the extension or not. Default to **`true`**.

### Return Values

A string with the extension corresponding to the given image type.

### Examples

**Example \#1 <span class="function">image\_type\_to\_extension</span>
example**

``` php
<?php
// Create image instance
$im = imagecreatetruecolor(100, 100);

// Save image
imagepng($im, './test' . image_type_to_extension(IMAGETYPE_PNG));
imagedestroy($im);
?>
```

### Notes

> **Note**:
>
> This function does not require the GD image library.

image\_type\_to\_mime\_type
===========================

Get Mime-Type for image-type returned by getimagesize, exif\_read\_data,
exif\_thumbnail, exif\_imagetype

### Description

<span class="type">string</span> <span
class="methodname">image\_type\_to\_mime\_type</span> ( <span
class="methodparam"><span class="type">int</span> `$imagetype`</span> )

The <span class="function">image\_type\_to\_mime\_type</span> function
will determine the Mime-Type for an IMAGETYPE constant.

### Parameters

`imagetype`  
One of the *IMAGETYPE\_XXX* constants.

### Return Values

The returned values are as follows

| `imagetype`                                   | Returned value                  |
|-----------------------------------------------|---------------------------------|
| **`IMAGETYPE_GIF`**                           | *image/gif*                     |
| **`IMAGETYPE_JPEG`**                          | *image/jpeg*                    |
| **`IMAGETYPE_PNG`**                           | *image/png*                     |
| **`IMAGETYPE_SWF`**                           | *application/x-shockwave-flash* |
| **`IMAGETYPE_PSD`**                           | *image/psd*                     |
| **`IMAGETYPE_BMP`**                           | *image/bmp*                     |
| **`IMAGETYPE_TIFF_II`** (intel byte order)    | *image/tiff*                    |
| **`IMAGETYPE_TIFF_MM`** (motorola byte order) | *image/tiff*                    |
| **`IMAGETYPE_JPC`**                           | *application/octet-stream*      |
| **`IMAGETYPE_JP2`**                           | *image/jp2*                     |
| **`IMAGETYPE_JPX`**                           | *application/octet-stream*      |
| **`IMAGETYPE_JB2`**                           | *application/octet-stream*      |
| **`IMAGETYPE_SWC`**                           | *application/x-shockwave-flash* |
| **`IMAGETYPE_IFF`**                           | *image/iff*                     |
| **`IMAGETYPE_WBMP`**                          | *image/vnd.wap.wbmp*            |
| **`IMAGETYPE_XBM`**                           | *image/xbm*                     |
| **`IMAGETYPE_ICO`**                           | *image/vnd.microsoft.icon*      |
| **`IMAGETYPE_WEBP`**                          | *image/webp*                    |

### Examples

**Example \#1 <span class="function">image\_type\_to\_mime\_type</span>
example**

``` php
<?php
header("Content-type: " . image_type_to_mime_type(IMAGETYPE_PNG));
?>
```

### Notes

> **Note**:
>
> This function does not require the GD image library.

### See Also

-   <span class="function">getimagesize</span>
-   <span class="function">exif\_imagetype</span>
-   <span class="function">exif\_read\_data</span>
-   <span class="function">exif\_thumbnail</span>

image2wbmp
==========

Output image to browser or file

**Warning**

<span class="function">image2wbmp</span> is deprecated as of PHP 7.3.0,
and will be removed in the next major version. Use <span
class="function">imagewbmp</span> instead.

### Description

<span class="type">bool</span> <span
class="methodname">image2wbmp</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> \[, <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$foreground`</span> \]\] )

<span class="function">image2wbmp</span> outputs or save a WBMP version
of the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`filename`  
Path to the saved file. If not given, the raw image stream will be
output directly.

`foreground`  
You can set the foreground color with this parameter by setting an
identifier obtained from <span
class="function">imagecolorallocate</span>. The default foreground color
is black.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 <span class="function">image2wbmp</span> example**

``` php
<?php
$file = 'php.png';
$image = imagecreatefrompng($file);

header('Content-Type: ' . image_type_to_mime_type(IMAGETYPE_WBMP));
image2wbmp($image); // output the stream directly
imagedestroy($image);
?>
```

### See Also

-   <span class="function">imagewbmp</span>

imageaffine
===========

Return an image containing the affine transformed src image, using an
optional clipping area

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">imageaffine</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">array</span> `$affine`</span> \[,
<span class="methodparam"><span class="type">array</span> `$clip`</span>
\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`affine`  
Array with keys 0 to 5.

`clip`  
Array with keys "x", "y", "width" and "height".

### Return Values

Return affined image resource on success or **`false`** on failure.

imageaffinematrixconcat
=======================

Concatenate two affine transformation matrices

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">imageaffinematrixconcat</span> ( <span
class="methodparam"><span class="type">array</span> `$m1`</span> , <span
class="methodparam"><span class="type">array</span> `$m2`</span> )

Returns the concatenation of two affine transformation matrices, what is
useful if multiple transformations should be applied to the same image
in one go.

### Parameters

`m1`  
An affine transformation matrix (an array with keys *0* to *5* and float
values).

`m2`  
An affine transformation matrix (an array with keys *0* to *5* and float
values).

### Return Values

An affine transformation matrix (an array with keys *0* to *5* and float
values) or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imageaffinematrixconcat</span>
example**

``` php
<?php
$m1 = imageaffinematrixget(IMG_AFFINE_TRANSLATE, array('x' = 2, 'y' => 3));
$m2 = imageaffinematrixget(IMG_AFFINE_SCALE, array('x' = 4, 'y' => 5));
$matrix = imageaffinematrixconcat($m1, $m2);
print_r($matrix);
?>
```

The above example will output:

    Array
    (
        [0] => 4
        [1] => 0
        [2] => 0
        [3] => 5
        [4] => 8
        [5] => 15
    )

### See Also

-   <span class="function">imageaffine</span>
-   <span class="function">imageaffinematrixget</span>

imageaffinematrixget
====================

Get an affine transformation matrix

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">imageaffinematrixget</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$options`</span> \] )

Returns an affine transformation matrix.

### Parameters

`type`  
One of the **`IMG_AFFINE_*`** constants.

`options`  
If `type` is **`IMG_AFFINE_TRANSLATE`** or **`IMG_AFFINE_SCALE`**,
`options` has to be an <span class="type">array</span> with keys *x* and
*y*, both having <span class="type">float</span> values.

If `type` is **`IMG_AFFINE_ROTATE`**, **`IMG_AFFINE_SHEAR_HORIZONTAL`**
or **`IMG_AFFINE_SHEAR_VERTICAL`**, `options` has to be a <span
class="type">float</span> specifying the angle.

### Return Values

An affine transformation matrix (an array with keys *0* to *5* and float
values) or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imageaffinematrixget</span>
example**

``` php
<?php
$matrix = imageaffinematrixget(IMG_AFFINE_TRANSLATE, array('x' = 2, 'y' => 3));
print_r($matrix);
?>
```

The above example will output:

    Array
    (
        [0] => 1
        [1] => 0
        [2] => 0
        [3] => 1
        [4] => 2
        [5] => 3
    )

### See Also

-   <span class="function">imageaffine</span>
-   <span class="function">imageaffinematrixconcat</span>

imagealphablending
==================

Set the blending mode for an image

### Description

<span class="type">bool</span> <span
class="methodname">imagealphablending</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$blendmode`</span> )

<span class="function">imagealphablending</span> allows for two
different modes of drawing on truecolor images. In blending mode, the
alpha channel component of the color supplied to all drawing function,
such as <span class="function">imagesetpixel</span> determines how much
of the underlying color should be allowed to shine through. As a result,
gd automatically blends the existing color at that point with the
drawing color, and stores the result in the image. The resulting pixel
is opaque. In non-blending mode, the drawing color is copied literally
with its alpha channel information, replacing the destination pixel.
Blending mode is not available when drawing on palette images.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`blendmode`  
Whether to enable the blending mode or not. On true color images the
default value is **`true`** otherwise the default value is **`false`**

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagealphablending</span> usage
example**

``` php
<?php
// Create image
$im = imagecreatetruecolor(100, 100);

// Set alphablending to on
imagealphablending($im, true);

// Draw a square
imagefilledrectangle($im, 30, 30, 70, 70, imagecolorallocate($im, 255, 0, 0));

// Output
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

imageantialias
==============

Should antialias functions be used or not

### Description

<span class="type">bool</span> <span
class="methodname">imageantialias</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$enabled`</span> )

Activate the fast drawing antialiased methods for lines and wired
polygons. It does not support alpha components. It works using a direct
blend operation. It works only with truecolor images.

Thickness and styled are not supported.

Using antialiased primitives with transparent background color can end
with some unexpected results. The blend method uses the background color
as any other colors. The lack of alpha component support does not allow
an alpha based antialiasing method.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`enabled`  
Whether to enable antialiasing or not.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                                                             |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">imageantialias</span> is now generally available. Formerly it was only available if PHP was compiled with the bundled version of the GD library. |

### Examples

**Example \#1 A comparison of two lines, one with anti-aliasing switched
on**

``` php
<?php
// Setup an anti-aliased image and a normal image
$aa = imagecreatetruecolor(400, 100);
$normal = imagecreatetruecolor(200, 100);

// Switch antialiasing on for one image
imageantialias($aa, true);

// Allocate colors
$red = imagecolorallocate($normal, 255, 0, 0);
$red_aa = imagecolorallocate($aa, 255, 0, 0);

// Draw two lines, one with AA enabled
imageline($normal, 0, 0, 200, 100, $red);
imageline($aa, 0, 0, 200, 100, $red_aa);

// Merge the two images side by side for output (AA: left, Normal: Right)
imagecopymerge($aa, $normal, 200, 0, 0, 0, 200, 100, 100);

// Output image
header('Content-type: image/png');

imagepng($aa);
imagedestroy($aa);
imagedestroy($normal);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageantialias.png" width="400" height="100" alt="Output of example : A comparison of two lines, one with anti-aliasing switched on" />

### See Also

-   <span class="function">imagecreatetruecolor</span>

imagearc
========

Draws an arc

### Description

<span class="type">bool</span> <span class="methodname">imagearc</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">int</span> `$cx`</span> , <span class="methodparam"><span
class="type">int</span> `$cy`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> ,
<span class="methodparam"><span class="type">int</span> `$start`</span>
, <span class="methodparam"><span class="type">int</span> `$end`</span>
, <span class="methodparam"><span class="type">int</span>
`$color`</span> )

<span class="function">imagearc</span> draws an arc of circle centered
at the given coordinates.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`cx`  
x-coordinate of the center.

`cy`  
y-coordinate of the center.

`width`  
The arc width.

`height`  
The arc height.

`start`  
The arc start angle, in degrees.

`end`  
The arc end angle, in degrees. 0° is located at the three-o'clock
position, and the arc is drawn clockwise.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Drawing a circle with <span
class="function">imagearc</span>**

``` php
<?php

// create a 200*200 image
$img = imagecreatetruecolor(200, 200);

// allocate some colors
$white = imagecolorallocate($img, 255, 255, 255);
$red   = imagecolorallocate($img, 255,   0,   0);
$green = imagecolorallocate($img,   0, 255,   0);
$blue  = imagecolorallocate($img,   0,   0, 255);

// draw the head
imagearc($img, 100, 100, 200, 200,  0, 360, $white);
// mouth
imagearc($img, 100, 100, 150, 150, 25, 155, $red);
// left and then the right eye
imagearc($img,  60,  75,  50,  50,  0, 360, $green);
imagearc($img, 140,  75,  50,  50,  0, 360, $blue);

// output image in the browser
header("Content-type: image/png");
imagepng($img);

// free memory
imagedestroy($img);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagearc.png" width="200" height="200" alt="Output of example : Drawing a circle with imagearc()" />

### See Also

-   <span class="function">imagefilledarc</span>
-   <span class="function">imageellipse</span>
-   <span class="function">imagefilledellipse</span>

imagebmp
========

Output a BMP image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagebmp</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$compressed`<span class="initializer"> =
**`true`**</span></span> \]\] )

Outputs or saves a BMP version of the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

> **Note**:
>
> **`null`** is invalid if the `compressed` arguments is not used.

`compressed`  
Whether the BMP should be compressed with run-length encoding (RLE), or
not.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Saving a BMP file**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);

imagestring($im, 1, 5, 5,  'BMP with PHP', $text_color);

// Save the image
imagebmp($im, 'php.bmp');

// Free up memory
imagedestroy($im);
?>
```

imagechar
=========

Draw a character horizontally

### Description

<span class="type">bool</span> <span class="methodname">imagechar</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">int</span> `$font`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">string</span> `$c`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

<span class="function">imagechar</span> draws the first character of `c`
in the image identified by `image` with its upper-left at `x`,`y` (top
left is 0, 0) with the color `color`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

`x`  
x-coordinate of the start.

`y`  
y-coordinate of the start.

`c`  
The character to draw.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagechar</span> example**

``` php
<?php

$im = imagecreate(100, 100);

$string = 'PHP';

$bg = imagecolorallocate($im, 255, 255, 255);
$black = imagecolorallocate($im, 0, 0, 0);

// prints a black "P" in the top left corner
imagechar($im, 1, 0, 0, $string, $black);

header('Content-type: image/png');
imagepng($im);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagechar.png" width="100" height="100" alt="Output of example : imagechar()" />

### See Also

-   <span class="function">imagecharup</span>
-   <span class="function">imageloadfont</span>

imagecharup
===========

Draw a character vertically

### Description

<span class="type">bool</span> <span
class="methodname">imagecharup</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$font`</span> , <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">string</span> `$c`</span> , <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Draws the character `c` vertically at the specified coordinate on the
given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

`x`  
x-coordinate of the start.

`y`  
y-coordinate of the start.

`c`  
The character to draw.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagecharup</span> example**

``` php
<?php

$im = imagecreate(100, 100);

$string = 'Note that the first letter is a N';

$bg = imagecolorallocate($im, 255, 255, 255);
$black = imagecolorallocate($im, 0, 0, 0);

// prints a black "Z" on a white background
imagecharup($im, 3, 10, 10, $string, $black);

header('Content-type: image/png');
imagepng($im);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecharup.png" width="100" height="100" alt="Output of example : imagecharup()" />

### See Also

-   <span class="function">imagechar</span>
-   <span class="function">imageloadfont</span>

imagecolorallocate
==================

Allocate a color for an image

### Description

<span class="type">int</span> <span
class="methodname">imagecolorallocate</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
)

Returns a color identifier representing the color composed of the given
RGB components.

<span class="function">imagecolorallocate</span> must be called to
create each color that is to be used in the image represented by
`image`.

> **Note**:
>
> The first call to <span class="function">imagecolorallocate</span>
> fills the background color in palette-based images - images created
> using <span class="function">imagecreate</span>.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

These parameters are integers between 0 and 255 or hexadecimals between
0x00 and 0xFF.

### Return Values

A color identifier or **`false`** if the allocation failed.

**Warning**

This function may return Boolean **`false`**, but may also return a
non-Boolean value which evaluates to **`false`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 <span class="function">imagecolorallocate</span> example**

``` php
<?php

$im = imagecreate(100, 100);

// sets background to red
$background = imagecolorallocate($im, 255, 0, 0);

// sets some colors
$white = imagecolorallocate($im, 255, 255, 255);
$black = imagecolorallocate($im, 0, 0, 0);

// hexadecimal way
$white = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);
$black = imagecolorallocate($im, 0x00, 0x00, 0x00);

?>
```

### See Also

-   <span class="function">imagecolorallocatealpha</span>
-   <span class="function">imagecolordeallocate</span>

imagecolorallocatealpha
=======================

Allocate a color for an image

### Description

<span class="type">int</span> <span
class="methodname">imagecolorallocatealpha</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
, <span class="methodparam"><span class="type">int</span>
`$alpha`</span> )

<span class="function">imagecolorallocatealpha</span> behaves
identically to <span class="function">imagecolorallocate</span> with the
addition of the transparency parameter `alpha`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

`alpha`  
A value between *0* and *127*. *0* indicates completely opaque while
*127* indicates completely transparent.

The `red`, `green` and `blue` parameters are integers between 0 and 255
or hexadecimals between 0x00 and 0xFF.

### Return Values

A color identifier or **`false`** if the allocation failed.

**Warning**

This function may return Boolean **`false`**, but may also return a
non-Boolean value which evaluates to **`false`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 Example of using <span
class="function">imagecolorallocatealpha</span>**

``` php
<?php
$size = 300;
$image=imagecreatetruecolor($size, $size);

// something to get a white background with black border
$back = imagecolorallocate($image, 255, 255, 255);
$border = imagecolorallocate($image, 0, 0, 0);
imagefilledrectangle($image, 0, 0, $size - 1, $size - 1, $back);
imagerectangle($image, 0, 0, $size - 1, $size - 1, $border);

$yellow_x = 100;
$yellow_y = 75;
$red_x    = 120;
$red_y    = 165;
$blue_x   = 187;
$blue_y   = 125;
$radius   = 150;

// allocate colors with alpha values
$yellow = imagecolorallocatealpha($image, 255, 255, 0, 75);
$red    = imagecolorallocatealpha($image, 255, 0, 0, 75);
$blue   = imagecolorallocatealpha($image, 0, 0, 255, 75);

// drawing 3 overlapped circle
imagefilledellipse($image, $yellow_x, $yellow_y, $radius, $radius, $yellow);
imagefilledellipse($image, $red_x, $red_y, $radius, $radius, $red);
imagefilledellipse($image, $blue_x, $blue_y, $radius, $radius, $blue);

// don't forget to output a correct header!
header('Content-Type: image/png');

// and finally, output the result
imagepng($image);
imagedestroy($image);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecolorallocatealpha.png" width="300" height="300" alt="Output of example : Example of using imagecolorallocatealpha()" />

**Example \#2 Convert typical alpha values for use with <span
class="function">imagecolorallocatealpha</span>**

Usually alpha values of *0* designate fully transparent pixels, and the
alpha channel has 8 bits. To convert such alpha values to be compatible
with <span class="function">imagecolorallocatealpha</span>, some simple
arithmetic is sufficient:

``` php
<?php
$alpha8 = 0; // fully transparent
var_dump(127 - ($alpha8 >> 1));
$alpha8 = 255; // fully opaque
var_dump(127 - ($alpha8 >> 1));
?>
```

The above example will output:

    int(127)
    int(0)

### See Also

-   <span class="function">imagecolorallocate</span>
-   <span class="function">imagecolordeallocate</span>

imagecolorat
============

Get the index of the color of a pixel

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">imagecolorat</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> )

Returns the index of the color of the pixel at the specified location in
the image specified by `image`.

If the image is a truecolor image, this function returns the RGB value
of that pixel as integer. Use bitshifting and masking to access the
distinct red, green and blue component values:

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x`  
x-coordinate of the point.

`y`  
y-coordinate of the point.

### Return Values

Returns the index of the color or **`false`** on failure.

**Warning**

This function may return Boolean **`false`**, but may also return a
non-Boolean value which evaluates to **`false`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 Access distinct RGB values**

``` php
<?php
$im = imagecreatefrompng("php.png");
$rgb = imagecolorat($im, 10, 15);
$r = ($rgb >> 16) & 0xFF;
$g = ($rgb >> 8) & 0xFF;
$b = $rgb & 0xFF;

var_dump($r, $g, $b);
?>
```

The above example will output something similar to:

    int(119)
    int(123)
    int(180)

**Example \#2 Human-readable RGB values using <span
class="function">imagecolorsforindex</span>**

``` php
<?php
$im = imagecreatefrompng("php.png");
$rgb = imagecolorat($im, 10, 15);

$colors = imagecolorsforindex($im, $rgb);

var_dump($colors);
?>
```

The above example will output something similar to:

    array(4) {
      ["red"]=>
      int(119)
      ["green"]=>
      int(123)
      ["blue"]=>
      int(180)
      ["alpha"]=>
      int(127)
    }

### See Also

-   <span class="function">imagecolorset</span>
-   <span class="function">imagecolorsforindex</span>
-   <span class="function">imagesetpixel</span>

imagecolorclosest
=================

Get the index of the closest color to the specified color

### Description

<span class="type">int</span> <span
class="methodname">imagecolorclosest</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
)

Returns the index of the color in the palette of the image which is
"closest" to the specified RGB value.

The "distance" between the desired color and each color in the palette
is calculated as if the RGB values represented points in
three-dimensional space.

If you created the image from a file, only colors used in the image are
resolved. Colors present only in the palette are not resolved.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

The colors parameters are integers between 0 and 255 or hexadecimals
between 0x00 and 0xFF.

### Return Values

Returns the index of the closest color, in the palette of the image, to
the specified one

### Examples

**Example \#1 Search for a set of colors in an image**

``` php
<?php
// Start with an image and convert it to a palette-based image
$im = imagecreatefrompng('figures/imagecolorclosest.png');
imagetruecolortopalette($im, false, 255);

// Search colors (RGB)
$colors = array(
    array(254, 145, 154),
    array(153, 145, 188),
    array(153, 90, 145),
    array(255, 137, 92)
);

// Loop through each search and find the closest color in the palette.
// Return the search number, the search RGB and the converted RGB match
foreach($colors as $id => $rgb)
{
    $result = imagecolorclosest($im, $rgb[0], $rgb[1], $rgb[2]);
    $result = imagecolorsforindex($im, $result);
    $result = "({$result['red']}, {$result['green']}, {$result['blue']})";

    echo "#$id: Search ($rgb[0], $rgb[1], $rgb[2]); Closest match: $result.\n";
}

imagedestroy($im);
?>
```

The above example will output something similar to:

    #0: Search (254, 145, 154); Closest match: (252, 150, 148).
    #1: Search (153, 145, 188); Closest match: (148, 150, 196).
    #2: Search (153, 90, 145); Closest match: (148, 90, 156).
    #3: Search (255, 137, 92); Closest match: (252, 150, 92).

### See Also

-   <span class="function">imagecolorexact</span>
-   <span class="function">imagecolorclosestalpha</span>
-   <span class="function">imagecolorclosesthwb</span>

imagecolorclosestalpha
======================

Get the index of the closest color to the specified color + alpha

### Description

<span class="type">int</span> <span
class="methodname">imagecolorclosestalpha</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
, <span class="methodparam"><span class="type">int</span>
`$alpha`</span> )

Returns the index of the color in the palette of the image which is
"closest" to the specified RGB value and `alpha` level.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

`alpha`  
A value between *0* and *127*. *0* indicates completely opaque while
*127* indicates completely transparent.

The colors parameters are integers between 0 and 255 or hexadecimals
between 0x00 and 0xFF.

### Return Values

Returns the index of the closest color in the palette.

### Examples

**Example \#1 Search for a set of colors in an image**

``` php
<?php
// Start with an image and convert it to a palette-based image
$im = imagecreatefrompng('figures/imagecolorclosest.png');
imagetruecolortopalette($im, false, 255);

// Search colors (RGB)
$colors = array(
    array(254, 145, 154, 50),
    array(153, 145, 188, 127),
    array(153, 90, 145, 0),
    array(255, 137, 92, 84)
);

// Loop through each search and find the closest color in the palette.
// Return the search number, the search RGB and the converted RGB match
foreach($colors as $id => $rgb)
{
    $result = imagecolorclosestalpha($im, $rgb[0], $rgb[1], $rgb[2], $rgb[3]);
    $result = imagecolorsforindex($im, $result);
    $result = "({$result['red']}, {$result['green']}, {$result['blue']}, {$result['alpha']})";

    echo "#$id: Search ($rgb[0], $rgb[1], $rgb[2], $rgb[3]); Closest match: $result.\n";
}

imagedestroy($im);
?>
```

The above example will output something similar to:

    #0: Search (254, 145, 154, 50); Closest match: (252, 150, 148, 0).
    #1: Search (153, 145, 188, 127); Closest match: (148, 150, 196, 0).
    #2: Search (153, 90, 145, 0); Closest match: (148, 90, 156, 0).
    #3: Search (255, 137, 92, 84); Closest match: (252, 150, 92, 0).

### See Also

-   <span class="function">imagecolorexactalpha</span>
-   <span class="function">imagecolorclosest</span>
-   <span class="function">imagecolorclosesthwb</span>

imagecolorclosesthwb
====================

Get the index of the color which has the hue, white and blackness

### Description

<span class="type">int</span> <span
class="methodname">imagecolorclosesthwb</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
)

Get the index of the color which has the hue, white and blackness
nearest the given color.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

### Return Values

Returns an integer with the index of the color which has the hue, white
and blackness nearest the given color.

### Examples

**Example \#1 Example of using <span
class="function">imagecolorclosesthwb</span>**

``` php
<?php
$im = imagecreatefromgif('php.gif');

echo 'HWB: ' . imagecolorclosesthwb($im, 116, 115, 152);

imagedestroy($im);
?>
```

The above example will output something similar to:

    HWB: 33

### See Also

-   <span class="function">imagecolorclosest</span>

imagecolordeallocate
====================

De-allocate a color for an image

### Description

<span class="type">bool</span> <span
class="methodname">imagecolordeallocate</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

De-allocates a color previously allocated with <span
class="function">imagecolorallocate</span> or <span
class="function">imagecolorallocatealpha</span>.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`color`  
The color identifier.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Using <span class="function">imagecolordeallocate</span>**

``` php
<?php
$white = imagecolorallocate($im, 255, 255, 255);
imagecolordeallocate($im, $white);
?>
```

### See Also

-   <span class="function">imagecolorallocate</span>
-   <span class="function">imagecolorallocatealpha</span>

imagecolorexact
===============

Get the index of the specified color

### Description

<span class="type">int</span> <span
class="methodname">imagecolorexact</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
)

Returns the index of the specified color in the palette of the image.

If you created the image from a file, only colors used in the image are
resolved. Colors present only in the palette are not resolved.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

### Return Values

Returns the index of the specified color in the palette, or -1 if the
color does not exist.

### Examples

**Example \#1 Get colors from the GD logo**

``` php
<?php
// Setup an image
$im = imagecreatefrompng('./gdlogo.png');

$colors   = Array();
$colors[] = imagecolorexact($im, 255, 0, 0);
$colors[] = imagecolorexact($im, 0, 0, 0);
$colors[] = imagecolorexact($im, 255, 255, 255);
$colors[] = imagecolorexact($im, 100, 255, 52);

print_r($colors);

// Free from memory
imagedestroy($im);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 16711680
        [1] => 0
        [2] => 16777215
        [3] => 6618932
    )

### See Also

-   <span class="function">imagecolorclosest</span>

imagecolorexactalpha
====================

Get the index of the specified color + alpha

### Description

<span class="type">int</span> <span
class="methodname">imagecolorexactalpha</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
, <span class="methodparam"><span class="type">int</span>
`$alpha`</span> )

Returns the index of the specified color+alpha in the palette of the
image.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

`alpha`  
A value between *0* and *127*. *0* indicates completely opaque while
*127* indicates completely transparent.

The colors parameters are integers between 0 and 255 or hexadecimals
between 0x00 and 0xFF.

### Return Values

Returns the index of the specified color+alpha in the palette of the
image, or -1 if the color does not exist in the image's palette.

### Examples

**Example \#1 Get colors from the GD logo**

``` php
<?php

// Setup an image
$im = imagecreatefrompng('./gdlogo.png');

$colors   = Array();
$colors[] = imagecolorexactalpha($im, 255, 0, 0, 0);
$colors[] = imagecolorexactalpha($im, 0, 0, 0, 127);
$colors[] = imagecolorexactalpha($im, 255, 255, 255, 55);
$colors[] = imagecolorexactalpha($im, 100, 255, 52, 20);

print_r($colors);

// Free from memory
imagedestroy($im);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 16711680
        [1] => 2130706432
        [2] => 939524095
        [3] => 342163252
    )

### See Also

-   <span class="function">imagecolorclosestalpha</span>

imagecolormatch
===============

Makes the colors of the palette version of an image more closely match
the true color version

### Description

<span class="type">bool</span> <span
class="methodname">imagecolormatch</span> ( <span
class="methodparam"><span class="type">resource</span> `$image1`</span>
, <span class="methodparam"><span class="type">resource</span>
`$image2`</span> )

Makes the colors of the palette version of an image more closely match
the true color version.

### Parameters

`image1`  
A truecolor image resource.

`image2`  
A palette image resource pointing to an image that has the same size as
`image1`.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagecolormatch</span> example**

``` php
<?php
// Setup the true color and palette images
$im1 = imagecreatefrompng('./gdlogo.png');
$im2 = imagecreate(imagesx($im1), imagesy($im1));

// Add some colors to $im2
$colors   = Array();
$colors[] = imagecolorallocate($im2, 255, 36, 74);
$colors[] = imagecolorallocate($im2, 40, 0, 240);
$colors[] = imagecolorallocate($im2, 82, 100, 255);
$colors[] = imagecolorallocate($im2, 84, 63, 44);

// Match these colors with the true color image
imagecolormatch($im1, $im2);

// Free from memory
imagedestroy($im1);
imagedestroy($im2);
?>
```

### See Also

-   <span class="function">imagecreatetruecolor</span>

imagecolorresolve
=================

Get the index of the specified color or its closest possible alternative

### Description

<span class="type">int</span> <span
class="methodname">imagecolorresolve</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
)

This function is guaranteed to return a color index for a requested
color, either the exact color or the closest possible alternative.

If you created the image from a file, only colors used in the image are
resolved. Colors present only in the palette are not resolved.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

### Return Values

Returns a color index.

### Examples

**Example \#1 Using <span class="function">imagecoloresolve</span> to
get colors from an image**

``` php
<?php
// Load an image
$im = imagecreatefromgif('phplogo.gif');

// Get closest colors from the image
$colors = array();
$colors[] = imagecolorresolve($im, 255, 255, 255);
$colors[] = imagecolorresolve($im, 0, 0, 200);

// Output
print_r($colors);

imagedestroy($im);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 89
        [1] => 85
    )

### See Also

-   <span class="function">imagecolorclosest</span>

imagecolorresolvealpha
======================

Get the index of the specified color + alpha or its closest possible
alternative

### Description

<span class="type">int</span> <span
class="methodname">imagecolorresolvealpha</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$red`</span> ,
<span class="methodparam"><span class="type">int</span> `$green`</span>
, <span class="methodparam"><span class="type">int</span> `$blue`</span>
, <span class="methodparam"><span class="type">int</span>
`$alpha`</span> )

This function is guaranteed to return a color index for a requested
color, either the exact color or the closest possible alternative.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

`alpha`  
A value between *0* and *127*. *0* indicates completely opaque while
*127* indicates completely transparent.

The colors parameters are integers between 0 and 255 or hexadecimals
between 0x00 and 0xFF.

### Return Values

Returns a color index.

### Examples

**Example \#1 Using <span class="function">imagecoloresolvealpha</span>
to get colors from an image**

``` php
<?php
// Load an image
$im = imagecreatefromgif('phplogo.gif');

// Get closest colors from the image
$colors = array();
$colors[] = imagecolorresolvealpha($im, 255, 255, 255, 0);
$colors[] = imagecolorresolvealpha($im, 0, 0, 200, 127);

// Output
print_r($colors);

imagedestroy($im);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 89
        [1] => 85
    )

### See Also

-   <span class="function">imagecolorclosestalpha</span>

imagecolorset
=============

Set the color for the specified palette index

### Description

<span class="type">void</span> <span
class="methodname">imagecolorset</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">int</span> `$red`</span>
, <span class="methodparam"><span class="type">int</span>
`$green`</span> , <span class="methodparam"><span
class="type">int</span> `$blue`</span> \[, <span
class="methodparam"><span class="type">int</span> `$alpha`<span
class="initializer"> = 0</span></span> \] )

This sets the specified index in the palette to the specified color.
This is useful for creating flood-fill-like effects in palleted images
without the overhead of performing the actual flood-fill.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`index`  
An index in the palette.

`red`  
Value of red component.

`green`  
Value of green component.

`blue`  
Value of blue component.

`alpha`  
Value of alpha component.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">imagecolorset</span> example**

``` php
<?php
// Create a 300x100 image
$im = imagecreate(300, 100);

// Set the background to be red
imagecolorallocate($im, 255, 0, 0);

// Get the color index for the background
$bg = imagecolorat($im, 0, 0);

// Set the backgrund to be blue
imagecolorset($im, $bg, 0, 0, 255);

// Output the image to the browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagecolorat</span>

imagecolorsforindex
===================

Get the colors for an index

### Description

<span class="type">array</span> <span
class="methodname">imagecolorsforindex</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$index`</span>
)

Gets the color for a specified index.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`index`  
The color index.

### Return Values

Returns an associative array with red, green, blue and alpha keys that
contain the appropriate values for the specified color index.

### Examples

**Example \#1 <span class="function">imagecolorsforindex</span>
example**

``` php
<?php

// open an image
$im = imagecreatefrompng('nexen.png');

// get a color
$start_x = 40;
$start_y = 50;
$color_index = imagecolorat($im, $start_x, $start_y);

// make it human readable
$color_tran = imagecolorsforindex($im, $color_index);

// what is it ?
print_r($color_tran);

?>
```

The above example will output something similar to:

    Array
    (
       [red] => 226
       [green] => 222
       [blue] => 252
       [alpha] => 0
    )

### See Also

-   <span class="function">imagecolorat</span>
-   <span class="function">imagecolorexact</span>

imagecolorstotal
================

Find out the number of colors in an image's palette

### Description

<span class="type">int</span> <span
class="methodname">imagecolorstotal</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> )

Returns the number of colors in an image palette.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Returns the number of colors in the specified image's palette or 0 for
truecolor images.

### Examples

**Example \#1 Getting total number of colors in an image using <span
class="function">imagecolorstotal</span>**

``` php
<?php
// Create image instance
$im = imagecreatefromgif('php.gif');

echo 'Total colors in image: ' . imagecolorstotal($im);

// Free image
imagedestroy($im);
?>
```

The above example will output something similar to:

    Total colors in image: 128

### See Also

-   <span class="function">imagecolorat</span>
-   <span class="function">imagecolorsforindex</span>
-   <span class="function">imageistruecolor</span>

imagecolortransparent
=====================

Define a color as transparent

### Description

<span class="type">int</span> <span
class="methodname">imagecolortransparent</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> )

<span class="type">int</span> <span
class="methodname">imagecolortransparent</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

Gets or sets the transparent color in the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

The identifier of the new (or current, if none is specified) transparent
color is returned. If `color` is not specified, and the image has no
transparent color, the returned identifier will be -1.

### Examples

**Example \#1 <span class="function">imagecolortransparent</span>
example**

``` php
<?php
// Create a 55x30 image
$im = imagecreatetruecolor(55, 30);
$red = imagecolorallocate($im, 255, 0, 0);
$black = imagecolorallocate($im, 0, 0, 0);

// Make the background transparent
imagecolortransparent($im, $black);

// Draw a red rectangle
imagefilledrectangle($im, 4, 4, 50, 25, $red);

// Save the image
imagepng($im, './imagecolortransparent.png');
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecolortransparent.png" width="55" height="30" alt="Output of example : imagecolortransparent()" />

### Notes

> **Note**:
>
> Transparency is copied only with <span
> class="function">imagecopymerge</span> and true color images, not with
> <span class="function">imagecopy</span> or pallete images.

> **Note**:
>
> The transparent color is a property of the image, transparency is not
> a property of the color. Once you have set a color to be the
> transparent color, any regions of the image in that color that were
> drawn previously will be transparent.

imageconvolution
================

Apply a 3x3 convolution matrix, using coefficient and offset

### Description

<span class="type">bool</span> <span
class="methodname">imageconvolution</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">array</span>
`$matrix`</span> , <span class="methodparam"><span
class="type">float</span> `$div`</span> , <span
class="methodparam"><span class="type">float</span> `$offset`</span> )

Applies a convolution matrix on the image, using the given coefficient
and offset.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`matrix`  
A 3x3 matrix: an array of three arrays of three floats.

`div`  
The divisor of the result of the convolution, used for normalization.

`offset`  
Color offset.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Embossing the PHP.net logo**

``` php
<?php
$image = imagecreatefromgif('http://www.php.net/images/php.gif');

$emboss = array(array(2, 0, 0), array(0, -1, 0), array(0, 0, -1));
imageconvolution($image, $emboss, 1, 127);

header('Content-Type: image/png');
imagepng($image, null, 9);
?>
```

The above example will output:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageconvolution_emboss.png" width="120" height="67" alt="Output of example : Embossing the PHP.net logo" />

**Example \#2 Gaussian blur**

``` php
<?php
$image = imagecreatetruecolor(180,40);

// Writes the text and apply a gaussian blur on the image
imagestring($image, 5, 10, 8, 'Gaussian Blur Text', 0x00ff00);
$gaussian = array(array(1.0, 2.0, 1.0), array(2.0, 4.0, 2.0), array(1.0, 2.0, 1.0));
imageconvolution($image, $gaussian, 16, 0);

// Rewrites the text for comparison
imagestring($image, 5, 10, 18, 'Gaussian Blur Text', 0x00ff00);

header('Content-Type: image/png');
imagepng($image, null, 9);
?>
```

The above example will output:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageconvolution_gaussian.png" width="180" height="40" alt="Output of example : Gaussian blur" />

### Notes

This function requires GD 2.1.0 or higher.

### See Also

-   <span class="function">imagefilter</span>

imagecopy
=========

Copy part of an image

### Description

<span class="type">bool</span> <span class="methodname">imagecopy</span>
( <span class="methodparam"><span class="type">resource</span>
`$dst_im`</span> , <span class="methodparam"><span
class="type">resource</span> `$src_im`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_x`</span> ,
<span class="methodparam"><span class="type">int</span> `$dst_y`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_x`</span> , <span class="methodparam"><span
class="type">int</span> `$src_y`</span> , <span
class="methodparam"><span class="type">int</span> `$src_w`</span> ,
<span class="methodparam"><span class="type">int</span> `$src_h`</span>
)

Copy a part of `src_im` onto `dst_im` starting at the x,y coordinates
`src_x`, `src_y ` with a width of `src_w` and a height of `src_h`. The
portion defined will be copied onto the x,y coordinates, `dst_x` and
`dst_y`.

### Parameters

`dst_im`  
Destination image resource.

`src_im`  
Source image resource.

`dst_x`  
x-coordinate of destination point.

`dst_y`  
y-coordinate of destination point.

`src_x`  
x-coordinate of source point.

`src_y`  
y-coordinate of source point.

`src_w`  
Source width.

`src_h`  
Source height.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Cropping the PHP.net logo**

``` php
<?php
// Create image instances
$src = imagecreatefromgif('php.gif');
$dest = imagecreatetruecolor(80, 40);

// Copy
imagecopy($dest, $src, 0, 0, 20, 13, 80, 40);

// Output and free from memory
header('Content-Type: image/gif');
imagegif($dest);

imagedestroy($dest);
imagedestroy($src);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecopy.gif" width="80" height="40" alt="Output of example : Cropping the PHP.net logo" />

### See Also

-   <span class="function">imagecrop</span>

imagecopymerge
==============

Copy and merge part of an image

### Description

<span class="type">bool</span> <span
class="methodname">imagecopymerge</span> ( <span
class="methodparam"><span class="type">resource</span> `$dst_im`</span>
, <span class="methodparam"><span class="type">resource</span>
`$src_im`</span> , <span class="methodparam"><span
class="type">int</span> `$dst_x`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_y`</span> ,
<span class="methodparam"><span class="type">int</span> `$src_x`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_y`</span> , <span class="methodparam"><span
class="type">int</span> `$src_w`</span> , <span
class="methodparam"><span class="type">int</span> `$src_h`</span> ,
<span class="methodparam"><span class="type">int</span> `$pct`</span> )

Copy a part of `src_im` onto `dst_im` starting at the x,y coordinates
`src_x`, `src_y ` with a width of `src_w` and a height of `src_h`. The
portion defined will be copied onto the x,y coordinates, `dst_x` and
`dst_y`.

### Parameters

`dst_im`  
Destination image resource.

`src_im`  
Source image resource.

`dst_x`  
x-coordinate of destination point.

`dst_y`  
y-coordinate of destination point.

`src_x`  
x-coordinate of source point.

`src_y`  
y-coordinate of source point.

`src_w`  
Source width.

`src_h`  
Source height.

`pct`  
The two images will be merged according to `pct` which can range from 0
to 100. When `pct` = 0, no action is taken, when 100 this function
behaves identically to <span class="function">imagecopy</span> for
pallete images, except for ignoring alpha components, while it
implements alpha transparency for true colour images.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Merging two copies of the PHP.net logo with 75%
transparency**

``` php
<?php
// Create image instances
$dest = imagecreatefromgif('php.gif');
$src = imagecreatefromgif('php.gif');

// Copy and merge
imagecopymerge($dest, $src, 10, 10, 0, 0, 100, 47, 75);

// Output and free from memory
header('Content-Type: image/gif');
imagegif($dest);

imagedestroy($dest);
imagedestroy($src);
?>
```

imagecopymergegray
==================

Copy and merge part of an image with gray scale

### Description

<span class="type">bool</span> <span
class="methodname">imagecopymergegray</span> ( <span
class="methodparam"><span class="type">resource</span> `$dst_im`</span>
, <span class="methodparam"><span class="type">resource</span>
`$src_im`</span> , <span class="methodparam"><span
class="type">int</span> `$dst_x`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_y`</span> ,
<span class="methodparam"><span class="type">int</span> `$src_x`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_y`</span> , <span class="methodparam"><span
class="type">int</span> `$src_w`</span> , <span
class="methodparam"><span class="type">int</span> `$src_h`</span> ,
<span class="methodparam"><span class="type">int</span> `$pct`</span> )

<span class="function">imagecopymergegray</span> copy a part of `src_im`
onto `dst_im` starting at the x,y coordinates `src_x`, `src_y ` with a
width of `src_w` and a height of `src_h`. The portion defined will be
copied onto the x,y coordinates, `dst_x` and `dst_y`.

This function is identical to <span
class="function">imagecopymerge</span> except that when merging it
preserves the hue of the source by converting the destination pixels to
gray scale before the copy operation.

### Parameters

`dst_im`  
Destination image resource.

`src_im`  
Source image resource.

`dst_x`  
x-coordinate of destination point.

`dst_y`  
y-coordinate of destination point.

`src_x`  
x-coordinate of source point.

`src_y`  
y-coordinate of source point.

`src_w`  
Source width.

`src_h`  
Source height.

`pct`  
The `src_im` will be changed to grayscale according to `pct` where 0 is
fully grayscale and 100 is unchanged. When `pct` = 100 this function
behaves identically to <span class="function">imagecopy</span> for
pallete images, except for ignoring alpha components, while it
implements alpha transparency for true colour images.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagecopymergegray</span> usage**

``` php
<?php
// Create image instances
$dest = imagecreatefromgif('php.gif');
$src = imagecreatefromgif('php.gif');

// Copy and merge - Gray = 20%
imagecopymergegray($dest, $src, 10, 10, 0, 0, 100, 47, 20);

// Output and free from memory
header('Content-Type: image/gif');
imagegif($dest);

imagedestroy($dest);
imagedestroy($src);
?>
```

imagecopyresampled
==================

Copy and resize part of an image with resampling

### Description

<span class="type">bool</span> <span
class="methodname">imagecopyresampled</span> ( <span
class="methodparam"><span class="type">resource</span>
`$dst_image`</span> , <span class="methodparam"><span
class="type">resource</span> `$src_image`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_x`</span> ,
<span class="methodparam"><span class="type">int</span> `$dst_y`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_x`</span> , <span class="methodparam"><span
class="type">int</span> `$src_y`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_w`</span> ,
<span class="methodparam"><span class="type">int</span> `$dst_h`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_w`</span> , <span class="methodparam"><span
class="type">int</span> `$src_h`</span> )

<span class="function">imagecopyresampled</span> copies a rectangular
portion of one image to another image, smoothly interpolating pixel
values so that, in particular, reducing the size of an image still
retains a great deal of clarity.

In other words, <span class="function">imagecopyresampled</span> will
take a rectangular area from `src_image` of width `src_w` and height
`src_h` at position (`src_x`,`src_y`) and place it in a rectangular area
of `dst_image` of width `dst_w` and height `dst_h` at position
(`dst_x`,`dst_y`).

If the source and destination coordinates and width and heights differ,
appropriate stretching or shrinking of the image fragment will be
performed. The coordinates refer to the upper left corner. This function
can be used to copy regions within the same image (if `dst_image` is the
same as `src_image`) but if the regions overlap the results will be
unpredictable.

### Parameters

`dst_image`  
Destination image resource.

`src_image`  
Source image resource.

`dst_x`  
x-coordinate of destination point.

`dst_y`  
y-coordinate of destination point.

`src_x`  
x-coordinate of source point.

`src_y`  
y-coordinate of source point.

`dst_w`  
Destination width.

`dst_h`  
Destination height.

`src_w`  
Source width.

`src_h`  
Source height.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Simple example**

This example will resample an image to half its original size.

``` php
<?php
// The file
$filename = 'test.jpg';
$percent = 0.5;

// Content type
header('Content-Type: image/jpeg');

// Get new dimensions
list($width, $height) = getimagesize($filename);
$new_width = $width * $percent;
$new_height = $height * $percent;

// Resample
$image_p = imagecreatetruecolor($new_width, $new_height);
$image = imagecreatefromjpeg($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $new_width, $new_height, $width, $height);

// Output
imagejpeg($image_p, null, 100);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecopyresampled.jpg" width="47" height="25" alt="Output of example : Simple example" />

**Example \#2 Resampling an image proportionally**

This example will display an image with the maximum width, or height, of
200 pixels.

``` php
<?php
// The file
$filename = 'test.jpg';

// Set a maximum height and width
$width = 200;
$height = 200;

// Content type
header('Content-Type: image/jpeg');

// Get new dimensions
list($width_orig, $height_orig) = getimagesize($filename);

$ratio_orig = $width_orig/$height_orig;

if ($width/$height > $ratio_orig) {
   $width = $height*$ratio_orig;
} else {
   $height = $width/$ratio_orig;
}

// Resample
$image_p = imagecreatetruecolor($width, $height);
$image = imagecreatefromjpeg($filename);
imagecopyresampled($image_p, $image, 0, 0, 0, 0, $width, $height, $width_orig, $height_orig);

// Output
imagejpeg($image_p, null, 100);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecopyresampled_2.jpg" width="200" height="107" alt="Output of example : Resampling an image proportionally" />

### Notes

> **Note**:
>
> There is a problem due to palette image limitations (255+1 colors).
> Resampling or filtering an image commonly needs more colors than 255,
> a kind of approximation is used to calculate the new resampled pixel
> and its color. With a palette image we try to allocate a new color, if
> that failed, we choose the closest (in theory) computed color. This is
> not always the closest visual color. That may produce a weird result,
> like blank (or visually blank) images. To skip this problem, please
> use a truecolor image as a destination image, such as one created by
> <span class="function">imagecreatetruecolor</span>.

### See Also

-   <span class="function">imagecopyresized</span>
-   <span class="function">imagescale</span>
-   <span class="function">imagecrop</span>

imagecopyresized
================

Copy and resize part of an image

### Description

<span class="type">bool</span> <span
class="methodname">imagecopyresized</span> ( <span
class="methodparam"><span class="type">resource</span>
`$dst_image`</span> , <span class="methodparam"><span
class="type">resource</span> `$src_image`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_x`</span> ,
<span class="methodparam"><span class="type">int</span> `$dst_y`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_x`</span> , <span class="methodparam"><span
class="type">int</span> `$src_y`</span> , <span
class="methodparam"><span class="type">int</span> `$dst_w`</span> ,
<span class="methodparam"><span class="type">int</span> `$dst_h`</span>
, <span class="methodparam"><span class="type">int</span>
`$src_w`</span> , <span class="methodparam"><span
class="type">int</span> `$src_h`</span> )

<span class="function">imagecopyresized</span> copies a rectangular
portion of one image to another image. `dst_image` is the destination
image, `src_image` is the source image identifier.

In other words, <span class="function">imagecopyresized</span> will take
a rectangular area from `src_image` of width `src_w` and height `src_h`
at position (`src_x`,`src_y`) and place it in a rectangular area of
`dst_image` of width `dst_w` and height `dst_h` at position
(`dst_x`,`dst_y`).

If the source and destination coordinates and width and heights differ,
appropriate stretching or shrinking of the image fragment will be
performed. The coordinates refer to the upper left corner. This function
can be used to copy regions within the same image (if `dst_image` is the
same as `src_image`) but if the regions overlap the results will be
unpredictable.

### Parameters

`dst_image`  
Destination image resource.

`src_image`  
Source image resource.

`dst_x`  
x-coordinate of destination point.

`dst_y`  
y-coordinate of destination point.

`src_x`  
x-coordinate of source point.

`src_y`  
y-coordinate of source point.

`dst_w`  
Destination width.

`dst_h`  
Destination height.

`src_w`  
Source width.

`src_h`  
Source height.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Resizing an image**

This example will display the image at half size.

``` php
<?php
// File and new size
$filename = 'test.jpg';
$percent = 0.5;

// Content type
header('Content-Type: image/jpeg');

// Get new sizes
list($width, $height) = getimagesize($filename);
$newwidth = $width * $percent;
$newheight = $height * $percent;

// Load
$thumb = imagecreatetruecolor($newwidth, $newheight);
$source = imagecreatefromjpeg($filename);

// Resize
imagecopyresized($thumb, $source, 0, 0, 0, 0, $newwidth, $newheight, $width, $height);

// Output
imagejpeg($thumb);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecopyresized.jpg" width="47" height="25" alt="Output of example : Resizing an image" />

The image will be output at half size, though better quality could be
obtained using <span class="function">imagecopyresampled</span>.

### Notes

> **Note**:
>
> There is a problem due to palette image limitations (255+1 colors).
> Resampling or filtering an image commonly needs more colors than 255,
> a kind of approximation is used to calculate the new resampled pixel
> and its color. With a palette image we try to allocate a new color, if
> that failed, we choose the closest (in theory) computed color. This is
> not always the closest visual color. That may produce a weird result,
> like blank (or visually blank) images. To skip this problem, please
> use a truecolor image as a destination image, such as one created by
> <span class="function">imagecreatetruecolor</span>.

### See Also

-   <span class="function">imagecopyresampled</span>
-   <span class="function">imagescale</span>
-   <span class="function">imagecrop</span>

imagecreate
===========

Create a new palette based image

### Description

<span class="type">resource</span> <span
class="methodname">imagecreate</span> ( <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> )

<span class="function">imagecreate</span> returns an image identifier
representing a blank image of specified size.

In general, we recommend the use of <span
class="function">imagecreatetruecolor</span> instead of <span
class="function">imagecreate</span> so that image processing occurs on
the highest quality image possible. If you want to output a palette
image, then <span class="function">imagetruecolortopalette</span> should
be called immediately before saving the image with <span
class="function">imagepng</span> or <span
class="function">imagegif</span>.

### Parameters

`width`  
The image width.

`height`  
The image height.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Creating a new GD image stream and outputting an image.**

``` php
<?php
header("Content-Type: image/png");
$im = @imagecreate(110, 20)
    or die("Cannot Initialize new GD image stream");
$background_color = imagecolorallocate($im, 0, 0, 0);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);
imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreate.png" width="110" height="25" alt="Output of example : Creating a new GD image stream and outputting an image." />

### See Also

-   <span class="function">imagedestroy</span>
-   <span class="function">imagecreatetruecolor</span>

imagecreatefrombmp
==================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefrombmp</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefrombmp</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the BMP image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Convert an BMP image to a PNG image using <span
class="function">imagecreatefrombmp</span>**

``` php
<?php
// Load the BMP file
$im = imagecreatefrombmp('./example.bmp');

// Convert it to a PNG file with default settings
imagepng($im, './example.png');
imagedestroy($im);
?>
```

imagecreatefromgd2
==================

Create a new image from GD2 file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromgd2</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Create a new image from GD2 file or URL.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the GD2 image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 <span class="function">imagecreatefromgd2</span> example**

``` php
<?php
// Load the gd2 image
$im = imagecreatefromgd2('./test.gd2');

// Apply an effect on the image, in this 
// case negate the image
if(function_exists('imagefilter'))
{
    imagefilter($im, IMG_FILTER_NEGATE);
}

// Save the image
imagegd2($im, './test_updated.gd2');
imagedestroy($im);
?>
```

### Notes

**Warning**

The GD and GD2 image formats are proprietary image formats of libgd.
They have to be regarded *obsolete*, and should only be used for
development and testing purposes.

imagecreatefromgd2part
======================

Create a new image from a given part of GD2 file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromgd2part</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">int</span> `$srcX`</span>
, <span class="methodparam"><span class="type">int</span> `$srcY`</span>
, <span class="methodparam"><span class="type">int</span>
`$width`</span> , <span class="methodparam"><span
class="type">int</span> `$height`</span> )

Create a new image from a given part of GD2 file or URL.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the GD2 image.

`srcX`  
x-coordinate of source point.

`srcY`  
y-coordinate of source point.

`width`  
Source width.

`height`  
Source height.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 <span class="function">imagecreatefromgd2part</span>
example**

``` php
<?php
// For this example we need the image size before
$image = getimagesize('./test.gd2');

// Create the image instance now we got the image 
// sizes
$im = imagecreatefromgd2part('./test.gd2', 4, 4, ($image[0] / 2) - 6, ($image[1] / 2) - 6);

// Do an image operation, in this case we emboss the image
if(function_exists('imagefilter'))
{
    imagefilter($im, IMG_FILTER_EMBOSS);
}

// Save optimized image
imagegd2($im, './test_emboss.gd2');
imagedestroy($im);
?>
```

### Notes

**Warning**

The GD and GD2 image formats are proprietary image formats of libgd.
They have to be regarded *obsolete*, and should only be used for
development and testing purposes.

imagecreatefromgd
=================

Create a new image from GD file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromgd</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Create a new image from GD file or URL.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the GD file.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 <span class="function">imagecreatefromgd</span> example**

``` php
<?php
// Load the gd image
$im = @imagecreatefromgd('./test.gd');

// Test if the image was loaded
if(!is_resource($im))
{
     die('Unable to load gd image!');
}

// Do image operations here

// Save the image
imagegd($im, './test_updated.gd');
imagedestroy($im);
?>
```

### Notes

**Warning**

The GD and GD2 image formats are proprietary image formats of libgd.
They have to be regarded *obsolete*, and should only be used for
development and testing purposes.

imagecreatefromgif
==================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromgif</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromgif</span> returns an image
identifier representing the image obtained from the given filename.

**Caution**

When reading GIF files into memory, only the first frame is returned in
the image resource pointer. The size of the image is not necessarily
what is reported by <span class="function">getimagesize</span>.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the GIF image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Example to handle an error during loading of a GIF**

``` php
<?php
function LoadGif($imgname)
{
    /* Attempt to open */
    $im = @imagecreatefromgif($imgname);

    /* See if it failed */
    if(!$im)
    {
        /* Create a blank image */
        $im = imagecreatetruecolor (150, 30);
        $bgc = imagecolorallocate ($im, 255, 255, 255);
        $tc = imagecolorallocate ($im, 0, 0, 0);

        imagefilledrectangle ($im, 0, 0, 150, 30, $bgc);

        /* Output an error message */
        imagestring ($im, 1, 5, 5, 'Error loading ' . $imgname, $tc);
    }

    return $im;
}

header('Content-Type: image/gif');

$img = LoadGif('bogus.image');

imagegif($img);
imagedestroy($img);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreatefromgif.gif" width="150" height="30" alt="Output of example : Example to handle an error during loading of a GIF" />

### Notes

> **Note**:
>
> GIF support was removed from the GD library in Version 1.6, and added
> back in Version 2.0.28. This function is not available between these
> versions.

imagecreatefromjpeg
===================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromjpeg</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromjpeg</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the JPEG image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Example to handle an error during loading of a JPEG**

``` php
<?php
function LoadJpeg($imgname)
{
    /* Attempt to open */
    $im = @imagecreatefromjpeg($imgname);

    /* See if it failed */
    if(!$im)
    {
        /* Create a black image */
        $im  = imagecreatetruecolor(150, 30);
        $bgc = imagecolorallocate($im, 255, 255, 255);
        $tc  = imagecolorallocate($im, 0, 0, 0);

        imagefilledrectangle($im, 0, 0, 150, 30, $bgc);

        /* Output an error message */
        imagestring($im, 1, 5, 5, 'Error loading ' . $imgname, $tc);
    }

    return $im;
}

header('Content-Type: image/jpeg');

$img = LoadJpeg('bogus.image');

imagejpeg($img);
imagedestroy($img);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreatefromjpeg.jpg" width="150" height="30" alt="Output of example : Example to handle an error during loading of a JPEG" />

imagecreatefrompng
==================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefrompng</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefrompng</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the PNG image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Example to handle an error during loading of a PNG**

``` php
<?php
function LoadPNG($imgname)
{
    /* Attempt to open */
    $im = @imagecreatefrompng($imgname);

    /* See if it failed */
    if(!$im)
    {
        /* Create a blank image */
        $im  = imagecreatetruecolor(150, 30);
        $bgc = imagecolorallocate($im, 255, 255, 255);
        $tc  = imagecolorallocate($im, 0, 0, 0);

        imagefilledrectangle($im, 0, 0, 150, 30, $bgc);

        /* Output an error message */
        imagestring($im, 1, 5, 5, 'Error loading ' . $imgname, $tc);
    }

    return $im;
}

header('Content-Type: image/png');

$img = LoadPNG('bogus.image');

imagepng($img);
imagedestroy($img);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreatefrompng.png" width="150" height="30" alt="imagecreatefrompng() example" />

imagecreatefromstring
=====================

Create a new image from the image stream in the string

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromstring</span> ( <span
class="methodparam"><span class="type">string</span> `$image`</span> )

<span class="function">imagecreatefromstring</span> returns an image
identifier representing the image obtained from the given `image`. These
types will be automatically detected if your build of PHP supports them:
JPEG, PNG, GIF, BMP, WBMP, GD2, and WEBP.

### Parameters

`image`  
A string containing the image data.

### Return Values

An image resource will be returned on success. **`false`** is returned
if the image type is unsupported, the data is not in a recognised
format, or the image is corrupt and cannot be loaded.

### Changelog

| Version | Description                                               |
|---------|-----------------------------------------------------------|
| 7.3.0   | WEBP is supported now (if supported by the libgd in use). |

### Errors/Exceptions

<span class="function">imagecreatefromstring</span> raises an E\_WARNING
level error, if the data is not in a recognized format.

### Examples

**Example \#1 <span class="function">imagecreatefromstring</span>
example**

``` php
<?php
$data = 'iVBORw0KGgoAAAANSUhEUgAAABwAAAASCAMAAAB/2U7WAAAABl'
       . 'BMVEUAAAD///+l2Z/dAAAASUlEQVR4XqWQUQoAIAxC2/0vXZDr'
       . 'EX4IJTRkb7lobNUStXsB0jIXIAMSsQnWlsV+wULF4Avk9fLq2r'
       . '8a5HSE35Q3eO2XP1A1wQkZSgETvDtKdQAAAABJRU5ErkJggg==';
$data = base64_decode($data);

$im = imagecreatefromstring($data);
if ($im !== false) {
    header('Content-Type: image/png');
    imagepng($im);
    imagedestroy($im);
}
else {
    echo 'An error occurred.';
}
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreatefromstring.png" width="28" height="18" alt="Output of example : imagecreatefromstring()" />

### See Also

-   <span class="function">imagecreatefromjpeg</span>
-   <span class="function">imagecreatefrompng</span>
-   <span class="function">imagecreatefromgif</span>
-   <span class="function">imagecreatetruecolor</span>

imagecreatefromwbmp
===================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromwbmp</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromwbmp</span> returns an image
identifier representing the image obtained from the given filename.

> **Note**: <span class="simpara"> WBMP images are Wireless Bitmaps, not
> Windows Bitmaps. The latter can be loaded with <span
> class="function">imagecreatefrombmp</span>. </span>

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the WBMP image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Example to handle an error during loading of a WBMP**

``` php
<?php
function LoadWBMP($imgname)
{
    /* Attempt to open */
    $im = @imagecreatefromwbmp($imgname);

    /* See if it failed */
    if(!$im)
    {
        /* Create a blank image */
        $im  = imagecreatetruecolor(150, 30);
        $bgc = imagecolorallocate($im, 255, 255, 255);
        $tc  = imagecolorallocate($im, 0, 0, 0);

        imagefilledrectangle($im, 0, 0, 150, 30, $bgc);

        /* Output an error message */
        imagestring($im, 1, 5, 5, 'Error loading ' . $imgname, $tc);
    }

    return $im;
}

header('Content-Type: image/vnd.wap.wbmp');

$img = LoadWBMP('bogus.image');

imagewbmp($img);
imagedestroy($img);
?>
```

imagecreatefromwebp
===================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromwebp</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromwebp</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the WebP image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Convert an WebP image to a jpeg image using <span
class="function">imagecreatefromwebp</span>**

``` php
<?php
// Load the WebP file
$im = imagecreatefromwebp('./example.webp');

// Convert it to a jpeg file with 100% quality
imagejpeg($im, './example.jpeg', 100);
imagedestroy($im);
?>
```

imagecreatefromxbm
==================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromxbm</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromxbm</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the XBM image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Convert an XBM image to a png image using <span
class="function">imagecreatefromxbm</span>**

``` php
<?php
// Load the xbm file
$xbm = imagecreatefromxbm('./example.xbm');

// Convert it to a png file
imagepng($xbm, './example.png');
imagedestroy($xbm);
?>
```

imagecreatefromxpm
==================

Create a new image from file or URL

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatefromxpm</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="function">imagecreatefromxpm</span> returns an image
identifier representing the image obtained from the given filename.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### Parameters

`filename`  
Path to the XPM image.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Creating an image instance using <span
class="function">imagecreatefromxpm</span>**

``` php
<?php
// Check for XPM support
if(!(imagetypes() & IMG_XPM))
{
    die('Support for xpm was not found!');
}

// Create the image instance
$xpm = imagecreatefromxpm('./example.xpm');

// Do image operations here

// PHP has no support for writing xpm images
// so in this case we save the image as a 
// jpeg file with 100% quality
imagejpeg($xpm, './example.jpg', 100);
imagedestroy($xpm);
?>
```

imagecreatetruecolor
====================

Create a new true color image

### Description

<span class="type">resource</span> <span
class="methodname">imagecreatetruecolor</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
)

<span class="function">imagecreatetruecolor</span> returns an image
identifier representing a black image of the specified size.

### Parameters

`width`  
Image width.

`height`  
Image height.

### Return Values

Returns an image resource identifier on success, **`false`** on errors.

### Examples

**Example \#1 Creating a new GD image stream and outputting an image.**

``` php
<?php
header ('Content-Type: image/png');
$im = @imagecreatetruecolor(120, 20)
      or die('Cannot Initialize new GD image stream');
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);
imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagecreatetruecolor.png" width="120" height="20" alt="Output of example : Creating a new GD image stream and outputting an image." />

### See Also

-   <span class="function">imagedestroy</span>
-   <span class="function">imagecreate</span>

imagecrop
=========

Crop an image to the given rectangle

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">imagecrop</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">array</span> `$rect`</span> )

Crops an image to the given rectangular area and returns the resulting
image. The given `image` is not modified.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`rect`  
The cropping rectangle as <span class="type">array</span> with keys *x*,
*y*, *width* and *height*.

### Return Values

Return cropped image resource on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagecrop</span> example**

This example shows how to crop an image to a square area.

``` php
<?php
$im = imagecreatefrompng('example.png');
$size = min(imagesx($im), imagesy($im));
$im2 = imagecrop($im, ['x' => 0, 'y' => 0, 'width' => $size, 'height' => $size]);
if ($im2 !== FALSE) {
    imagepng($im2, 'example-cropped.png');
    imagedestroy($im2);
}
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagecropauto</span>

imagecropauto
=============

Crop an image automatically using one of the available modes

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">imagecropauto</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span>
\[, <span class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`IMG_CROP_DEFAULT`**</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$threshold`<span
class="initializer"> = .5</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$color`<span
class="initializer"> = -1</span></span> \]\]\] )

Automatically crops an image according to the given `mode`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`mode`  
One of the following constants:

**`IMG_CROP_DEFAULT`**  
<span class="simpara"> Same as **`IMG_CROP_TRANSPARENT`**. Before PHP
7.4.0, the bundled libgd fell back to **`IMG_CROP_SIDES`**, if the image
had no transparent color. </span>

**`IMG_CROP_TRANSPARENT`**  
<span class="simpara"> Crops out a transparent background. </span>

**`IMG_CROP_BLACK`**  
<span class="simpara"> Crops out a black background. </span>

**`IMG_CROP_WHITE`**  
<span class="simpara"> Crops out a white background. </span>

**`IMG_CROP_SIDES`**  
<span class="simpara"> Uses the 4 corners of the image to attempt to
detect the background to crop. </span>

**`IMG_CROP_THRESHOLD`**  
<span class="simpara"> Crops an image using the given `threshold` and
`color`. </span>

`threshold`  
Specifies the tolerance in percent to be used while comparing the image
color and the color to crop. The method used to calculate the color
difference is based on the color distance in the RGB(a) cube.

Used only in **`IMG_CROP_THRESHOLD`** mode.

> **Note**: <span class="simpara"> Before PHP 7.4.0, the bundled libgd
> used a somewhat different algorithm, so the same `threshold` yielded
> different results for system and bundled libgd. </span>

`color`  
Either an RGB color value or a palette index.

Used only in **`IMG_CROP_THRESHOLD`** mode.

### Return Values

Returns a cropped image resource on success or **`false`** on failure.
If the complete image was cropped, <span
class="function">imagecrop</span> returns **`false`**.

### Changelog

| Version | Description                                                                                                                                                                                                                             |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The behavior of imagecropauto() in the bundled libgd has been synced with that of system libgd: **`IMG_CROP_DEFAULT`** no longer falls back to **`IMG_CROP_SIDES`** and threshold-cropping now uses the same algorithm as system libgd. |
| 7.4.0   | The default value of `mode` has been changed to **`IMG_CROP_AUTO`**. Formerly, the default value has been *-1* which corresponds to **`IMG_CROP_DEFAULT`**, but passing *-1* is now deprecated.                                         |

### Examples

**Example \#1 Proper handling of auto-cropping**

As noted in the return value section, <span
class="function">imagecropauto</span> returns **`false`** if the whole
image was cropped. In this example we have an image resource *$im* which
should be automatically cropped only if there is something to crop;
otherwise we want to proceed with the original image.

``` php
<?php
$cropped = imagecropauto($im, IMG_CROP_DEFAULT);
if ($cropped !== false) { // in case a new image resource was returned
    imagedestroy($im);    // we destroy the original image
    $im = $cropped;       // and assign the cropped image to $im
}
?>
```

### See Also

-   <span class="function">imagecrop</span>

imagedashedline
===============

Draw a dashed line

### Description

<span class="type">bool</span> <span
class="methodname">imagedashedline</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$x1`</span> ,
<span class="methodparam"><span class="type">int</span> `$y1`</span> ,
<span class="methodparam"><span class="type">int</span> `$x2`</span> ,
<span class="methodparam"><span class="type">int</span> `$y2`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

This function is deprecated. Use combination of <span
class="function">imagesetstyle</span> and <span
class="function">imageline</span> instead.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x1`  
Upper left x coordinate.

`y1`  
Upper left y coordinate 0, 0 is the top left corner of the image.

`x2`  
Bottom right x coordinate.

`y2`  
Bottom right y coordinate.

`color`  
The fill color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagedashedline</span> example**

``` php
<?php
// Create a 100x100 image
$im = imagecreatetruecolor(100, 100);
$white = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);

// Draw a vertical dashed line
imagedashedline($im, 50, 25, 50, 75, $white);

// Save the image
imagepng($im, './dashedline.png');
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagedashedline.png" width="100" height="100" alt="Output of example : imagedashedline()" />

**Example \#2 Alternative to <span
class="function">imagedashedline</span>**

``` php
<?php
// Create a 100x100 image
$im = imagecreatetruecolor(100, 100);
$white = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);

// Define our style: First 4 pixels is white and the 
// next 4 is transparent. This creates the dashed line effect
$style = Array(
                $white, 
                $white, 
                $white, 
                $white, 
                IMG_COLOR_TRANSPARENT, 
                IMG_COLOR_TRANSPARENT, 
                IMG_COLOR_TRANSPARENT, 
                IMG_COLOR_TRANSPARENT
                );

imagesetstyle($im, $style);

// Draw the dashed line
imageline($im, 50, 25, 50, 75, IMG_COLOR_STYLED);

// Save the image
imagepng($im, './imageline.png');
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagesetstyle</span>
-   <span class="function">imageline</span>

imagedestroy
============

Destroy an image

### Description

<span class="type">bool</span> <span
class="methodname">imagedestroy</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> )

<span class="function">imagedestroy</span> frees any memory associated
with image `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Using <span class="function">imagedestroy</span> example**

``` php
<?php
// create a 100 x 100 image
$im = imagecreatetruecolor(100, 100);

// alter or save the image

// frees image from memory
imagedestroy($im);
?>
```

imageellipse
============

Draw an ellipse

### Description

<span class="type">bool</span> <span
class="methodname">imageellipse</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$cx`</span> , <span
class="methodparam"><span class="type">int</span> `$cy`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span>
`$color`</span> )

Draws an ellipse centered at the specified coordinates.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`cx`  
x-coordinate of the center.

`cy`  
y-coordinate of the center.

`width`  
The ellipse width.

`height`  
The ellipse height.

`color`  
The color of the ellipse. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imageellipse</span> example**

``` php
<?php

// Create a blank image.
$image = imagecreatetruecolor(400, 300);

// Select the background color.
$bg = imagecolorallocate($image, 0, 0, 0);

// Fill the background with the color selected above.
imagefill($image, 0, 0, $bg);

// Choose a color for the ellipse.
$col_ellipse = imagecolorallocate($image, 255, 255, 255);

// Draw the ellipse.
imageellipse($image, 200, 150, 300, 200, $col_ellipse);

// Output the image.
header("Content-type: image/png");
imagepng($image);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageellipse.png" width="400" height="300" alt="Output of example : imageellipse()" />

### Notes

> **Note**:
>
> <span class="function">imageellipse</span> ignores <span
> class="function">imagesetthickness</span>.

### See Also

-   <span class="function">imagefilledellipse</span>
-   <span class="function">imagearc</span>

imagefill
=========

Flood fill

### Description

<span class="type">bool</span> <span class="methodname">imagefill</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

Performs a flood fill starting at the given coordinate (top left is 0,
0) with the given `color` in the `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x`  
x-coordinate of start point.

`y`  
y-coordinate of start point.

`color`  
The fill color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagefill</span> example**

``` php
<?php

$im = imagecreatetruecolor(100, 100);

// sets background to red
$red = imagecolorallocate($im, 255, 0, 0);
imagefill($im, 0, 0, $red);

header('Content-type: image/png');
imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefill.png" width="100" height="100" alt="Output of example : imagefill()" />

### See Also

-   <span class="function">imagecolorallocate</span>

imagefilledarc
==============

Draw a partial arc and fill it

### Description

<span class="type">bool</span> <span
class="methodname">imagefilledarc</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$cx`</span> ,
<span class="methodparam"><span class="type">int</span> `$cy`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
, <span class="methodparam"><span class="type">int</span>
`$height`</span> , <span class="methodparam"><span
class="type">int</span> `$start`</span> , <span
class="methodparam"><span class="type">int</span> `$end`</span> , <span
class="methodparam"><span class="type">int</span> `$color`</span> ,
<span class="methodparam"><span class="type">int</span> `$style`</span>
)

Draws a partial arc centered at the specified coordinate in the given
`image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`cx`  
x-coordinate of the center.

`cy`  
y-coordinate of the center.

`width`  
The arc width.

`height`  
The arc height.

`start`  
The arc start angle, in degrees.

`end`  
The arc end angle, in degrees. 0° is located at the three-o'clock
position, and the arc is drawn clockwise.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

`style`  
A bitwise OR of the following possibilities:

1.  <span class="simpara">**`IMG_ARC_PIE`**</span>
2.  <span class="simpara">**`IMG_ARC_CHORD`**</span>
3.  <span class="simpara">**`IMG_ARC_NOFILL`**</span>
4.  <span class="simpara">**`IMG_ARC_EDGED`**</span>

**`IMG_ARC_PIE`** and **`IMG_ARC_CHORD`** are mutually exclusive;
**`IMG_ARC_CHORD`** just connects the starting and ending angles with a
straight line, while **`IMG_ARC_PIE`** produces a rounded edge.
**`IMG_ARC_NOFILL`** indicates that the arc or chord should be outlined,
not filled. **`IMG_ARC_EDGED`**, used together with
**`IMG_ARC_NOFILL`**, indicates that the beginning and ending angles
should be connected to the center - this is a good way to outline
(rather than fill) a 'pie slice'.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Creating a 3D looking pie**

``` php
<?php

// create image
$image = imagecreatetruecolor(100, 100);

// allocate some colors
$white    = imagecolorallocate($image, 0xFF, 0xFF, 0xFF);
$gray     = imagecolorallocate($image, 0xC0, 0xC0, 0xC0);
$darkgray = imagecolorallocate($image, 0x90, 0x90, 0x90);
$navy     = imagecolorallocate($image, 0x00, 0x00, 0x80);
$darknavy = imagecolorallocate($image, 0x00, 0x00, 0x50);
$red      = imagecolorallocate($image, 0xFF, 0x00, 0x00);
$darkred  = imagecolorallocate($image, 0x90, 0x00, 0x00);

// make the 3D effect
for ($i = 60; $i > 50; $i--) {
   imagefilledarc($image, 50, $i, 100, 50, 0, 45, $darknavy, IMG_ARC_PIE);
   imagefilledarc($image, 50, $i, 100, 50, 45, 75 , $darkgray, IMG_ARC_PIE);
   imagefilledarc($image, 50, $i, 100, 50, 75, 360 , $darkred, IMG_ARC_PIE);
}

imagefilledarc($image, 50, 50, 100, 50, 0, 45, $navy, IMG_ARC_PIE);
imagefilledarc($image, 50, 50, 100, 50, 45, 75 , $gray, IMG_ARC_PIE);
imagefilledarc($image, 50, 50, 100, 50, 75, 360 , $red, IMG_ARC_PIE);


// flush image
header('Content-type: image/png');
imagepng($image);
imagedestroy($image);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilledarc.png" width="100" height="100" alt="Output of example : Creating a 3D looking pie" />

imagefilledellipse
==================

Draw a filled ellipse

### Description

<span class="type">bool</span> <span
class="methodname">imagefilledellipse</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$cx`</span> ,
<span class="methodparam"><span class="type">int</span> `$cy`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
, <span class="methodparam"><span class="type">int</span>
`$height`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

Draws an ellipse centered at the specified coordinate on the given
`image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`cx`  
x-coordinate of the center.

`cy`  
y-coordinate of the center.

`width`  
The ellipse width.

`height`  
The ellipse height.

`color`  
The fill color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagefilledellipse</span> example**

``` php
<?php

// create a blank image
$image = imagecreatetruecolor(400, 300);

// fill the background color
$bg = imagecolorallocate($image, 0, 0, 0);

// choose a color for the ellipse
$col_ellipse = imagecolorallocate($image, 255, 255, 255);

// draw the white ellipse
imagefilledellipse($image, 200, 150, 300, 200, $col_ellipse);

// output the picture
header("Content-type: image/png");
imagepng($image);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilledellipse.png" width="400" height="300" alt="Output of example : imagefilledellipse()" />

### Notes

> **Note**:
>
> <span class="function">imagefilledellipse</span> ignores <span
> class="function">imagesetthickness</span>.

### See Also

-   <span class="function">imageellipse</span>
-   <span class="function">imagefilledarc</span>

imagefilledpolygon
==================

Draw a filled polygon

### Description

<span class="type">bool</span> <span
class="methodname">imagefilledpolygon</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">array</span>
`$points`</span> , <span class="methodparam"><span
class="type">int</span> `$num_points`</span> , <span
class="methodparam"><span class="type">int</span> `$color`</span> )

<span class="function">imagefilledpolygon</span> creates a filled
polygon in the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`points`  
An array containing the *x* and *y* coordinates of the polygons vertices
consecutively.

`num_points`  
Total number of points (vertices), which must be at least 3.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagefilledpolygon</span> example**

``` php
<?php
// set up array of points for polygon
$values = array(
            40,  50,  // Point 1 (x, y)
            20,  240, // Point 2 (x, y)
            60,  60,  // Point 3 (x, y)
            240, 20,  // Point 4 (x, y)
            50,  40,  // Point 5 (x, y)
            10,  10   // Point 6 (x, y)
            );

// create image
$image = imagecreatetruecolor(250, 250);

// allocate colors
$bg   = imagecolorallocate($image, 0, 0, 0);
$blue = imagecolorallocate($image, 0, 0, 255);

// fill the background
imagefilledrectangle($image, 0, 0, 249, 249, $bg);

// draw a polygon
imagefilledpolygon($image, $values, 6, $blue);

// flush image
header('Content-type: image/png');
imagepng($image);
imagedestroy($image);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilledpolygon.png" width="250" height="250" alt="Output of example : imagefilledpolygon()" />

### See Also

-   <span class="function">imagepolygon</span>

imagefilledrectangle
====================

Draw a filled rectangle

### Description

<span class="type">bool</span> <span
class="methodname">imagefilledrectangle</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$x1`</span> ,
<span class="methodparam"><span class="type">int</span> `$y1`</span> ,
<span class="methodparam"><span class="type">int</span> `$x2`</span> ,
<span class="methodparam"><span class="type">int</span> `$y2`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

Creates a rectangle filled with `color` in the given `image` starting at
point 1 and ending at point 2. 0, 0 is the top left corner of the image.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x1`  
x-coordinate for point 1.

`y1`  
y-coordinate for point 1.

`x2`  
x-coordinate for point 2.

`y2`  
y-coordinate for point 2.

`color`  
The fill color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagefilledrectangle</span> usage**

``` php
<?php
// Create a 55x30 image
$im = imagecreatetruecolor(55, 30);
$white = imagecolorallocate($im, 255, 255, 255);

// Draw a white rectangle
imagefilledrectangle($im, 4, 4, 50, 25, $white);

// Save the image
imagepng($im, './imagefilledrectangle.png');
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilledrectangle.png" width="55" height="30" alt="Output of example : imagefilledrectangle()" />

imagefilltoborder
=================

Flood fill to specific color

### Description

<span class="type">bool</span> <span
class="methodname">imagefilltoborder</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">int</span> `$border`</span>
, <span class="methodparam"><span class="type">int</span>
`$color`</span> )

<span class="function">imagefilltoborder</span> performs a flood fill
whose border color is defined by `border`. The starting point for the
fill is `x`, `y` (top left is 0, 0) and the region is filled with color
`color`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x`  
x-coordinate of start.

`y`  
y-coordinate of start.

`border`  
The border color. A color identifier created with <span
class="function">imagecolorallocate</span>.

`color`  
The fill color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Filling an ellipse with a color**

``` php
<?php
// Create the image handle, set the background to white
$im = imagecreatetruecolor(100, 100);
imagefilledrectangle($im, 0, 0, 100, 100, imagecolorallocate($im, 255, 255, 255));

// Draw an ellipse to fill with a black border
imageellipse($im, 50, 50, 50, 50, imagecolorallocate($im, 0, 0, 0));

// Set the border and fill colors
$border = imagecolorallocate($im, 0, 0, 0);
$fill = imagecolorallocate($im, 255, 0, 0);

// Fill the selection
imagefilltoborder($im, 50, 50, $border, $fill);

// Output and free memory
header('Content-type: image/png');
imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilltoborder.png" width="100" height="100" alt="Output of example : Filling an ellipse with a color" />

imagefilter
===========

Applies a filter to an image

### Description

<span class="type">bool</span> <span
class="methodname">imagefilter</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$filtertype`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$arg1`</span> \[, <span class="methodparam"><span
class="type">int</span> `$arg2`</span> \[, <span
class="methodparam"><span class="type">int</span> `$arg3`</span> \[,
<span class="methodparam"><span class="type">int</span> `$arg4`</span>
\]\]\]\] )

<span class="function">imagefilter</span> applies the given filter
`filtertype` on the `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`filtertype`  
`filtertype` can be one of the following:

-   <span class="simpara"> **`IMG_FILTER_NEGATE`**: Reverses all colors
    of the image. </span>
-   <span class="simpara"> **`IMG_FILTER_GRAYSCALE`**: Converts the
    image into grayscale by changing the red, green and blue components
    to their weighted sum using the same coefficients as the REC.601
    luma (Y') calculation. The alpha components are retained. For
    palette images the result may differ due to palette limitations.
    </span>
-   <span class="simpara"> **`IMG_FILTER_BRIGHTNESS`**: Changes the
    brightness of the image. Use `arg1` to set the level of brightness.
    The range for the brightness is -255 to 255. </span>
-   <span class="simpara"> **`IMG_FILTER_CONTRAST`**: Changes the
    contrast of the image. Use `arg1` to set the level of contrast.
    </span>
-   <span class="simpara"> **`IMG_FILTER_COLORIZE`**: Like
    **`IMG_FILTER_GRAYSCALE`**, except you can specify the color. Use
    `arg1`, `arg2` and `arg3` in the form of `red`, `green`, `blue` and
    `arg4` for the `alpha` channel. The range for each color is 0 to
    255. </span>
-   <span class="simpara"> **`IMG_FILTER_EDGEDETECT`**: Uses edge
    detection to highlight the edges in the image. </span>
-   <span class="simpara"> **`IMG_FILTER_EMBOSS`**: Embosses the image.
    </span>
-   <span class="simpara"> **`IMG_FILTER_GAUSSIAN_BLUR`**: Blurs the
    image using the Gaussian method. </span>
-   <span class="simpara"> **`IMG_FILTER_SELECTIVE_BLUR`**: Blurs the
    image. </span>
-   <span class="simpara"> **`IMG_FILTER_MEAN_REMOVAL`**: Uses mean
    removal to achieve a "sketchy" effect. </span>
-   <span class="simpara"> **`IMG_FILTER_SMOOTH`**: Makes the image
    smoother. Use `arg1` to set the level of smoothness. </span>
-   <span class="simpara"> **`IMG_FILTER_PIXELATE`**: Applies pixelation
    effect to the image, use `arg1` to set the block size and `arg2` to
    set the pixelation effect mode. </span>
-   <span class="simpara"> **`IMG_FILTER_SCATTER`**: Applies scatter
    effect to the image, use `arg1` and `arg2` to define the effect
    strength and additionally `arg3` to only apply the on select pixel
    colors. </span>

`arg1`  
-   <span class="simpara"> **`IMG_FILTER_BRIGHTNESS`**: Brightness
    level. </span>
-   <span class="simpara"> **`IMG_FILTER_CONTRAST`**: Contrast level.
    </span>
-   <span class="simpara"> **`IMG_FILTER_COLORIZE`**: Value of red
    component. </span>
-   <span class="simpara"> **`IMG_FILTER_SMOOTH`**: Smoothness level.
    </span>
-   <span class="simpara"> **`IMG_FILTER_PIXELATE`**: Block size in
    pixels. </span>
-   <span class="simpara"> **`IMG_FILTER_SCATTER`**: Effect substraction
    level. This must not be higher or equal to the addition level set
    with `arg2`. </span>

`arg2`  
-   <span class="simpara"> **`IMG_FILTER_COLORIZE`**: Value of green
    component. </span>
-   <span class="simpara"> **`IMG_FILTER_PIXELATE`**: Whether to use
    advanced pixelation effect or not (defaults to **`false`**). </span>
-   <span class="simpara"> **`IMG_FILTER_SCATTER`**: Effect addition
    level. </span>

`arg3`  
-   <span class="simpara"> **`IMG_FILTER_COLORIZE`**: Value of blue
    component. </span>
-   <span class="simpara"> **`IMG_FILTER_SCATTER`**: Optional array
    indexed color values to apply effect at. </span>

`arg4`  
-   <span class="simpara"> **`IMG_FILTER_COLORIZE`**: Alpha channel, A
    value between 0 and 127. 0 indicates completely opaque while 127
    indicates completely transparent. </span>

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                           |
|---------|-------------------------------------------------------|
| 7.4.0   | Scatter support (**`IMG_FILTER_SCATTER`**) was added. |

### Examples

**Example \#1 <span class="function">imagefilter</span> grayscale
example**

``` php
<?php
$im = imagecreatefrompng('dave.png');

if($im && imagefilter($im, IMG_FILTER_GRAYSCALE))
{
    echo 'Image converted to grayscale.';

    imagepng($im, 'dave.png');
}
else
{
    echo 'Conversion to grayscale failed.';
}

imagedestroy($im);
?>
```

**Example \#2 <span class="function">imagefilter</span> brightness
example**

``` php
<?php
$im = imagecreatefrompng('sean.png');

if($im && imagefilter($im, IMG_FILTER_BRIGHTNESS, 20))
{
    echo 'Image brightness changed.';

    imagepng($im, 'sean.png');
    imagedestroy($im);
}
else
{
    echo 'Image brightness change failed.';
}
?>
```

**Example \#3 <span class="function">imagefilter</span> colorize
example**

``` php
<?php
$im = imagecreatefrompng('philip.png');

/* R, G, B, so 0, 255, 0 is green */
if($im && imagefilter($im, IMG_FILTER_COLORIZE, 0, 255, 0))
{
    echo 'Image successfully shaded green.';

    imagepng($im, 'philip.png');
    imagedestroy($im);
}
else
{
    echo 'Green shading failed.';
}
?>
```

**Example \#4 <span class="function">imagefilter</span> negate example**

``` php
<?php
// Define our negate function so its portable for 
// php versions without imagefilter()
function negate($im)
{
    if(function_exists('imagefilter'))
    {
        return imagefilter($im, IMG_FILTER_NEGATE);
    }

    for($x = 0; $x < imagesx($im); ++$x)
    {
        for($y = 0; $y < imagesy($im); ++$y)
        {
            $index = imagecolorat($im, $x, $y);
            $rgb = imagecolorsforindex($index);
            $color = imagecolorallocate($im, 255 - $rgb['red'], 255 - $rgb['green'], 255 - $rgb['blue']);

            imagesetpixel($im, $x, $y, $color);
        }
    }

    return(true);
}

$im = imagecreatefromjpeg('kalle.jpg');

if($im && negate($im))
{
    echo 'Image successfully converted to negative colors.';

    imagejpeg($im, 'kalle.jpg', 100);
    imagedestroy($im);
}
else
{
    echo 'Converting to negative colors failed.';
}
?>
```

**Example \#5 <span class="function">imagefilter</span> pixelate
example**

``` php
<?php
// Load the PHP logo, we need to create two instances 
// to show the differences
$logo1 = imagecreatefrompng('./php.png');
$logo2 = imagecreatefrompng('./php.png');

// Create the image instance we want to show the 
// differences on
$output = imagecreatetruecolor(imagesx($logo1) * 2, imagesy($logo1));

// Apply pixelation to each instance, with a block 
// size of 3
imagefilter($logo1, IMG_FILTER_PIXELATE, 3);
imagefilter($logo2, IMG_FILTER_PIXELATE, 3, true);

// Merge the differences onto the output image
imagecopy($output, $logo1, 0, 0, 0, 0, imagesx($logo1) - 1, imagesy($logo1) - 1);
imagecopy($output, $logo2, imagesx($logo2), 0, 0, 0, imagesx($logo2) - 1, imagesy($logo2) - 1);
imagedestroy($logo1);
imagedestroy($logo2);

// Output the differences
header('Content-Type: image/png');
imagepng($output);
imagedestroy($output);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefilterpixelate.png" width="190" height="51" alt="Output of example : imagefilter() pixelate" />

**Example \#6 <span class="function">imagefilter</span> scatter
example**

``` php
<?php
// Load the image
$logo = imagecreatefrompng('./php.png');

// Apply a very soft scatter effect to the image
imagefilter($logo, IMG_FILTER_SCATTER, 3, 5);

// Output the image with the scatter effect
header('Content-Type: image/png');
imagepng($logo);
imagedestroy($logo);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-scatter.png" width="200" height="106" alt="Output of example : imagefilter() scatter" />

### Notes

> **Note**: <span class="simpara"> The result of
> **`IMG_FILTER_SCATTER`** is always random. </span>

### See Also

-   <span class="function">imageconvolution</span>

imageflip
=========

Flips an image using a given mode

### Description

<span class="type">bool</span> <span class="methodname">imageflip</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">int</span> `$mode`</span> )

Flips the `image` image using the given `mode`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`mode`  
Flip mode, this can be one of the **`IMG_FLIP_*`** constants:

| Constant                  | Meaning                                           |
|---------------------------|---------------------------------------------------|
| **`IMG_FLIP_HORIZONTAL`** | Flips the image horizontally.                     |
| **`IMG_FLIP_VERTICAL`**   | Flips the image vertically.                       |
| **`IMG_FLIP_BOTH`**       | Flips the image both horizontally and vertically. |

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Flips an image vertically**

This example uses the **`IMG_FLIP_VERTICAL`** constant.

``` php
<?php
// File
$filename = 'phplogo.png';

// Content type
header('Content-type: image/png');

// Load
$im = imagecreatefrompng($filename);

// Flip it vertically
imageflip($im, IMG_FLIP_VERTICAL);

// Output
imagejpeg($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageflipvertical.png" width="120" height="67" alt="Output of example: Vertically flipped image" />

**Example \#2 Flips the image horizontally**

This example uses the **`IMG_FLIP_HORIZONTAL`** constant.

``` php
<?php
// File
$filename = 'phplogo.png';

// Content type
header('Content-type: image/png');

// Load
$im = imagecreatefrompng($filename);

// Flip it horizontally
imageflip($im, IMG_FLIP_HORIZONTAL);

// Output
imagejpeg($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagefliphorizontal.png" width="120" height="67" alt="Output of example: Horizontally flipped image" />

imagefontheight
===============

Get font height

### Description

<span class="type">int</span> <span
class="methodname">imagefontheight</span> ( <span
class="methodparam"><span class="type">int</span> `$font`</span> )

Returns the pixel height of a character in the specified font.

### Parameters

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

### Return Values

Returns the pixel height of the font.

### Examples

**Example \#1 Using <span class="function">imagefontheight</span> on
built-in fonts**

``` php
<?php
echo 'Font height: ' . imagefontheight(4);
?>
```

The above example will output something similar to:

    Font height: 16

**Example \#2 Using <span class="function">imagefontheight</span>
together with <span class="function">imageloadfont</span>**

``` php
<?php
// Load a .gdf font
$font = imageloadfont('anonymous.gdf');

echo 'Font height: ' . imagefontheight($font);
?>
```

The above example will output something similar to:

    Font height: 43

### See Also

-   <span class="function">imagefontwidth</span>
-   <span class="function">imageloadfont</span>

imagefontwidth
==============

Get font width

### Description

<span class="type">int</span> <span
class="methodname">imagefontwidth</span> ( <span
class="methodparam"><span class="type">int</span> `$font`</span> )

Returns the pixel width of a character in font.

### Parameters

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

### Return Values

Returns the pixel width of the font.

### Examples

**Example \#1 Using <span class="function">imagefontwidth</span> on
built-in fonts**

``` php
<?php
echo 'Font width: ' . imagefontwidth(4);
?>
```

The above example will output something similar to:

    Font width: 8

**Example \#2 Using <span class="function">imagefontwidth</span>
together with <span class="function">imageloadfont</span>**

``` php
<?php
// Load a .gdf font
$font = imageloadfont('anonymous.gdf');

echo 'Font width: ' . imagefontwidth($font);
?>
```

The above example will output something similar to:

    Font width: 23

### See Also

-   <span class="function">imagefontheight</span>
-   <span class="function">imageloadfont</span>

imageftbbox
===========

Give the bounding box of a text using fonts via freetype2

### Description

<span class="type">array</span> <span
class="methodname">imageftbbox</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> , <span
class="methodparam"><span class="type">float</span> `$angle`</span> ,
<span class="methodparam"><span class="type">string</span>
`$fontfile`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> \[, <span
class="methodparam"><span class="type">array</span> `$extrainfo`</span>
\] )

This function calculates and returns the bounding box in pixels for a
FreeType text.

> **Note**:
>
> <span class="function">imageftbbox</span> is an extended variant of
> <span class="function">imagettfbbox</span> which additionally supports
> the `extrainfo`.

### Parameters

`size`  
The font size in points.

`angle`  
Angle in degrees in which `text` will be measured.

`fontfile`  
The name of the TrueType font file (can be a URL). Depending on which
version of the GD library that PHP is using, it may attempt to search
for files that do not begin with a leading '/' by appending '.ttf' to
the filename and searching along a library-defined font path.

`text`  
The string to be measured.

`extrainfo`  
| Key           | Type                            | Meaning                     |
|---------------|---------------------------------|-----------------------------|
| *linespacing* | <span class="type">float</span> | Defines drawing linespacing |

### Return Values

<span class="function">imageftbbox</span> returns an array with 8
elements representing four points making the bounding box of the text:

|     |                                |
|-----|--------------------------------|
| 0   | lower left corner, X position  |
| 1   | lower left corner, Y position  |
| 2   | lower right corner, X position |
| 3   | lower right corner, Y position |
| 4   | upper right corner, X position |
| 5   | upper right corner, Y position |
| 6   | upper left corner, X position  |
| 7   | upper left corner, Y position  |

The points are relative to the *text* regardless of the `angle`, so
"upper left" means in the top left-hand corner seeing the text
horizontally.

### Examples

**Example \#1 <span class="function">imageftbbox</span> example**

``` php
<?php
// Create a 300x150 image
$im = imagecreatetruecolor(300, 150);
$black = imagecolorallocate($im, 0, 0, 0);
$white = imagecolorallocate($im, 255, 255, 255);

// Set the background to be white
imagefilledrectangle($im, 0, 0, 299, 299, $white);

// Path to our font file
$font = './arial.ttf';

// First we create our bounding box
$bbox = imageftbbox(10, 0, $font, 'The PHP Documentation Group');

// This is our cordinates for X and Y
$x = $bbox[0] + (imagesx($im) / 2) - ($bbox[4] / 2) - 5;
$y = $bbox[1] + (imagesy($im) / 2) - ($bbox[5] / 2) - 5;

imagefttext($im, 10, 0, $x, $y, $black, $font, 'The PHP Documentation Group');

// Output to browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### Notes

> **Note**: <span class="simpara">This function is only available if PHP
> is compiled with freetype support (**--with-freetype-dir=DIR**)
> </span>

### See Also

-   <span class="function">imagefttext</span>
-   <span class="function">imagettfbbox</span>

imagefttext
===========

Write text to the image using fonts using FreeType 2

### Description

<span class="type">array</span> <span
class="methodname">imagefttext</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">float</span> `$size`</span> ,
<span class="methodparam"><span class="type">float</span>
`$angle`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> , <span
class="methodparam"><span class="type">string</span> `$fontfile`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> \[, <span class="methodparam"><span
class="type">array</span> `$extrainfo`</span> \] )

> **Note**:
>
> <span class="function">imagefttext</span> is an extended variant of
> <span class="function">imagettftext</span> which additionally supports
> the `extrainfo`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`size`  
The font size to use in points.

`angle`  
The angle in degrees, with 0 degrees being left-to-right reading text.
Higher values represent a counter-clockwise rotation. For example, a
value of 90 would result in bottom-to-top reading text.

`x`  
The coordinates given by `x` and `y` will define the basepoint of the
first character (roughly the lower-left corner of the character). This
is different from the <span class="function">imagestring</span>, where
`x` and `y` define the upper-left corner of the first character. For
example, "top left" is 0, 0.

`y`  
The y-ordinate. This sets the position of the fonts baseline, not the
very bottom of the character.

`color`  
The index of the desired color for the text, see <span
class="function">imagecolorexact</span>.

`fontfile`  
The path to the TrueType font you wish to use.

Depending on which version of the GD library PHP is using, *when
`fontfile` does not begin with a leading */* then *.ttf* will be
appended* to the filename and the library will attempt to search for
that filename along a library-defined font path.

When using versions of the GD library lower than 2.0.18, a *space*
character, rather than a semicolon, was used as the 'path separator' for
different font files. Unintentional use of this feature will result in
the warning message: *Warning: Could not find/open font*. For these
affected versions, the only solution is moving the font to a path which
does not contain spaces.

In many cases where a font resides in the same directory as the script
using it the following trick will alleviate any include problems.

``` php
<?php
// Set the enviroment variable for GD
putenv('GDFONTPATH=' . realpath('.'));

// Name the font to be used (note the lack of the .ttf extension)
$font = 'SomeFont';
?>
```

`text`  
Text to be inserted into image.

`extrainfo`  
| Key           | Type                            | Meaning                     |
|---------------|---------------------------------|-----------------------------|
| *linespacing* | <span class="type">float</span> | Defines drawing linespacing |

### Return Values

This function returns an array defining the four points of the box,
starting in the lower left and moving counter-clockwise:

|     |                          |
|-----|--------------------------|
| 0   | lower left x-coordinate  |
| 1   | lower left y-coordinate  |
| 2   | lower right x-coordinate |
| 3   | lower right y-coordinate |
| 4   | upper right x-coordinate |
| 5   | upper right y-coordinate |
| 6   | upper left x-coordinate  |
| 7   | upper left y-coordinate  |

### Examples

**Example \#1 <span class="function">imagefttext</span> example**

``` php
<?php
// Create a 300x100 image
$im = imagecreatetruecolor(300, 100);
$red = imagecolorallocate($im, 0xFF, 0x00, 0x00);
$black = imagecolorallocate($im, 0x00, 0x00, 0x00);

// Make the background red
imagefilledrectangle($im, 0, 0, 299, 99, $red);

// Path to our ttf font file
$font_file = './arial.ttf';

// Draw the text 'PHP Manual' using font size 13
imagefttext($im, 13, 0, 105, 55, $black, $font_file, 'PHP Manual');

// Output image to the browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### Notes

> **Note**: <span class="simpara">This function is only available if PHP
> is compiled with freetype support (**--with-freetype-dir=DIR**)
> </span>

### See Also

-   <span class="function">imageftbbox</span>
-   <span class="function">imagettftext</span>

imagegammacorrect
=================

Apply a gamma correction to a GD image

### Description

<span class="type">bool</span> <span
class="methodname">imagegammacorrect</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">float</span>
`$inputgamma`</span> , <span class="methodparam"><span
class="type">float</span> `$outputgamma`</span> )

Applies gamma correction to the given gd `image` given an input and an
output gamma.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`inputgamma`  
The input gamma.

`outputgamma`  
The output gamma.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagegammacorrect</span> usage**

``` php
<?php
// Create image instance
$im = imagecreatefromgif('php.gif');

// Correct gamma, out = 1.537
imagegammacorrect($im, 1.0, 1.537);

// Save and free image
imagegif($im, './php_gamma_corrected.gif');
imagedestroy($im);
?>
```

imagegd2
========

Output GD2 image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagegd2</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
NULL</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$chunk_size`<span class="initializer"> =
128</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
IMG\_GD2\_RAW</span></span> \]\]\] )

Outputs a GD2 image to the given `to`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

`chunk_size`  
Chunk size.

`type`  
Either **`IMG_GD2_RAW`** or **`IMG_GD2_COMPRESSED`**. Default is
**`IMG_GD2_RAW`**.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Outputting a GD2 image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);

// Output the image
imagegd2($im);

// Free up memory
imagedestroy($im);
?>
```

**Example \#2 Saving a GD2 image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);

// Save the gd2 image
// The file format for GD2 images is .gd2, see http://www.libgd.org/GdFileFormats
imagegd2($im, 'simple.gd2');

// Free up memory
imagedestroy($im);
?>
```

### Notes

> **Note**:
>
> The GD2 format is commonly used to allow fast loading of parts of
> images. Note that the GD2 format is only usable in GD2-compatible
> applications.

**Warning**

The GD and GD2 image formats are proprietary image formats of libgd.
They have to be regarded *obsolete*, and should only be used for
development and testing purposes.

### See Also

-   <span class="function">imagegd</span>

imagegd
=======

Output GD image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagegd</span> (
<span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
NULL</span></span> \] )

Outputs a GD image to the given `to`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Changelog

| Version | Description                                                                                                                             |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">imagegd</span> now allows to output truecolor images. Formerly, these have been implicitly converted to palette. |

### Examples

**Example \#1 Outputting a GD image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);

// Output the image
imagegd($im);

// Free up memory
imagedestroy($im);
?>
```

**Example \#2 Saving a GD image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  "A Simple Text String", $text_color);

// Save the gd image
// The file format for GD images is .gd, see http://www.libgd.org/GdFileFormats
imagegd($im, 'simple.gd');

// Free up memory
imagedestroy($im);
?>
```

### Notes

> **Note**:
>
> The GD format is commonly used to allow fast loading of parts of
> images. Note that the GD format is only usable in GD-compatible
> applications.

**Warning**

The GD and GD2 image formats are proprietary image formats of libgd.
They have to be regarded *obsolete*, and should only be used for
development and testing purposes.

### See Also

-   <span class="function">imagegd2</span>

imagegetclip
============

Get the clipping rectangle

### Description

<span class="type">array</span> <span
class="methodname">imagegetclip</span> ( <span class="methodparam"><span
class="type">resource</span> `$im`</span> )

<span class="function">imagegetclip</span> retrieves the current
clipping rectangle, i.e. the area beyond which no pixels will be drawn.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

The function returns an indexed array with the coordinates of the
clipping rectangle which has the following entries:

-   <span class="simpara">x-coordinate of the upper left corner</span>
-   <span class="simpara">y-coordinate of the upper left corner</span>
-   <span class="simpara">x-coordinate of the lower right corner</span>
-   <span class="simpara">y-coordinate of the lower right corner</span>

### Examples

**Example \#1 <span class="function">imagegetclip</span> example**

Setting and retrieving the clipping rectangle.

``` php
<?php
$im = imagecreate(100, 100);
imagesetclip($im, 10,10, 89,89);
print_r(imagegetclip($im));
```

The above example will output:

    Array
    (
        [0] => 10
        [1] => 10
        [2] => 89
        [3] => 89
    )

### See Also

-   <span class="function">imagesetclip</span>

imagegetinterpolation
=====================

Get the interpolation method

### Description

<span class="type">int</span> <span
class="methodname">imagegetinterpolation</span> ( <span
class="methodparam"><span class="type">GdImage</span> `$image`</span> )

Gets the currently set interpolation method of the `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Returns the interpolation method.

### See Also

-   <span class="function">imagesetinterpolation</span>

imagegif
========

Output image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagegif</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \] )

<span class="function">imagegif</span> creates the GIF file in `to` from
the image `image`. The `image` argument is the return from the <span
class="function">imagecreate</span> or *imagecreatefrom\** function.

The image format will be GIF87a unless the image has been made
transparent with <span class="function">imagecolortransparent</span>, in
which case the image format will be GIF89a.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Outputting an image using <span
class="function">imagegif</span>**

``` php
<?php
// Create a new image instance
$im = imagecreatetruecolor(100, 100);

// Make the background white
imagefilledrectangle($im, 0, 0, 99, 99, 0xFFFFFF);

// Draw a text string on the image
imagestring($im, 3, 40, 20, 'GD Library', 0xFFBA00);

// Output the image to browser
header('Content-Type: image/gif');

imagegif($im);
imagedestroy($im);
?>
```

**Example \#2 Converting a PNG image to GIF using <span
class="function">imagegif</span>**

``` php
<?php

// Load the PNG
$png = imagecreatefrompng('./php.png');

// Save the image as a GIF
imagegif($png, './php.gif');

// Free from memory
imagedestroy($png);

// We're done
echo 'Converted PNG image to GIF with success!';
?>
```

### Notes

> **Note**:
>
> GIF support was removed from the GD library in Version 1.6, and added
> back in Version 2.0.28. This function is not available between these
> versions. For more information, see the
> <a href="http://www.libgd.org/" class="link external">» GD Project</a>
> site.
>
> The following code snippet allows you to write more portable PHP
> applications by auto-detecting the type of GD support which is
> available. Replace the sequence *header ("Content-Type: image/gif");
> imagegif ($im);* by the more flexible sequence:
>
> ``` php
> <?php
> // Create a new image instance
> $im = imagecreatetruecolor(100, 100);
>
> // Do some image operations here
>
> // Handle output
> if(function_exists('imagegif'))
> {
>     // For GIF
>     header('Content-Type: image/gif');
>
>     imagegif($im);
> }
> elseif(function_exists('imagejpeg'))
> {
>     // For JPEG
>     header('Content-Type: image/jpeg');
>
>     imagejpeg($im, NULL, 100);
> }
> elseif(function_exists('imagepng'))
> {
>     // For PNG
>     header('Content-Type: image/png');
>
>     imagepng($im);
> }
> elseif(function_exists('imagewbmp'))
> {
>     // For WBMP
>     header('Content-Type: image/vnd.wap.wbmp');
>
>     imagewbmp($im);
> }
> else
> {
>     imagedestroy($im);
>
>     die('No image support in this PHP server');
> }
>
> // If image support was found for one of these
> // formats, then free it from memory
> if($im)
> {
>     imagedestroy($im);
> }
> ?>
> ```

> **Note**:
>
> You can use the function <span class="function">imagetypes</span> for
> checking the presence of the various supported image formats:
>
> ``` php
> <?php
> if(imagetypes() & IMG_GIF)
> {
>     header('Content-Type: image/gif');
>     imagegif($im);
> }
> elseif(imagetypes() & IMG_JPG)
> {
>     /* ... etc. */
> }
> ?>
> ```

### See Also

-   <span class="function">imagepng</span>
-   <span class="function">imagewbmp</span>
-   <span class="function">imagejpeg</span>
-   <span class="function">imagetypes</span>

imagegrabscreen
===============

Captures the whole screen

### Description

<span class="type">resource</span> <span
class="methodname">imagegrabscreen</span> ( <span
class="methodparam">void</span> )

Grabs a screenshot of the whole screen.

> **Note**:
>
> This function is only available on Windows.

### Return Values

Returns an image resource identifier on success, **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagegrabscreen</span> example**

This example demonstrates how to take a screenshot of the current screen
and save it as a png image.

``` php
<?php
$im = imagegrabscreen();
imagepng($im, "myscreenshot.png");
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagegrabwindow</span>

imagegrabwindow
===============

Captures a window

### Description

<span class="type">resource</span> <span
class="methodname">imagegrabwindow</span> ( <span
class="methodparam"><span class="type">int</span>
`$window_handle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$client_area`<span class="initializer"> =
0</span></span> \] )

Grabs a window or its client area using a windows handle (HWND property
in COM instance)

> **Note**:
>
> This function is only available on Windows.

### Parameters

`window_handle`  
The HWND window ID.

`client_area`  
Include the client area of the application window.

### Return Values

Returns an image resource identifier on success, **`false`** on failure.

### Errors/Exceptions

E\_NOTICE is issued if `window_handle` is invalid window handle.
E\_WARNING is issued if the Windows API is too old.

### Examples

**Example \#1 <span class="function">imagegrabwindow</span> example**

Capture a window (IE for example)

``` php
<?php
$browser = new COM("InternetExplorer.Application");
$handle = $browser->HWND;
$browser->Visible = true;
$im = imagegrabwindow($handle);
$browser->Quit();
imagepng($im, "iesnap.png");
imagedestroy($im);
?>
```

Capture a window (IE for example) but with its content

``` php
<?php
$browser = new COM("InternetExplorer.Application");
$handle = $browser->HWND;
$browser->Visible = true;
$browser->Navigate("http://www.libgd.org");

/* Still working? */
while ($browser->Busy) {
    com_message_pump(4000);
}
$im = imagegrabwindow($handle, 0);
$browser->Quit();
imagepng($im, "iesnap.png");
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagegrabscreen</span>

imageinterlace
==============

Enable or disable interlace

### Description

<span class="type">int</span> <span
class="methodname">imageinterlace</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$interlace`<span class="initializer"> = 0</span></span> \] )

<span class="function">imageinterlace</span> turns the interlace bit on
or off.

If the interlace bit is set and the image is used as a JPEG image, the
image is created as a progressive JPEG.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`interlace`  
If non-zero, the image will be interlaced, else the interlace bit is
turned off.

### Return Values

Returns 1 if the interlace bit is set for the image, 0 otherwise.

### Examples

**Example \#1 Turn on interlacing using <span
class="function">imageinterlace</span>**

``` php
<?php
// Create an image instance
$im = imagecreatefromgif('php.gif');

// Enable interlancing
imageinterlace($im, true);

// Save the interlaced image
imagegif($im, './php_interlaced.gif');
imagedestroy($im);
?>
```

imageistruecolor
================

Finds whether an image is a truecolor image

### Description

<span class="type">bool</span> <span
class="methodname">imageistruecolor</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> )

<span class="function">imageistruecolor</span> finds whether the image
`image` is a truecolor image.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Returns **`true`** if the `image` is truecolor, **`false`** otherwise.

### Examples

**Example \#1 Simple detection of true color image instances using <span
class="function">imageistruecolor</span>**

``` php
<?php
// $im is an image instance

// Check if image is a true color image or not
if(!imageistruecolor($im))
{
    // Create a new true color image instance
    $tc = imagecreatetruecolor(imagesx($im), imagesy($im));

    // Copy over the pixels
    imagecopy($tc, $im, 0, 0, 0, 0, imagesx($im), imagesy($im));
    imagedestroy($im);

    $im = $tc;
    $tc = NULL;

    // OR use imagepalettetotruecolor()
}

// Continue working with image instance
?>
```

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">imagepalettetotruecolor</span>

imagejpeg
=========

Output image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagejpeg</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$quality`<span class="initializer"> =
-1</span></span> \]\] )

<span class="function">imagejpeg</span> creates a JPEG file from the
given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

`quality`  
`quality` is optional, and ranges from 0 (worst quality, smaller file)
to 100 (best quality, biggest file). The default (*-1*) uses the default
IJG quality value (about 75).

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Outputting a JPEG image to the browser**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Set the content type header - in this case image/jpeg
header('Content-Type: image/jpeg');

// Output the image
imagejpeg($im);

// Free up memory
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagejpeg.jpg" width="120" height="20" alt="Output of example : Outputting a JPEG image" />

**Example \#2 Saving a JPEG image to a file**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Save the image as 'simpletext.jpg'
imagejpeg($im, 'simpletext.jpg');

// Free up memory
imagedestroy($im);
?>
```

**Example \#3 Outputting the image at 75% quality to the browser**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Set the content type header - in this case image/jpeg
header('Content-Type: image/jpeg');

// Skip the to parameter using NULL, then set the quality to 75%
imagejpeg($im, NULL, 75);

// Free up memory
imagedestroy($im);
?>
```

### Notes

> **Note**:
>
> If you want to output Progressive JPEGs, you need to set interlacing
> on with <span class="function">imageinterlace</span>.

### See Also

-   <span class="function">imagepng</span>
-   <span class="function">imagegif</span>
-   <span class="function">imagewbmp</span>
-   <span class="function">imageinterlace</span>
-   <span class="function">imagetypes</span>

imagelayereffect
================

Set the alpha blending flag to use layering effects

### Description

<span class="type">bool</span> <span
class="methodname">imagelayereffect</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$effect`</span>
)

Set the alpha blending flag to use layering effects.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`effect`  
One of the following constants:

**`IMG_EFFECT_REPLACE`**  
<span class="simpara"> Use pixel replacement (equivalent of passing
**`true`** to <span class="function">imagealphablending</span>) </span>

**`IMG_EFFECT_ALPHABLEND`**  
<span class="simpara"> Use normal pixel blending (equivalent of passing
**`false`** to <span class="function">imagealphablending</span>) </span>

**`IMG_EFFECT_NORMAL`**  
<span class="simpara"> Same as **`IMG_EFFECT_ALPHABLEND`**. </span>

**`IMG_EFFECT_OVERLAY`**  
<span class="simpara"> Overlay has the effect that black background
pixels will remain black, white background pixels will remain white, but
grey background pixels will take the colour of the foreground pixel.
</span>

**`IMG_EFFECT_MULTIPLY`**  
<span class="simpara"> Overlays with a multiply effect. </span>

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                             |
|---------|-----------------------------------------------------------------------------------------|
| 7.2.0   | Added **`IMG_EFFECT_MULTIPLY`** (requires system libgd \>= 2.1.1 or the bundled libgd). |

### Examples

**Example \#1 <span class="function">imagelayereffect</span> example**

``` php
<?php
// Setup an image
$im = imagecreatetruecolor(100, 100);

// Set a background
imagefilledrectangle($im, 0, 0, 100, 100, imagecolorallocate($im, 220, 220, 220));

// Apply the overlay alpha blending flag
imagelayereffect($im, IMG_EFFECT_OVERLAY);

// Draw two grey ellipses
imagefilledellipse($im, 50, 50, 40, 40, imagecolorallocate($im, 100, 255, 100));
imagefilledellipse($im, 50, 50, 50, 80, imagecolorallocate($im, 100, 100, 255));
imagefilledellipse($im, 50, 50, 80, 50, imagecolorallocate($im, 255, 100, 100));

// Output
header('Content-type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagelayereffect.png" width="100" height="100" alt="Output of example : imagelayereffect()" />

imageline
=========

Draw a line

### Description

<span class="type">bool</span> <span class="methodname">imageline</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">int</span> `$x1`</span> , <span class="methodparam"><span
class="type">int</span> `$y1`</span> , <span class="methodparam"><span
class="type">int</span> `$x2`</span> , <span class="methodparam"><span
class="type">int</span> `$y2`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

Draws a line between the two given points.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x1`  
x-coordinate for first point.

`y1`  
y-coordinate for first point.

`x2`  
x-coordinate for second point.

`y2`  
y-coordinate for second point.

`color`  
The line color. A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Drawing a thick line**

``` php
<?php

function imagelinethick($image, $x1, $y1, $x2, $y2, $color, $thick = 1)
{
    /* this way it works well only for orthogonal lines
    imagesetthickness($image, $thick);
    return imageline($image, $x1, $y1, $x2, $y2, $color);
    */
    if ($thick == 1) {
        return imageline($image, $x1, $y1, $x2, $y2, $color);
    }
    $t = $thick / 2 - 0.5;
    if ($x1 == $x2 || $y1 == $y2) {
        return imagefilledrectangle($image, round(min($x1, $x2) - $t), round(min($y1, $y2) - $t), round(max($x1, $x2) + $t), round(max($y1, $y2) + $t), $color);
    }
    $k = ($y2 - $y1) / ($x2 - $x1); //y = kx + q
    $a = $t / sqrt(1 + pow($k, 2));
    $points = array(
        round($x1 - (1+$k)*$a), round($y1 + (1-$k)*$a),
        round($x1 - (1-$k)*$a), round($y1 - (1+$k)*$a),
        round($x2 + (1+$k)*$a), round($y2 - (1-$k)*$a),
        round($x2 + (1-$k)*$a), round($y2 + (1+$k)*$a),
    );
    imagefilledpolygon($image, $points, 4, $color);
    return imagepolygon($image, $points, 4, $color);
}

?>
```

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">imagecolorallocate</span>

imageloadfont
=============

Load a new font

### Description

<span class="type">int</span> <span
class="methodname">imageloadfont</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

<span class="function">imageloadfont</span> loads a user-defined bitmap
and returns its identifier.

### Parameters

`file`  
The font file format is currently binary and architecture dependent.
This means you should generate the font files on the same type of CPU as
the machine you are running PHP on.

| byte position | C data type | description                                                                                                    |
|---------------|-------------|----------------------------------------------------------------------------------------------------------------|
| byte 0-3      | int         | number of characters in the font                                                                               |
| byte 4-7      | int         | value of first character in the font (often 32 for space)                                                      |
| byte 8-11     | int         | pixel width of each character                                                                                  |
| byte 12-15    | int         | pixel height of each character                                                                                 |
| byte 16-      | char        | array with character data, one byte per pixel in each character, for a total of (nchars\*width\*height) bytes. |

### Return Values

The font identifier which is always bigger than 5 to avoid conflicts
with built-in fonts or **`false`** on errors.

### Examples

**Example \#1 <span class="function">imageloadfont</span> usage
example**

``` php
<?php
// Create a new image instance
$im = imagecreatetruecolor(50, 20);
$black = imagecolorallocate($im, 0, 0, 0);
$white = imagecolorallocate($im, 255, 255, 255);

// Make the background white
imagefilledrectangle($im, 0, 0, 49, 19, $white);

// Load the gd font and write 'Hello'
$font = imageloadfont('./04b.gdf');
imagestring($im, $font, 0, 0, 'Hello', $black);

// Output to browser
header('Content-type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagefontwidth</span>
-   <span class="function">imagefontheight</span>

imageopenpolygon
================

Draws an open polygon

### Description

<span class="type">bool</span> <span
class="methodname">imageopenpolygon</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">array</span>
`$points`</span> , <span class="methodparam"><span
class="type">int</span> `$num_points`</span> , <span
class="methodparam"><span class="type">int</span> `$color`</span> )

<span class="function">imageopenpolygon</span> draws an open polygon on
the given `image`. Contrary to <span
class="function">imagepolygon</span>, no line is drawn between the last
and the first point.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`points`  
An array containing the polygon's vertices, e.g.:

|             |      |
|-------------|------|
| points\[0\] | = x0 |
| points\[1\] | = y0 |
| points\[2\] | = x1 |
| points\[3\] | = y1 |

`num_points`  
Total number of points (vertices), which must be at least 3.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imageopenpolygon</span> example**

``` php
<?php
// Create a blank image
$image = imagecreatetruecolor(400, 300);

// Allocate a color for the polygon
$col_poly = imagecolorallocate($image, 255, 255, 255);

// Draw the polygon
imageopenpolygon($image, array(
        0,   0,
        100, 200,
        300, 200
    ),
    3,
    $col_poly);

// Output the picture to the browser
header('Content-type: image/png');

imagepng($image);
imagedestroy($image);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imageopenpolygon.png" width="400" height="300" alt="Output of example : imageopenpolygon()" />

### See Also

-   <span class="function">imagepolygon</span>

imagepalettecopy
================

Copy the palette from one image to another

### Description

<span class="type">void</span> <span
class="methodname">imagepalettecopy</span> ( <span
class="methodparam"><span class="type">resource</span>
`$destination`</span> , <span class="methodparam"><span
class="type">resource</span> `$source`</span> )

<span class="function">imagepalettecopy</span> copies the palette from
the `source` image to the `destination` image.

### Parameters

`destination`  
The destination image resource.

`source`  
The source image resource.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">imagepalettecopy</span> example**

``` php
<?php
// Create two palette images
$palette1 = imagecreate(100, 100);
$palette2 = imagecreate(100, 100);

// Allocate the background to be 
// green in the first palette image
$green = imagecolorallocate($palette1, 0, 255, 0);

// Copy the palette from image 1 to image 2
imagepalettecopy($palette2, $palette1);

// Since the palette is now copied we can use the 
// green color allocated to image 1 without using 
// imagecolorallocate() twice
imagefilledrectangle($palette2, 0, 0, 99, 99, $green);

// Output image to the browser
header('Content-type: image/png');

imagepng($palette2);
imagedestroy($palette1);
imagedestroy($palette2);
?>
```

imagepalettetotruecolor
=======================

Converts a palette based image to true color

### Description

<span class="type">bool</span> <span
class="methodname">imagepalettetotruecolor</span> ( <span
class="methodparam"><span class="type">resource</span> `$src`</span> )

Converts a palette based image, created by functions like <span
class="function">imagecreate</span> to a true color image, like <span
class="function">imagecreatetruecolor</span>.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Returns **`true`** if the convertion was complete, or if the source
image already is a true color image, otherwise **`false`** is returned.

### Examples

**Example \#1 Converts any image resource to true color**

``` php
<?php
// Backwards compatiblity
if(!function_exists('imagepalettetotruecolor'))
{
    function imagepalettetotruecolor(&$src)
    {
        if(imageistruecolor($src))
        {
            return(true);
        }

        $dst = imagecreatetruecolor(imagesx($src), imagesy($src));

        imagecopy($dst, $src, 0, 0, 0, 0, imagesx($src), imagesy($src));
        imagedestroy($src);

        $src = $dst;

        return(true);
    }
}

// Helper closure
$typeof = function() use($im)
{
    echo 'typeof($im) = ' . (imageistruecolor($im) ? 'true color' : 'palette'), PHP_EOL;
};

// Create a palette based image
$im = imagecreate(100, 100);
$typeof();

// Convert it to true color
imagepalettetotruecolor($im);
$typeof();

// Free the memory
imagedestroy($im);
?>
```

The above example will output:

    typeof($im) = palette
    typeof($im) = true color

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">imageistruecolor</span>

imagepng
========

Output a PNG image to either the browser or a file

### Description

<span class="type">bool</span> <span class="methodname">imagepng</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$quality`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$filters`<span class="initializer"> =
-1</span></span> \]\]\] )

Outputs or saves a PNG image from the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

> **Note**:
>
> **`null`** is invalid if the `quality` and `filters` arguments are not
> used.

`quality`  
Compression level: from 0 (no compression) to 9. The default (*-1*) uses
the zlib compression default. For more information see the
<a href="http://www.zlib.net/manual.html" class="link external">» zlib manual</a>.

`filters`  
Allows reducing the PNG file size. It is a bitmask field which may be
set to any combination of the *PNG\_FILTER\_XXX* constants.
**`PNG_NO_FILTER`** or **`PNG_ALL_FILTERS`** may also be used to
respectively disable or activate all filters. The default value (*-1*)
disables filtering.

**Caution**
The `filters` parameter is ignored by system libgd.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

``` php
<?php
$im = imagecreatefrompng("test.png");

header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### See Also

-   <span class="function">imagegif</span>
-   <span class="function">imagewbmp</span>
-   <span class="function">imagejpeg</span>
-   <span class="function">imagetypes</span>
-   <span class="function">imagesavealpha</span>

imagepolygon
============

Draws a polygon

### Description

<span class="type">bool</span> <span
class="methodname">imagepolygon</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">array</span> `$points`</span> ,
<span class="methodparam"><span class="type">int</span>
`$num_points`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

<span class="function">imagepolygon</span> creates a polygon in the
given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`points`  
An array containing the polygon's vertices, e.g.:

|             |      |
|-------------|------|
| points\[0\] | = x0 |
| points\[1\] | = y0 |
| points\[2\] | = x1 |
| points\[3\] | = y1 |

`num_points`  
Total number of points (vertices), which must be at least 3.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagepolygon</span> example**

``` php
<?php
// Create a blank image
$image = imagecreatetruecolor(400, 300);

// Allocate a color for the polygon
$col_poly = imagecolorallocate($image, 255, 255, 255);

// Draw the polygon
imagepolygon($image, array(
        0,   0,
        100, 200,
        300, 200
    ),
    3,
    $col_poly);

// Output the picture to the browser
header('Content-type: image/png');

imagepng($image);
imagedestroy($image);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagepolygon.png" width="400" height="300" alt="Output of example : imagepolygon()" />

### See Also

-   <span class="function">imagefilledpolygon</span>
-   <span class="function">imageopenpolygon</span>
-   <span class="function">imagecreate</span>
-   <span class="function">imagecreatetruecolor</span>

imagerectangle
==============

Draw a rectangle

### Description

<span class="type">bool</span> <span
class="methodname">imagerectangle</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$x1`</span> ,
<span class="methodparam"><span class="type">int</span> `$y1`</span> ,
<span class="methodparam"><span class="type">int</span> `$x2`</span> ,
<span class="methodparam"><span class="type">int</span> `$y2`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

<span class="function">imagerectangle</span> creates a rectangle
starting at the specified coordinates.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x1`  
Upper left x coordinate.

`y1`  
Upper left y coordinate 0, 0 is the top left corner of the image.

`x2`  
Bottom right x coordinate.

`y2`  
Bottom right y coordinate.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Simple <span class="function">imagerectangle</span>
example**

``` php
<?php
// Create a 200 x 200 image
$canvas = imagecreatetruecolor(200, 200);

// Allocate colors
$pink = imagecolorallocate($canvas, 255, 105, 180);
$white = imagecolorallocate($canvas, 255, 255, 255);
$green = imagecolorallocate($canvas, 132, 135, 28);

// Draw three rectangles each with its own color
imagerectangle($canvas, 50, 50, 150, 150, $pink);
imagerectangle($canvas, 45, 60, 120, 100, $white);
imagerectangle($canvas, 100, 120, 75, 160, $green);

// Output and free from memory
header('Content-Type: image/jpeg');

imagejpeg($canvas);
imagedestroy($canvas);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagerectangle.jpg" width="200" height="200" alt="Output of example : Simple imagerectangle() example" />

imageresolution
===============

Get or set the resolution of the image

### Description

<span class="type">mixed</span> <span
class="methodname">imageresolution</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> )

<span class="type">mixed</span> <span
class="methodname">imageresolution</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$res_x`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$res_y`<span class="initializer"> = $res\_x</span></span> \] )

<span class="function">imageresolution</span> allows to set and get the
resolution of an image in DPI (dots per inch). If none of the optional
parameters is given, the current resolution is returned as indexed
array. If only `res_x` is given, the horizontal and vertical resolution
are set to this value. If both optional parameters are given, the
horizontal and vertical resolution are set to these values,
respectively.

The resolution is only used as meta information when images are read
from and written to formats supporting this kind of information
(curently PNG and JPEG). It does not affect any drawing operations. The
default resolution for new images is 96 DPI.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`res_x`  
The horizontal resolution in DPI.

`res_y`  
The vertical resolution in DPI.

### Return Values

When used as getter (first signature), it returns an indexed array of
the horizontal and vertical resolution on success, or **`false`** on
failure. When used as setter (second signature), it returns **`true`**
on success, or **`false`** on failure.

### Examples

**Example \#1 Setting and getting the resolution of an image**

``` php
<?php
$im = imagecreatetruecolor(100, 100);
imageresolution($im, 200);
print_r(imageresolution($im));
imageresolution($im, 300, 72);
print_r(imageresolution($im));
?>
```

The above example will output:

    Array
    (
        [0] => 200
        [1] => 200
    )
    Array
    (
        [0] => 300
        [1] => 72
    )

imagerotate
===========

Rotate an image with a given angle

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">imagerotate</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">float</span> `$angle`</span> ,
<span class="methodparam"><span class="type">int</span>
`$bgd_color`</span> \[, <span class="methodparam"><span
class="type">int</span> `$dummy`<span class="initializer"> =
0</span></span> \] )

Rotates the `image` image using the given `angle` in degrees.

The center of rotation is the center of the image, and the rotated image
may have different dimensions than the original image.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`angle`  
Rotation angle, in degrees. The rotation angle is interpreted as the
number of degrees to rotate the image anticlockwise.

`bgd_color`  
Specifies the color of the uncovered zone after the rotation

`dummy`  
This parameter is unused.

### Return Values

Returns an image resource for the rotated image, or **`false`** on
failure.

### Examples

**Example \#1 Rotate an image 180 degrees**

This example rotates an image 180 degrees - upside down.

``` php
<?php
// File and rotation
$filename = 'test.jpg';
$degrees = 180;

// Content type
header('Content-type: image/jpeg');

// Load
$source = imagecreatefromjpeg($filename);

// Rotate
$rotate = imagerotate($source, $degrees, 0);

// Output
imagejpeg($rotate);

// Free the memory
imagedestroy($source);
imagedestroy($rotate);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagerotate.jpg" width="95" height="51" alt="Output of example : Rotate an image 180 degrees" />

### Notes

> **Note**:
>
> This function is affected by the interpolation method set by <span
> class="function">imagesetinterpolation</span>.

### See Also

-   <span class="function">imagesetinterpolation</span>

imagesavealpha
==============

Whether to retain full alpha channel information when saving PNG images

### Description

<span class="type">bool</span> <span
class="methodname">imagesavealpha</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$saveflag`</span> )

<span class="function">imagesavealpha</span> sets the flag which
determines whether to retain full alpha channel information (as opposed
to single-color transparency) when saving PNG images.

Alphablending has to be disabled (`imagealphablending($im, false)`) to
retain the alpha-channel in the first place.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`saveflag`  
Whether to save the alpha channel or not. Defaults to **`false`**.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Basic <span class="function">imagesavealpha</span> Usage**

``` php
<?php
// Load a png image with alpha channel
$png = imagecreatefrompng('./alphachannel_example.png');

// Turn off alpha blending
imagealphablending($png, false);

// Do desired operations

// Set alpha flag
imagesavealpha($png, true);

// Output image to browser
header('Content-Type: image/png');

imagepng($png);
imagedestroy($png);
?>
```

### See Also

-   <span class="function">imagealphablending</span>

imagescale
==========

Scale an image using the given new width and height

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">imagescale</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$new_width`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$new_height`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = IMG\_BILINEAR\_FIXED</span></span> \]\] )

<span class="function">imagescale</span> scales an image using the given
interpolation algorithm.

> **Note**:
>
> Unlike many of other image functions, <span
> class="function">imagescale</span> does not modify the passed `image`;
> instead, a *new* image is returned.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`new_width`  
The width to scale the image to.

`new_height`  
The height to scale the image to. If omitted or negative, the aspect
ratio will be preserved.

`mode`  
One of **`IMG_NEAREST_NEIGHBOUR`**, **`IMG_BILINEAR_FIXED`**,
**`IMG_BICUBIC`**, **`IMG_BICUBIC_FIXED`** or anything else (will use
two pass).

> **Note**: <span class="simpara"> **`IMG_WEIGHTED4`** is not yet
> supported. </span>

### Return Values

Return the scaled image resource on success or **`false`** on failure.

### See Also

-   <span class="function">imagecopyresized</span>
-   <span class="function">imagecopyresampled</span>

imagesetbrush
=============

Set the brush image for line drawing

### Description

<span class="type">bool</span> <span
class="methodname">imagesetbrush</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$brush`</span> )

<span class="function">imagesetbrush</span> sets the brush image to be
used by all line drawing functions (such as <span
class="function">imageline</span> and <span
class="function">imagepolygon</span>) when drawing with the special
colors **`IMG_COLOR_BRUSHED`** or **`IMG_COLOR_STYLEDBRUSHED`**.

**Caution**

You need not take special action when you are finished with a brush, but
if you destroy the brush image (or let PHP destroy it), you must not use
the **`IMG_COLOR_BRUSHED`** or **`IMG_COLOR_STYLEDBRUSHED`** colors
until you have set a new brush image!

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`brush`  
An image resource.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagesetbrush</span> example**

``` php
<?php
// Load a mini php logo
$php = imagecreatefrompng('./php.png');

// Create the main image, 100x100
$im = imagecreatetruecolor(100, 100);

// Fill the background with white
$white = imagecolorallocate($im, 255, 255, 255);
imagefilledrectangle($im, 0, 0, 299, 99, $white);

// Set the brush
imagesetbrush($im, $php);

// Draw a couple of brushes, each overlaying each
imageline($im, 50, 50, 50, 60, IMG_COLOR_BRUSHED);

// Output image to the browser
header('Content-type: image/png');

imagepng($im);
imagedestroy($im);
imagedestroy($php);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagesetbrush.png" width="100" height="100" alt="Output of example : imagesetbrush()" />

imagesetclip
============

Set the clipping rectangle

### Description

<span class="type">bool</span> <span
class="methodname">imagesetclip</span> ( <span class="methodparam"><span
class="type">resource</span> `$im`</span> , <span
class="methodparam"><span class="type">int</span> `$x1`</span> , <span
class="methodparam"><span class="type">int</span> `$y1`</span> , <span
class="methodparam"><span class="type">int</span> `$x2`</span> , <span
class="methodparam"><span class="type">int</span> `$y2`</span> )

<span class="function">imagesetclip</span> sets the current clipping
rectangle, i.e. the area beyond which no pixels will be drawn.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x1`  
The x-coordinate of the upper left corner.

`y1`  
The y-coordinate of the upper left corner.

`x2`  
The x-coordinate of the lower right corner.

`y2`  
The y-coordinate of the lower right corner.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">imagegetclip</span>

imagesetinterpolation
=====================

Set the interpolation method

### Description

<span class="type">bool</span> <span
class="methodname">imagesetinterpolation</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$method`<span class="initializer"> = IMG\_BILINEAR\_FIXED</span></span>
\] )

Sets the interpolation method, setting an interpolation method affects
the rendering of various functions in GD, such as the <span
class="function">imagerotate</span> function.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`method`  
The interpolation method, which can be one of the following:

-   <span class="simpara"> **`IMG_BELL`**: Bell filter. </span>
-   <span class="simpara"> **`IMG_BESSEL`**: Bessel filter. </span>
-   <span class="simpara"> **`IMG_BICUBIC`**: Bicubic interpolation.
    </span>
-   <span class="simpara"> **`IMG_BICUBIC_FIXED`**: Fixed point
    implementation of the bicubic interpolation. </span>
-   <span class="simpara"> **`IMG_BILINEAR_FIXED`**: Fixed point
    implementation of the bilinear interpolation (*default (also on
    image creation)*). </span>
-   <span class="simpara"> **`IMG_BLACKMAN`**: Blackman window function.
    </span>
-   <span class="simpara"> **`IMG_BOX`**: Box blur filter. </span>
-   <span class="simpara"> **`IMG_BSPLINE`**: Spline interpolation.
    </span>
-   <span class="simpara"> **`IMG_CATMULLROM`**: Cubic Hermite spline
    interpolation. </span>
-   <span class="simpara"> **`IMG_GAUSSIAN`**: Gaussian function.
    </span>
-   <span class="simpara"> **`IMG_GENERALIZED_CUBIC`**: Generalized
    cubic spline fractal interpolation. </span>
-   <span class="simpara"> **`IMG_HERMITE`**: Hermite interpolation.
    </span>
-   <span class="simpara"> **`IMG_HAMMING`**: Hamming filter. </span>
-   <span class="simpara"> **`IMG_HANNING`**: Hanning filter. </span>
-   <span class="simpara"> **`IMG_MITCHELL`**: Mitchell filter. </span>
-   <span class="simpara"> **`IMG_POWER`**: Power interpolation. </span>
-   <span class="simpara"> **`IMG_QUADRATIC`**: Inverse quadratic
    interpolation. </span>
-   <span class="simpara"> **`IMG_SINC`**: Sinc function. </span>
-   <span class="simpara"> **`IMG_NEAREST_NEIGHBOUR`**: Nearest
    neighbour interpolation. </span>
-   <span class="simpara"> **`IMG_WEIGHTED4`**: Weighting filter.
    </span>
-   <span class="simpara"> **`IMG_TRIANGLE`**: Triangle interpolation.
    </span>

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagesetinterpolation</span>
example**

``` php
<?php
// Load an image
$im = imagecreate(500, 500);

// By default interpolation is IMG_BILINEAR_FIXED, switch 
// to use the 'Mitchell' filter:
imagesetinterpolation($im, IMG_MITCHELL);

// Continue to work with $im ...
?>
```

### Notes

Changing the interpolation method affects the following functions when
rendering:

-   <span class="simpara"> <span class="function">imageaffine</span>
    </span>
-   <span class="simpara"> <span class="function">imagerotate</span>
    </span>

### See Also

-   <span class="function">imagegetinterpolation</span>

imagesetpixel
=============

Set a single pixel

### Description

<span class="type">bool</span> <span
class="methodname">imagesetpixel</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

<span class="function">imagesetpixel</span> draws a pixel at the
specified coordinate.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`x`  
x-coordinate.

`y`  
y-coordinate.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagesetpixel</span> example**

A random drawing that ends with a regular picture.

``` php
<?php

$x = 200;
$y = 200;

$gd = imagecreatetruecolor($x, $y);
 
$corners[0] = array('x' => 100, 'y' =>  10);
$corners[1] = array('x' =>   0, 'y' => 190);
$corners[2] = array('x' => 200, 'y' => 190);

$red = imagecolorallocate($gd, 255, 0, 0); 

for ($i = 0; $i < 100000; $i++) {
  imagesetpixel($gd, round($x),round($y), $red);
  $a = rand(0, 2);
  $x = ($x + $corners[$a]['x']) / 2;
  $y = ($y + $corners[$a]['y']) / 2;
}
 
header('Content-Type: image/png');
imagepng($gd);

?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagesetpixel.png" width="200" height="200" alt="Output of example : imagesetpixel()" />

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">imagecolorallocate</span>
-   <span class="function">imagecolorat</span>

imagesetstyle
=============

Set the style for line drawing

### Description

<span class="type">bool</span> <span
class="methodname">imagesetstyle</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">array</span>
`$style`</span> )

<span class="function">imagesetstyle</span> sets the style to be used by
all line drawing functions (such as <span
class="function">imageline</span> and <span
class="function">imagepolygon</span>) when drawing with the special
color **`IMG_COLOR_STYLED`** or lines of images with color
**`IMG_COLOR_STYLEDBRUSHED`**.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`style`  
An array of pixel colors. You can use the **`IMG_COLOR_TRANSPARENT`**
constant to add a transparent pixel. Note that `style` must not be an
empty <span class="type">array</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

Following example script draws a dashed line from upper left to lower
right corner of the canvas:

**Example \#1 <span class="function">imagesetstyle</span> example**

``` php
<?php
header("Content-type: image/jpeg");
$im  = imagecreatetruecolor(100, 100);
$w   = imagecolorallocate($im, 255, 255, 255);
$red = imagecolorallocate($im, 255, 0, 0);

/* Draw a dashed line, 5 red pixels, 5 white pixels */
$style = array($red, $red, $red, $red, $red, $w, $w, $w, $w, $w);
imagesetstyle($im, $style);
imageline($im, 0, 0, 100, 100, IMG_COLOR_STYLED);

/* Draw a line of happy faces using imagesetbrush() with imagesetstyle */
$style = array($w, $w, $w, $w, $w, $w, $w, $w, $w, $w, $w, $w, $red);
imagesetstyle($im, $style);

$brush = imagecreatefrompng("http://www.libpng.org/pub/png/images/smile.happy.png");
$w2 = imagecolorallocate($brush, 255, 255, 255);
imagecolortransparent($brush, $w2);
imagesetbrush($im, $brush);
imageline($im, 100, 0, 0, 100, IMG_COLOR_STYLEDBRUSHED);

imagejpeg($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagesetstyle.jpg" width="100" height="100" alt="Output of example : imagesetstyle()" />

### See Also

-   <span class="function">imagesetbrush</span>
-   <span class="function">imageline</span>

imagesetthickness
=================

Set the thickness for line drawing

### Description

<span class="type">bool</span> <span
class="methodname">imagesetthickness</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span>
`$thickness`</span> )

<span class="function">imagesetthickness</span> sets the thickness of
the lines drawn when drawing rectangles, polygons, arcs etc. to
`thickness` pixels.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`thickness`  
Thickness, in pixels.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagesetthickness</span> example**

``` php
<?php
// Create a 200x100 image
$im = imagecreatetruecolor(200, 100);
$white = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);
$black = imagecolorallocate($im, 0x00, 0x00, 0x00);

// Set the background to be white
imagefilledrectangle($im, 0, 0, 299, 99, $white);

// Set the line thickness to 5
imagesetthickness($im, 5);

// Draw the rectangle
imagerectangle($im, 14, 14, 185, 85, $black);

// Output image to the browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagesetthickness.png" width="200" height="100" alt="Output of example : imagesetthickness()" />

imagesettile
============

Set the tile image for filling

### Description

<span class="type">bool</span> <span
class="methodname">imagesettile</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">resource</span> `$tile`</span> )

<span class="function">imagesettile</span> sets the tile image to be
used by all region filling functions (such as <span
class="function">imagefill</span> and <span
class="function">imagefilledpolygon</span>) when filling with the
special color **`IMG_COLOR_TILED`**.

A tile is an image used to fill an area with a repeated pattern. *Any*
GD image can be used as a tile, and by setting the transparent color
index of the tile image with <span
class="function">imagecolortransparent</span>, a tile allows certain
parts of the underlying area to shine through can be created.

**Caution**

You need not take special action when you are finished with a tile, but
if you destroy the tile image (or let PHP destroy it), you must not use
the **`IMG_COLOR_TILED`** color until you have set a new tile image!

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`tile`  
The image resource to be used as a tile.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagesettile</span> example**

``` php
<?php
// Load an external image
$zend = imagecreatefromgif('./zend.gif');

// Create a 200x200 image
$im = imagecreatetruecolor(200, 200);

// Set the tile
imagesettile($im, $zend);

// Make the image repeat
imagefilledrectangle($im, 0, 0, 199, 199, IMG_COLOR_TILED);

// Output image to the browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
imagedestroy($zend);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagesettile.png" width="200" height="200" alt="Output of example : imagesettile()" />

imagestring
===========

Draw a string horizontally

### Description

<span class="type">bool</span> <span
class="methodname">imagestring</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">int</span> `$font`</span> , <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

Draws a `string` at the given coordinates.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

`x`  
x-coordinate of the upper left corner.

`y`  
y-coordinate of the upper left corner.

`string`  
The string to be written.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagestring</span> example**

``` php
<?php
// Create a 100*30 image
$im = imagecreate(100, 30);

// White background and blue text
$bg = imagecolorallocate($im, 255, 255, 255);
$textcolor = imagecolorallocate($im, 0, 0, 255);

// Write the string at the top left
imagestring($im, 5, 0, 0, 'Hello world!', $textcolor);

// Output the image
header('Content-type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagestring.png" width="100" height="30" alt="Output of example : imagestring()" />

### See Also

-   <span class="function">imagestringup</span>
-   <span class="function">imageloadfont</span>
-   <span class="function">imagettftext</span>

imagestringup
=============

Draw a string vertically

### Description

<span class="type">bool</span> <span
class="methodname">imagestringup</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span> `$font`</span> ,
<span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">string</span>
`$string`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

Draws a `string` vertically at the given coordinates.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

` font`  
Can be 1, 2, 3, 4, 5 for built-in fonts in latin2 encoding (where higher
numbers corresponding to larger fonts) or any of your own font
identifiers registered with <span class="function">imageloadfont</span>.

`x`  
x-coordinate of the bottom left corner.

`y`  
y-coordinate of the bottom left corner.

`string`  
The string to be written.

`color`  
A color identifier created with <span
class="function">imagecolorallocate</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">imagestringup</span> example**

``` php
<?php
// create a 100*100 image
$im = imagecreatetruecolor(100, 100);

// Write the text
$textcolor = imagecolorallocate($im, 0xFF, 0xFF, 0xFF);
imagestringup($im, 3, 40, 80, 'gd library', $textcolor);

// Save the image
imagepng($im, './stringup.png');
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagestringup.png" width="100" height="100" alt="Output of example : imagestringup()" />

### See Also

-   <span class="function">imagestring</span>
-   <span class="function">imageloadfont</span>

imagesx
=======

Get image width

### Description

<span class="type">int</span> <span class="methodname">imagesx</span> (
<span class="methodparam"><span class="type">resource</span>
`$image`</span> )

Returns the width of the given `image` resource.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Return the width of the `image` or **`false`** on errors.

### Examples

**Example \#1 Using <span class="function">imagesx</span>**

``` php
<?php

// create a 300*200 image
$img = imagecreatetruecolor(300, 200);

echo imagesx($img); // 300

?>
```

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">getimagesize</span>
-   <span class="function">imagesy</span>

imagesy
=======

Get image height

### Description

<span class="type">int</span> <span class="methodname">imagesy</span> (
<span class="methodparam"><span class="type">resource</span>
`$image`</span> )

Returns the height of the given `image` resource.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

### Return Values

Return the height of the `image` or **`false`** on errors.

### Examples

**Example \#1 Using <span class="function">imagesy</span>**

``` php
<?php

// create a 300*200 image
$img = imagecreatetruecolor(300, 200);

echo imagesy($img); // 200

?>
```

### See Also

-   <span class="function">imagecreatetruecolor</span>
-   <span class="function">getimagesize</span>
-   <span class="function">imagesx</span>

imagetruecolortopalette
=======================

Convert a true color image to a palette image

### Description

<span class="type">bool</span> <span
class="methodname">imagetruecolortopalette</span> ( <span
class="methodparam"><span class="type">resource</span> `$image`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$dither`</span> , <span class="methodparam"><span
class="type">int</span> `$ncolors`</span> )

<span class="function">imagetruecolortopalette</span> converts a
truecolor image to a palette image. The code for this function was
originally drawn from the Independent JPEG Group library code, which is
excellent. The code has been modified to preserve as much alpha channel
information as possible in the resulting palette, in addition to
preserving colors as well as possible. This does not work as well as
might be hoped. It is usually best to simply produce a truecolor output
image instead, which guarantees the highest output quality.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`dither`  
Indicates if the image should be dithered - if it is **`true`** then
dithering will be used which will result in a more speckled image but
with better color approximation.

`ncolors`  
Sets the maximum number of colors that should be retained in the
palette.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Converting a true color image to a palette-based image**

``` php
<?php
// Create a new true color image
$im = imagecreatetruecolor(100, 100);

// Convert to palette-based with no dithering and 255 colors
imagetruecolortopalette($im, false, 255);

// Save the image
imagepng($im, './paletteimage.png');
imagedestroy($im);
?>
```

imagettfbbox
============

Give the bounding box of a text using TrueType fonts

### Description

<span class="type">array</span> <span
class="methodname">imagettfbbox</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> , <span
class="methodparam"><span class="type">float</span> `$angle`</span> ,
<span class="methodparam"><span class="type">string</span>
`$fontfile`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> )

This function calculates and returns the bounding box in pixels for a
TrueType text.

> **Note**:
>
> <span class="function">imageftbbox</span> is an extended variant of
> <span class="function">imagettfbbox</span> which additionally supports
> the `extrainfo`.

### Parameters

`size`  
The font size in points.

`angle`  
Angle in degrees in which `text` will be measured.

`fontfile`  
The path to the TrueType font you wish to use.

Depending on which version of the GD library PHP is using, *when
`fontfile` does not begin with a leading */* then *.ttf* will be
appended* to the filename and the library will attempt to search for
that filename along a library-defined font path.

When using versions of the GD library lower than 2.0.18, a *space*
character, rather than a semicolon, was used as the 'path separator' for
different font files. Unintentional use of this feature will result in
the warning message: *Warning: Could not find/open font*. For these
affected versions, the only solution is moving the font to a path which
does not contain spaces.

In many cases where a font resides in the same directory as the script
using it the following trick will alleviate any include problems.

``` php
<?php
// Set the environment variable for GD
putenv('GDFONTPATH=' . realpath('.'));

// Name the font to be used (note the lack of the .ttf extension)
$font = 'SomeFont';
?>
```

> **Note**:
>
> Note that
> <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
> does *not* apply to `fontfile`.

`text`  
The string to be measured.

### Return Values

<span class="function">imagettfbbox</span> returns an array with 8
elements representing four points making the bounding box of the text on
success and **`false`** on error.

| key | contents                       |
|-----|--------------------------------|
| 0   | lower left corner, X position  |
| 1   | lower left corner, Y position  |
| 2   | lower right corner, X position |
| 3   | lower right corner, Y position |
| 4   | upper right corner, X position |
| 5   | upper right corner, Y position |
| 6   | upper left corner, X position  |
| 7   | upper left corner, Y position  |

The points are relative to the *text* regardless of the `angle`, so
"upper left" means in the top left-hand corner seeing the text
horizontally.

### Examples

**Example \#1 <span class="function">imagettfbbox</span> example**

``` php
<?php
// Create a 300x150 image
$im = imagecreatetruecolor(300, 150);
$black = imagecolorallocate($im, 0, 0, 0);
$white = imagecolorallocate($im, 255, 255, 255);

// Set the background to be white
imagefilledrectangle($im, 0, 0, 299, 299, $white);

// Path to our font file
$font = './arial.ttf';

// First we create our bounding box for the first text
$bbox = imagettfbbox(10, 45, $font, 'Powered by PHP ' . phpversion());

// This is our cordinates for X and Y
$x = $bbox[0] + (imagesx($im) / 2) - ($bbox[4] / 2) - 25;
$y = $bbox[1] + (imagesy($im) / 2) - ($bbox[5] / 2) - 5;

// Write it
imagettftext($im, 10, 45, $x, $y, $black, $font, 'Powered by PHP ' . phpversion());

// Create the next bounding box for the second text
$bbox = imagettfbbox(10, 45, $font, 'and Zend Engine ' . zend_version());

// Set the cordinates so its next to the first text
$x = $bbox[0] + (imagesx($im) / 2) - ($bbox[4] / 2) + 10;
$y = $bbox[1] + (imagesy($im) / 2) - ($bbox[5] / 2) - 5;

// Write it
imagettftext($im, 10, 45, $x, $y, $black, $font, 'and Zend Engine ' . zend_version());

// Output to browser
header('Content-Type: image/png');

imagepng($im);
imagedestroy($im);
?>
```

### Notes

> **Note**: <span class="simpara">This function is only available if PHP
> is compiled with freetype support (**--with-freetype-dir=DIR**)
> </span>

### See Also

-   <span class="function">imagettftext</span>
-   <span class="function">imageftbbox</span>

imagettftext
============

Write text to the image using TrueType fonts

### Description

<span class="type">array</span> <span
class="methodname">imagettftext</span> ( <span class="methodparam"><span
class="type">resource</span> `$image`</span> , <span
class="methodparam"><span class="type">float</span> `$size`</span> ,
<span class="methodparam"><span class="type">float</span>
`$angle`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> , <span
class="methodparam"><span class="type">string</span> `$fontfile`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> )

Writes the given `text` into the image using TrueType fonts.

> **Note**:
>
> <span class="function">imagefttext</span> is an extended variant of
> <span class="function">imagettftext</span> which additionally supports
> the `extrainfo`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`size`  
The font size in points.

`angle`  
The angle in degrees, with 0 degrees being left-to-right reading text.
Higher values represent a counter-clockwise rotation. For example, a
value of 90 would result in bottom-to-top reading text.

`x`  
The coordinates given by `x` and `y` will define the basepoint of the
first character (roughly the lower-left corner of the character). This
is different from the <span class="function">imagestring</span>, where
`x` and `y` define the upper-left corner of the first character. For
example, "top left" is 0, 0.

`y`  
The y-ordinate. This sets the position of the fonts baseline, not the
very bottom of the character.

`color`  
The color index. Using the negative of a color index has the effect of
turning off antialiasing. See <span
class="function">imagecolorallocate</span>.

`fontfile`  
The path to the TrueType font you wish to use.

Depending on which version of the GD library PHP is using, *when
`fontfile` does not begin with a leading */* then *.ttf* will be
appended* to the filename and the library will attempt to search for
that filename along a library-defined font path.

When using versions of the GD library lower than 2.0.18, a *space*
character, rather than a semicolon, was used as the 'path separator' for
different font files. Unintentional use of this feature will result in
the warning message: *Warning: Could not find/open font*. For these
affected versions, the only solution is moving the font to a path which
does not contain spaces.

In many cases where a font resides in the same directory as the script
using it the following trick will alleviate any include problems.

``` php
<?php
// Set the environment variable for GD
putenv('GDFONTPATH=' . realpath('.'));

// Name the font to be used (note the lack of the .ttf extension)
$font = 'SomeFont';
?>
```

> **Note**:
>
> Note that
> <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
> does *not* apply to `fontfile`.

`text`  
The text string in UTF-8 encoding.

May include decimal numeric character references (of the form: &\#8364;)
to access characters in a font beyond position 127. The hexadecimal
format (like &\#xA9;) is supported. Strings in UTF-8 encoding can be
passed directly.

Named entities, such as &copy;, are not supported. Consider using <span
class="function">html\_entity\_decode</span> to decode these named
entities into UTF-8 strings.

If a character is used in the string which is not supported by the font,
a hollow rectangle will replace the character.

### Return Values

Returns an array with 8 elements representing four points making the
bounding box of the text. The order of the points is lower left, lower
right, upper right, upper left. The points are relative to the text
regardless of the angle, so "upper left" means in the top left-hand
corner when you see the text horizontally. Returns **`false`** on error.

### Examples

**Example \#1 <span class="function">imagettftext</span> example**

This example script will produce a white PNG 400x30 pixels, with the
words "Testing..." in black (with grey shadow), in the font Arial.

``` php
<?php
// Set the content-type
header('Content-Type: image/png');

// Create the image
$im = imagecreatetruecolor(400, 30);

// Create some colors
$white = imagecolorallocate($im, 255, 255, 255);
$grey = imagecolorallocate($im, 128, 128, 128);
$black = imagecolorallocate($im, 0, 0, 0);
imagefilledrectangle($im, 0, 0, 399, 29, $white);

// The text to draw
$text = 'Testing...';
// Replace path by your own font path
$font = 'arial.ttf';

// Add some shadow to the text
imagettftext($im, 20, 0, 11, 21, $grey, $font, $text);

// Add the text
imagettftext($im, 20, 0, 10, 20, $black, $font, $text);

// Using imagepng() results in clearer text compared with imagejpeg()
imagepng($im);
imagedestroy($im);
?>
```

The above example will output something similar to:

<img src="images/21009b70229598c6a80eef8b45bf282b-imagettftext.png" width="400" height="30" alt="Output of example : imagettftext()" />

### Notes

> **Note**: <span class="simpara">This function is only available if PHP
> is compiled with freetype support (**--with-freetype-dir=DIR**)
> </span>

### See Also

-   <span class="function">imagettfbbox</span>
-   <span class="function">imagefttext</span>

imagetypes
==========

Return the image types supported by this PHP build

### Description

<span class="type">int</span> <span class="methodname">imagetypes</span>
( <span class="methodparam">void</span> )

Returns the image types supported by the current PHP installation.

### Return Values

Returns a bit-field corresponding to the image formats supported by the
version of GD linked into PHP. The following bits are returned,
**`IMG_BMP`** \| **`IMG_GIF`** \| **`IMG_JPG`** \| **`IMG_PNG`** \|
**`IMG_WBMP`** \| **`IMG_XPM`** \| **`IMG_WEBP`**.

### Examples

**Example \#1 Checking for PNG support**

``` php
<?php
if (imagetypes() & IMG_PNG) {
    echo "PNG Support is enabled";
}
?>
```

### Changelog

| Version | Description           |
|---------|-----------------------|
| 7.2.0   | **`IMG_BMP`** added.  |
| 7.0.10  | **`IMG_WEBP`** added. |

### See Also

-   <span class="function">gd\_info</span>

imagewbmp
=========

Output image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagewbmp</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$foreground`</span> \]\] )

<span class="function">imagewbmp</span> outputs or save a WBMP version
of the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

`foreground`  
You can set the foreground color with this parameter by setting an
identifier obtained from <span
class="function">imagecolorallocate</span>. The default foreground color
is black.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Outputting a WBMP image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Set the content type header - in this case image/vnd.wap.wbmp
// Hint: see image_type_to_mime_type() for content-types
header('Content-Type: image/vnd.wap.wbmp');

// Output the image
imagewbmp($im);

// Free up memory
imagedestroy($im);
?>
```

**Example \#2 Saving the WBMP image**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Save the image
imagewbmp($im, 'simpletext.wbmp');

// Free up memory
imagedestroy($im);
?>
```

**Example \#3 Outputting the image with a different foreground**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Set the content type header - in this case image/vnd.wap.wbmp
// Hint: see image_type_to_mime_type() for content-types
header('Content-Type: image/vnd.wap.wbmp');

// Set a replacement foreground color
$foreground_color = imagecolorallocate($im, 255, 0, 0);

imagewbmp($im, NULL, $foreground_color);

// Free up memory
imagedestroy($im);
?>
```

### See Also

-   <span class="function">image2wbmp</span>
-   <span class="function">imagepng</span>
-   <span class="function">imagegif</span>
-   <span class="function">imagejpeg</span>
-   <span class="function">imagetypes</span>

imagewebp
=========

Output a WebP image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagewebp</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$to`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$quality`<span class="initializer"> =
80</span></span> \]\] )

Outputs or saves a WebP version of the given `image`.

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`to`  
The path or an open stream resource (which is automatically being closed
after this function returns) to save the file to. If not set or
**`null`**, the raw image stream will be outputted directly.

`quality`  
`quality` ranges from 0 (worst quality, smaller file) to 100 (best
quality, biggest file).

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 Saving an WebP file**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);

imagestring($im, 1, 5, 5,  'WebP with PHP', $text_color);

// Save the image
imagewebp($im, 'php.webp');

// Free up memory
imagedestroy($im);
?>
```

imagexbm
========

Output an XBM image to browser or file

### Description

<span class="type">bool</span> <span class="methodname">imagexbm</span>
( <span class="methodparam"><span class="type">resource</span>
`$image`</span> , <span class="methodparam"><span
class="type">mixed</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">int</span> `$foreground`</span>
\] )

Outputs or save an XBM version of the given `image`.

> **Note**: <span class="simpara"> <span
> class="function">imagexbm</span> doesn't apply any padding, so the
> image width has to be a multiple of 8. This restriction does no longer
> apply as of PHP 7.0.9. </span>

### Parameters

` image`  
An image resource, returned by one of the image creation functions, such
as <span class="function">imagecreatetruecolor</span>.

`filename`  
The path to save the file to, given as <span class="type">string</span>.
If **`null`**, the raw image stream will be output directly.

The `filename` (without the .xbm extension) is also used for the C
identifiers of the XBM, whereby non alphanumeric characters of the
current locale are substituted by underscores. If `filename` is set to
**`null`**, *image* is used to build the C identifiers.

`foreground`  
You can set the foreground color with this parameter by setting an
identifier obtained from <span
class="function">imagecolorallocate</span>. The default foreground color
is black. All other colors are treated as background.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Changelog

| Version | Description                                               |
|---------|-----------------------------------------------------------|
| 8.0.0   | The fourth parameter, which was unused, has been removed. |

### Examples

**Example \#1 Saving an XBM file**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Save the image
imagexbm($im, 'simpletext.xbm');

// Free up memory
imagedestroy($im);
?>
```

**Example \#2 Saving an XBM file with a different foreground color**

``` php
<?php
// Create a blank image and add some text
$im = imagecreatetruecolor(120, 20);
$text_color = imagecolorallocate($im, 233, 14, 91);
imagestring($im, 1, 5, 5,  'A Simple Text String', $text_color);

// Set a replacement foreground color
$foreground_color = imagecolorallocate($im, 255, 0, 0);

// Save the image
imagexbm($im, NULL, $foreground_color);

// Free up memory
imagedestroy($im);
?>
```

### Notes

iptcembed
=========

Embeds binary IPTC data into a JPEG image

### Description

<span class="type">mixed</span> <span
class="methodname">iptcembed</span> ( <span class="methodparam"><span
class="type">string</span> `$iptcdata`</span> , <span
class="methodparam"><span class="type">string</span>
`$jpeg_file_name`</span> \[, <span class="methodparam"><span
class="type">int</span> `$spool`<span class="initializer"> =
0</span></span> \] )

Embeds binary IPTC data into a JPEG image.

### Parameters

`iptcdata`  
The data to be written.

`jpeg_file_name`  
Path to the JPEG image.

`spool`  
Spool flag. If the spool flag is less than 2 then the JPEG will be
returned as a string. Otherwise the JPEG will be printed to STDOUT.

### Return Values

If `spool` is less than 2, the JPEG will be returned, or **`false`** on
failure. Otherwise returns **`true`** on success or **`false`** on
failure.

### Examples

**Example \#1 Embedding IPTC data into a JPEG**

``` php
<?php

// iptc_make_tag() function by Thies C. Arntzen
function iptc_make_tag($rec, $data, $value)
{
    $length = strlen($value);
    $retval = chr(0x1C) . chr($rec) . chr($data);

    if($length < 0x8000)
    {
        $retval .= chr($length >> 8) .  chr($length & 0xFF);
    }
    else
    {
        $retval .= chr(0x80) . 
                   chr(0x04) . 
                   chr(($length >> 24) & 0xFF) . 
                   chr(($length >> 16) & 0xFF) . 
                   chr(($length >> 8) & 0xFF) . 
                   chr($length & 0xFF);
    }

    return $retval . $value;
}

// Path to jpeg file
$path = './phplogo.jpg';

// Set the IPTC tags
$iptc = array(
    '2#120' => 'Test image',
    '2#116' => 'Copyright 2008-2009, The PHP Group'
);

// Convert the IPTC tags into binary code
$data = '';

foreach($iptc as $tag => $string)
{
    $tag = substr($tag, 2);
    $data .= iptc_make_tag(2, $tag, $string);
}

// Embed the IPTC data
$content = iptcembed($data, $path);

// Write the new image data out to the file.
$fp = fopen($path, "wb");
fwrite($fp, $content);
fclose($fp);
?>
```

### Notes

> **Note**:
>
> This function does not require the GD image library.

iptcparse
=========

Parse a binary IPTC block into single tags

### Description

<span class="type">array</span> <span
class="methodname">iptcparse</span> ( <span class="methodparam"><span
class="type">string</span> `$iptcblock`</span> )

Parses an
<a href="http://www.iptc.org/" class="link external">» IPTC</a> block
into its single tags.

### Parameters

`iptcblock`  
A binary IPTC block.

### Return Values

Returns an array using the tagmarker as an index and the value as the
value. It returns **`false`** on error or if no IPTC data was found.

### Examples

**Example \#1 iptcparse() used together with <span
class="function">getimagesize</span>**

``` php
<?php
$size = getimagesize('./test.jpg', $info);
if(isset($info['APP13']))
{
    $iptc = iptcparse($info['APP13']);
    var_dump($iptc);
}
?>
```

### Notes

> **Note**:
>
> This function does not require the GD image library.

jpeg2wbmp
=========

Convert JPEG image file to WBMP image file

**Warning**

<span class="function">jpeg2wbmp</span> has been deprecated as of PHP
7.2.0, and will be removed as of PHP 8.0.0. Use <span
class="function">imagecreatefromjpeg</span> and <span
class="function">imagewbmp</span> instead.

### Description

<span class="type">bool</span> <span class="methodname">jpeg2wbmp</span>
( <span class="methodparam"><span class="type">string</span>
`$jpegname`</span> , <span class="methodparam"><span
class="type">string</span> `$wbmpname`</span> , <span
class="methodparam"><span class="type">int</span> `$dest_height`</span>
, <span class="methodparam"><span class="type">int</span>
`$dest_width`</span> , <span class="methodparam"><span
class="type">int</span> `$threshold`</span> )

Converts a JPEG file into a WBMP file.

### Parameters

`jpegname`  
Path to JPEG file.

`wbmpname`  
Path to destination WBMP file.

`dest_height`  
Destination image height.

`dest_width`  
Destination image width.

`threshold`  
Threshold value, between 0 and 8 (inclusive).

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 <span class="function">jpeg2wbmp</span> example**

``` php
<?php
// Path to the target jpeg
$path = './test.jpg';

// Get the image sizes
$image = getimagesize($path);

// Convert image
jpeg2wbmp($path, './test.wbmp', $image[1], $image[0], 5);
?>
```

### See Also

-   <span class="function">png2wbmp</span>

png2wbmp
========

Convert PNG image file to WBMP image file

**Warning**

<span class="function">png2wbmp</span> has been deprecated as of PHP
7.2.0, and will be removed as of PHP 8.0.0. Use <span
class="function">imagecreatefrompng</span> and <span
class="function">imagewbmp</span> instead.

### Description

<span class="type">bool</span> <span class="methodname">png2wbmp</span>
( <span class="methodparam"><span class="type">string</span>
`$pngname`</span> , <span class="methodparam"><span
class="type">string</span> `$wbmpname`</span> , <span
class="methodparam"><span class="type">int</span> `$dest_height`</span>
, <span class="methodparam"><span class="type">int</span>
`$dest_width`</span> , <span class="methodparam"><span
class="type">int</span> `$threshold`</span> )

Converts a PNG file into a WBMP file.

### Parameters

`pngname`  
Path to PNG file.

`wbmpname`  
Path to destination WBMP file.

`dest_height`  
Destination image height.

`dest_width`  
Destination image width.

`threshold`  
Threshold value, between 0 and 8 (inclusive).

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Caution**

However, if libgd fails to output the image, this function returns
**`true`**.

### Examples

**Example \#1 <span class="function">png2wbmp</span> example**

``` php
<?php
// Path to the target png
$path = './test.png';

// Get the image sizes
$image = getimagesize($path);

// Convert image
png2wbmp($path, './test.wbmp', $image[1], $image[0], 7);
?>
```

### See Also

-   <span class="function">jpeg2wbmp</span>

**Table of Contents**

-   [gd\_info](/ref/image.html#gd_info) — Retrieve information about the
    currently installed GD library
-   [getimagesize](/ref/image.html#getimagesize) — Get the size of an
    image
-   [getimagesizefromstring](/ref/image.html#getimagesizefromstring) —
    Get the size of an image from a string
-   [image\_type\_to\_extension](/ref/image.html#image_type_to_extension)
    — Get file extension for image type
-   [image\_type\_to\_mime\_type](/ref/image.html#image_type_to_mime_type)
    — Get Mime-Type for image-type returned by getimagesize,
    exif\_read\_data, exif\_thumbnail, exif\_imagetype
-   [image2wbmp](/ref/image.html#image2wbmp) — Output image to browser
    or file
-   [imageaffine](/ref/image.html#imageaffine) — Return an image
    containing the affine transformed src image, using an optional
    clipping area
-   [imageaffinematrixconcat](/ref/image.html#imageaffinematrixconcat) —
    Concatenate two affine transformation matrices
-   [imageaffinematrixget](/ref/image.html#imageaffinematrixget) — Get
    an affine transformation matrix
-   [imagealphablending](/ref/image.html#imagealphablending) — Set the
    blending mode for an image
-   [imageantialias](/ref/image.html#imageantialias) — Should antialias
    functions be used or not
-   [imagearc](/ref/image.html#imagearc) — Draws an arc
-   [imagebmp](/ref/image.html#imagebmp) — Output a BMP image to browser
    or file
-   [imagechar](/ref/image.html#imagechar) — Draw a character
    horizontally
-   [imagecharup](/ref/image.html#imagecharup) — Draw a character
    vertically
-   [imagecolorallocate](/ref/image.html#imagecolorallocate) — Allocate
    a color for an image
-   [imagecolorallocatealpha](/ref/image.html#imagecolorallocatealpha) —
    Allocate a color for an image
-   [imagecolorat](/ref/image.html#imagecolorat) — Get the index of the
    color of a pixel
-   [imagecolorclosest](/ref/image.html#imagecolorclosest) — Get the
    index of the closest color to the specified color
-   [imagecolorclosestalpha](/ref/image.html#imagecolorclosestalpha) —
    Get the index of the closest color to the specified color + alpha
-   [imagecolorclosesthwb](/ref/image.html#imagecolorclosesthwb) — Get
    the index of the color which has the hue, white and blackness
-   [imagecolordeallocate](/ref/image.html#imagecolordeallocate) —
    De-allocate a color for an image
-   [imagecolorexact](/ref/image.html#imagecolorexact) — Get the index
    of the specified color
-   [imagecolorexactalpha](/ref/image.html#imagecolorexactalpha) — Get
    the index of the specified color + alpha
-   [imagecolormatch](/ref/image.html#imagecolormatch) — Makes the
    colors of the palette version of an image more closely match the
    true color version
-   [imagecolorresolve](/ref/image.html#imagecolorresolve) — Get the
    index of the specified color or its closest possible alternative
-   [imagecolorresolvealpha](/ref/image.html#imagecolorresolvealpha) —
    Get the index of the specified color + alpha or its closest possible
    alternative
-   [imagecolorset](/ref/image.html#imagecolorset) — Set the color for
    the specified palette index
-   [imagecolorsforindex](/ref/image.html#imagecolorsforindex) — Get the
    colors for an index
-   [imagecolorstotal](/ref/image.html#imagecolorstotal) — Find out the
    number of colors in an image's palette
-   [imagecolortransparent](/ref/image.html#imagecolortransparent) —
    Define a color as transparent
-   [imageconvolution](/ref/image.html#imageconvolution) — Apply a 3x3
    convolution matrix, using coefficient and offset
-   [imagecopy](/ref/image.html#imagecopy) — Copy part of an image
-   [imagecopymerge](/ref/image.html#imagecopymerge) — Copy and merge
    part of an image
-   [imagecopymergegray](/ref/image.html#imagecopymergegray) — Copy and
    merge part of an image with gray scale
-   [imagecopyresampled](/ref/image.html#imagecopyresampled) — Copy and
    resize part of an image with resampling
-   [imagecopyresized](/ref/image.html#imagecopyresized) — Copy and
    resize part of an image
-   [imagecreate](/ref/image.html#imagecreate) — Create a new palette
    based image
-   [imagecreatefrombmp](/ref/image.html#imagecreatefrombmp) — Create a
    new image from file or URL
-   [imagecreatefromgd2](/ref/image.html#imagecreatefromgd2) — Create a
    new image from GD2 file or URL
-   [imagecreatefromgd2part](/ref/image.html#imagecreatefromgd2part) —
    Create a new image from a given part of GD2 file or URL
-   [imagecreatefromgd](/ref/image.html#imagecreatefromgd) — Create a
    new image from GD file or URL
-   [imagecreatefromgif](/ref/image.html#imagecreatefromgif) — Create a
    new image from file or URL
-   [imagecreatefromjpeg](/ref/image.html#imagecreatefromjpeg) — Create
    a new image from file or URL
-   [imagecreatefrompng](/ref/image.html#imagecreatefrompng) — Create a
    new image from file or URL
-   [imagecreatefromstring](/ref/image.html#imagecreatefromstring) —
    Create a new image from the image stream in the string
-   [imagecreatefromwbmp](/ref/image.html#imagecreatefromwbmp) — Create
    a new image from file or URL
-   [imagecreatefromwebp](/ref/image.html#imagecreatefromwebp) — Create
    a new image from file or URL
-   [imagecreatefromxbm](/ref/image.html#imagecreatefromxbm) — Create a
    new image from file or URL
-   [imagecreatefromxpm](/ref/image.html#imagecreatefromxpm) — Create a
    new image from file or URL
-   [imagecreatetruecolor](/ref/image.html#imagecreatetruecolor) —
    Create a new true color image
-   [imagecrop](/ref/image.html#imagecrop) — Crop an image to the given
    rectangle
-   [imagecropauto](/ref/image.html#imagecropauto) — Crop an image
    automatically using one of the available modes
-   [imagedashedline](/ref/image.html#imagedashedline) — Draw a dashed
    line
-   [imagedestroy](/ref/image.html#imagedestroy) — Destroy an image
-   [imageellipse](/ref/image.html#imageellipse) — Draw an ellipse
-   [imagefill](/ref/image.html#imagefill) — Flood fill
-   [imagefilledarc](/ref/image.html#imagefilledarc) — Draw a partial
    arc and fill it
-   [imagefilledellipse](/ref/image.html#imagefilledellipse) — Draw a
    filled ellipse
-   [imagefilledpolygon](/ref/image.html#imagefilledpolygon) — Draw a
    filled polygon
-   [imagefilledrectangle](/ref/image.html#imagefilledrectangle) — Draw
    a filled rectangle
-   [imagefilltoborder](/ref/image.html#imagefilltoborder) — Flood fill
    to specific color
-   [imagefilter](/ref/image.html#imagefilter) — Applies a filter to an
    image
-   [imageflip](/ref/image.html#imageflip) — Flips an image using a
    given mode
-   [imagefontheight](/ref/image.html#imagefontheight) — Get font height
-   [imagefontwidth](/ref/image.html#imagefontwidth) — Get font width
-   [imageftbbox](/ref/image.html#imageftbbox) — Give the bounding box
    of a text using fonts via freetype2
-   [imagefttext](/ref/image.html#imagefttext) — Write text to the image
    using fonts using FreeType 2
-   [imagegammacorrect](/ref/image.html#imagegammacorrect) — Apply a
    gamma correction to a GD image
-   [imagegd2](/ref/image.html#imagegd2) — Output GD2 image to browser
    or file
-   [imagegd](/ref/image.html#imagegd) — Output GD image to browser or
    file
-   [imagegetclip](/ref/image.html#imagegetclip) — Get the clipping
    rectangle
-   [imagegetinterpolation](/ref/image.html#imagegetinterpolation) — Get
    the interpolation method
-   [imagegif](/ref/image.html#imagegif) — Output image to browser or
    file
-   [imagegrabscreen](/ref/image.html#imagegrabscreen) — Captures the
    whole screen
-   [imagegrabwindow](/ref/image.html#imagegrabwindow) — Captures a
    window
-   [imageinterlace](/ref/image.html#imageinterlace) — Enable or disable
    interlace
-   [imageistruecolor](/ref/image.html#imageistruecolor) — Finds whether
    an image is a truecolor image
-   [imagejpeg](/ref/image.html#imagejpeg) — Output image to browser or
    file
-   [imagelayereffect](/ref/image.html#imagelayereffect) — Set the alpha
    blending flag to use layering effects
-   [imageline](/ref/image.html#imageline) — Draw a line
-   [imageloadfont](/ref/image.html#imageloadfont) — Load a new font
-   [imageopenpolygon](/ref/image.html#imageopenpolygon) — Draws an open
    polygon
-   [imagepalettecopy](/ref/image.html#imagepalettecopy) — Copy the
    palette from one image to another
-   [imagepalettetotruecolor](/ref/image.html#imagepalettetotruecolor) —
    Converts a palette based image to true color
-   [imagepng](/ref/image.html#imagepng) — Output a PNG image to either
    the browser or a file
-   [imagepolygon](/ref/image.html#imagepolygon) — Draws a polygon
-   [imagerectangle](/ref/image.html#imagerectangle) — Draw a rectangle
-   [imageresolution](/ref/image.html#imageresolution) — Get or set the
    resolution of the image
-   [imagerotate](/ref/image.html#imagerotate) — Rotate an image with a
    given angle
-   [imagesavealpha](/ref/image.html#imagesavealpha) — Whether to retain
    full alpha channel information when saving PNG images
-   [imagescale](/ref/image.html#imagescale) — Scale an image using the
    given new width and height
-   [imagesetbrush](/ref/image.html#imagesetbrush) — Set the brush image
    for line drawing
-   [imagesetclip](/ref/image.html#imagesetclip) — Set the clipping
    rectangle
-   [imagesetinterpolation](/ref/image.html#imagesetinterpolation) — Set
    the interpolation method
-   [imagesetpixel](/ref/image.html#imagesetpixel) — Set a single pixel
-   [imagesetstyle](/ref/image.html#imagesetstyle) — Set the style for
    line drawing
-   [imagesetthickness](/ref/image.html#imagesetthickness) — Set the
    thickness for line drawing
-   [imagesettile](/ref/image.html#imagesettile) — Set the tile image
    for filling
-   [imagestring](/ref/image.html#imagestring) — Draw a string
    horizontally
-   [imagestringup](/ref/image.html#imagestringup) — Draw a string
    vertically
-   [imagesx](/ref/image.html#imagesx) — Get image width
-   [imagesy](/ref/image.html#imagesy) — Get image height
-   [imagetruecolortopalette](/ref/image.html#imagetruecolortopalette) —
    Convert a true color image to a palette image
-   [imagettfbbox](/ref/image.html#imagettfbbox) — Give the bounding box
    of a text using TrueType fonts
-   [imagettftext](/ref/image.html#imagettftext) — Write text to the
    image using TrueType fonts
-   [imagetypes](/ref/image.html#imagetypes) — Return the image types
    supported by this PHP build
-   [imagewbmp](/ref/image.html#imagewbmp) — Output image to browser or
    file
-   [imagewebp](/ref/image.html#imagewebp) — Output a WebP image to
    browser or file
-   [imagexbm](/ref/image.html#imagexbm) — Output an XBM image to
    browser or file
-   [iptcembed](/ref/image.html#iptcembed) — Embeds binary IPTC data
    into a JPEG image
-   [iptcparse](/ref/image.html#iptcparse) — Parse a binary IPTC block
    into single tags
-   [jpeg2wbmp](/ref/image.html#jpeg2wbmp) — Convert JPEG image file to
    WBMP image file
-   [png2wbmp](/ref/image.html#png2wbmp) — Convert PNG image file to
    WBMP image file
