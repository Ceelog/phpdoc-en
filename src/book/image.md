Image Processing and GD
=======================

**Table of Contents**

-   [Introduction](/intro/image.html)
-   [Installing/Configuring](/image/setup.html)
    -   [Requirements](/image/setup.html#Requirements)
    -   [Installation](/image/setup.html#Installation)
    -   [Runtime
        Configuration](/image/setup.html#Runtime%20Configuration)
    -   [Resource Types](/image/setup.html#Resource%20Types)
-   [Predefined Constants](/image/constants.html)
-   [Examples](/image/examples.html)
    -   [PNG creation with
        PHP](/image/examples.html#PNG%20creation%20with%20PHP)
    -   [Adding watermarks to images using alpha
        channels](/image/examples.html#Adding%20watermarks%20to%20images%20using%20alpha%20channels)
    -   [Using imagecopymerge to create a translucent
        watermark](/image/examples.html#Using%20imagecopymerge%20to%20create%20a%20translucent%20watermark)
-   [GD and Image Functions](/ref/image.html)
    -   [gd\_info](/ref/image.html#gd_info) — Retrieve information about
        the currently installed GD library
    -   [getimagesize](/ref/image.html#getimagesize) — Get the size of
        an image
    -   [getimagesizefromstring](/ref/image.html#getimagesizefromstring)
        — Get the size of an image from a string
    -   [image\_type\_to\_extension](/ref/image.html#image_type_to_extension)
        — Get file extension for image type
    -   [image\_type\_to\_mime\_type](/ref/image.html#image_type_to_mime_type)
        — Get Mime-Type for image-type returned by getimagesize,
        exif\_read\_data, exif\_thumbnail, exif\_imagetype
    -   [image2wbmp](/ref/image.html#image2wbmp) — Output image to
        browser or file
    -   [imageaffine](/ref/image.html#imageaffine) — Return an image
        containing the affine transformed src image, using an optional
        clipping area
    -   [imageaffinematrixconcat](/ref/image.html#imageaffinematrixconcat)
        — Concatenate two affine transformation matrices
    -   [imageaffinematrixget](/ref/image.html#imageaffinematrixget) —
        Get an affine transformation matrix
    -   [imagealphablending](/ref/image.html#imagealphablending) — Set
        the blending mode for an image
    -   [imageantialias](/ref/image.html#imageantialias) — Should
        antialias functions be used or not
    -   [imagearc](/ref/image.html#imagearc) — Draws an arc
    -   [imagebmp](/ref/image.html#imagebmp) — Output a BMP image to
        browser or file
    -   [imagechar](/ref/image.html#imagechar) — Draw a character
        horizontally
    -   [imagecharup](/ref/image.html#imagecharup) — Draw a character
        vertically
    -   [imagecolorallocate](/ref/image.html#imagecolorallocate) —
        Allocate a color for an image
    -   [imagecolorallocatealpha](/ref/image.html#imagecolorallocatealpha)
        — Allocate a color for an image
    -   [imagecolorat](/ref/image.html#imagecolorat) — Get the index of
        the color of a pixel
    -   [imagecolorclosest](/ref/image.html#imagecolorclosest) — Get the
        index of the closest color to the specified color
    -   [imagecolorclosestalpha](/ref/image.html#imagecolorclosestalpha)
        — Get the index of the closest color to the specified color +
        alpha
    -   [imagecolorclosesthwb](/ref/image.html#imagecolorclosesthwb) —
        Get the index of the color which has the hue, white and
        blackness
    -   [imagecolordeallocate](/ref/image.html#imagecolordeallocate) —
        De-allocate a color for an image
    -   [imagecolorexact](/ref/image.html#imagecolorexact) — Get the
        index of the specified color
    -   [imagecolorexactalpha](/ref/image.html#imagecolorexactalpha) —
        Get the index of the specified color + alpha
    -   [imagecolormatch](/ref/image.html#imagecolormatch) — Makes the
        colors of the palette version of an image more closely match the
        true color version
    -   [imagecolorresolve](/ref/image.html#imagecolorresolve) — Get the
        index of the specified color or its closest possible alternative
    -   [imagecolorresolvealpha](/ref/image.html#imagecolorresolvealpha)
        — Get the index of the specified color + alpha or its closest
        possible alternative
    -   [imagecolorset](/ref/image.html#imagecolorset) — Set the color
        for the specified palette index
    -   [imagecolorsforindex](/ref/image.html#imagecolorsforindex) — Get
        the colors for an index
    -   [imagecolorstotal](/ref/image.html#imagecolorstotal) — Find out
        the number of colors in an image's palette
    -   [imagecolortransparent](/ref/image.html#imagecolortransparent) —
        Define a color as transparent
    -   [imageconvolution](/ref/image.html#imageconvolution) — Apply a
        3x3 convolution matrix, using coefficient and offset
    -   [imagecopy](/ref/image.html#imagecopy) — Copy part of an image
    -   [imagecopymerge](/ref/image.html#imagecopymerge) — Copy and
        merge part of an image
    -   [imagecopymergegray](/ref/image.html#imagecopymergegray) — Copy
        and merge part of an image with gray scale
    -   [imagecopyresampled](/ref/image.html#imagecopyresampled) — Copy
        and resize part of an image with resampling
    -   [imagecopyresized](/ref/image.html#imagecopyresized) — Copy and
        resize part of an image
    -   [imagecreate](/ref/image.html#imagecreate) — Create a new
        palette based image
    -   [imagecreatefrombmp](/ref/image.html#imagecreatefrombmp) —
        Create a new image from file or URL
    -   [imagecreatefromgd2](/ref/image.html#imagecreatefromgd2) —
        Create a new image from GD2 file or URL
    -   [imagecreatefromgd2part](/ref/image.html#imagecreatefromgd2part)
        — Create a new image from a given part of GD2 file or URL
    -   [imagecreatefromgd](/ref/image.html#imagecreatefromgd) — Create
        a new image from GD file or URL
    -   [imagecreatefromgif](/ref/image.html#imagecreatefromgif) —
        Create a new image from file or URL
    -   [imagecreatefromjpeg](/ref/image.html#imagecreatefromjpeg) —
        Create a new image from file or URL
    -   [imagecreatefrompng](/ref/image.html#imagecreatefrompng) —
        Create a new image from file or URL
    -   [imagecreatefromstring](/ref/image.html#imagecreatefromstring) —
        Create a new image from the image stream in the string
    -   [imagecreatefromwbmp](/ref/image.html#imagecreatefromwbmp) —
        Create a new image from file or URL
    -   [imagecreatefromwebp](/ref/image.html#imagecreatefromwebp) —
        Create a new image from file or URL
    -   [imagecreatefromxbm](/ref/image.html#imagecreatefromxbm) —
        Create a new image from file or URL
    -   [imagecreatefromxpm](/ref/image.html#imagecreatefromxpm) —
        Create a new image from file or URL
    -   [imagecreatetruecolor](/ref/image.html#imagecreatetruecolor) —
        Create a new true color image
    -   [imagecrop](/ref/image.html#imagecrop) — Crop an image to the
        given rectangle
    -   [imagecropauto](/ref/image.html#imagecropauto) — Crop an image
        automatically using one of the available modes
    -   [imagedashedline](/ref/image.html#imagedashedline) — Draw a
        dashed line
    -   [imagedestroy](/ref/image.html#imagedestroy) — Destroy an image
    -   [imageellipse](/ref/image.html#imageellipse) — Draw an ellipse
    -   [imagefill](/ref/image.html#imagefill) — Flood fill
    -   [imagefilledarc](/ref/image.html#imagefilledarc) — Draw a
        partial arc and fill it
    -   [imagefilledellipse](/ref/image.html#imagefilledellipse) — Draw
        a filled ellipse
    -   [imagefilledpolygon](/ref/image.html#imagefilledpolygon) — Draw
        a filled polygon
    -   [imagefilledrectangle](/ref/image.html#imagefilledrectangle) —
        Draw a filled rectangle
    -   [imagefilltoborder](/ref/image.html#imagefilltoborder) — Flood
        fill to specific color
    -   [imagefilter](/ref/image.html#imagefilter) — Applies a filter to
        an image
    -   [imageflip](/ref/image.html#imageflip) — Flips an image using a
        given mode
    -   [imagefontheight](/ref/image.html#imagefontheight) — Get font
        height
    -   [imagefontwidth](/ref/image.html#imagefontwidth) — Get font
        width
    -   [imageftbbox](/ref/image.html#imageftbbox) — Give the bounding
        box of a text using fonts via freetype2
    -   [imagefttext](/ref/image.html#imagefttext) — Write text to the
        image using fonts using FreeType 2
    -   [imagegammacorrect](/ref/image.html#imagegammacorrect) — Apply a
        gamma correction to a GD image
    -   [imagegd2](/ref/image.html#imagegd2) — Output GD2 image to
        browser or file
    -   [imagegd](/ref/image.html#imagegd) — Output GD image to browser
        or file
    -   [imagegetclip](/ref/image.html#imagegetclip) — Get the clipping
        rectangle
    -   [imagegetinterpolation](/ref/image.html#imagegetinterpolation) —
        Get the interpolation method
    -   [imagegif](/ref/image.html#imagegif) — Output image to browser
        or file
    -   [imagegrabscreen](/ref/image.html#imagegrabscreen) — Captures
        the whole screen
    -   [imagegrabwindow](/ref/image.html#imagegrabwindow) — Captures a
        window
    -   [imageinterlace](/ref/image.html#imageinterlace) — Enable or
        disable interlace
    -   [imageistruecolor](/ref/image.html#imageistruecolor) — Finds
        whether an image is a truecolor image
    -   [imagejpeg](/ref/image.html#imagejpeg) — Output image to browser
        or file
    -   [imagelayereffect](/ref/image.html#imagelayereffect) — Set the
        alpha blending flag to use layering effects
    -   [imageline](/ref/image.html#imageline) — Draw a line
    -   [imageloadfont](/ref/image.html#imageloadfont) — Load a new font
    -   [imageopenpolygon](/ref/image.html#imageopenpolygon) — Draws an
        open polygon
    -   [imagepalettecopy](/ref/image.html#imagepalettecopy) — Copy the
        palette from one image to another
    -   [imagepalettetotruecolor](/ref/image.html#imagepalettetotruecolor)
        — Converts a palette based image to true color
    -   [imagepng](/ref/image.html#imagepng) — Output a PNG image to
        either the browser or a file
    -   [imagepolygon](/ref/image.html#imagepolygon) — Draws a polygon
    -   [imagerectangle](/ref/image.html#imagerectangle) — Draw a
        rectangle
    -   [imageresolution](/ref/image.html#imageresolution) — Get or set
        the resolution of the image
    -   [imagerotate](/ref/image.html#imagerotate) — Rotate an image
        with a given angle
    -   [imagesavealpha](/ref/image.html#imagesavealpha) — Whether to
        retain full alpha channel information when saving PNG images
    -   [imagescale](/ref/image.html#imagescale) — Scale an image using
        the given new width and height
    -   [imagesetbrush](/ref/image.html#imagesetbrush) — Set the brush
        image for line drawing
    -   [imagesetclip](/ref/image.html#imagesetclip) — Set the clipping
        rectangle
    -   [imagesetinterpolation](/ref/image.html#imagesetinterpolation) —
        Set the interpolation method
    -   [imagesetpixel](/ref/image.html#imagesetpixel) — Set a single
        pixel
    -   [imagesetstyle](/ref/image.html#imagesetstyle) — Set the style
        for line drawing
    -   [imagesetthickness](/ref/image.html#imagesetthickness) — Set the
        thickness for line drawing
    -   [imagesettile](/ref/image.html#imagesettile) — Set the tile
        image for filling
    -   [imagestring](/ref/image.html#imagestring) — Draw a string
        horizontally
    -   [imagestringup](/ref/image.html#imagestringup) — Draw a string
        vertically
    -   [imagesx](/ref/image.html#imagesx) — Get image width
    -   [imagesy](/ref/image.html#imagesy) — Get image height
    -   [imagetruecolortopalette](/ref/image.html#imagetruecolortopalette)
        — Convert a true color image to a palette image
    -   [imagettfbbox](/ref/image.html#imagettfbbox) — Give the bounding
        box of a text using TrueType fonts
    -   [imagettftext](/ref/image.html#imagettftext) — Write text to the
        image using TrueType fonts
    -   [imagetypes](/ref/image.html#imagetypes) — Return the image
        types supported by this PHP build
    -   [imagewbmp](/ref/image.html#imagewbmp) — Output image to browser
        or file
    -   [imagewebp](/ref/image.html#imagewebp) — Output a WebP image to
        browser or file
    -   [imagexbm](/ref/image.html#imagexbm) — Output an XBM image to
        browser or file
    -   [iptcembed](/ref/image.html#iptcembed) — Embeds binary IPTC data
        into a JPEG image
    -   [iptcparse](/ref/image.html#iptcparse) — Parse a binary IPTC
        block into single tags
    -   [jpeg2wbmp](/ref/image.html#jpeg2wbmp) — Convert JPEG image file
        to WBMP image file
    -   [png2wbmp](/ref/image.html#png2wbmp) — Convert PNG image file to
        WBMP image file
-   [GdImage](/class/gdimage.html) — The GdImage class

Introduction
------------

A fully opaque class which replaces *gd* resources as of PHP 8.0.0.

Class synopsis
--------------

**GdImage**

<span class="ooclass"> <span class="modifier">final</span> class
**GdImage** </span> {

}
