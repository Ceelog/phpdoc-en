Examples
========

**Table of Contents**

-   [PNG creation with
    PHP](/image/examples.html#PNG%20creation%20with%20PHP)
-   [Adding watermarks to images using alpha
    channels](/image/examples.html#Adding%20watermarks%20to%20images%20using%20alpha%20channels)
-   [Using imagecopymerge to create a translucent
    watermark](/image/examples.html#Using%20imagecopymerge%20to%20create%20a%20translucent%20watermark)

PNG creation with PHP
---------------------

**Example \#1 PNG creation with PHP**

``` php
<?php

header("Content-type: image/png");
$string = $_GET['text'];
$im     = imagecreatefrompng("images/button1.png");
$orange = imagecolorallocate($im, 220, 210, 60);
$px     = (imagesx($im) - 7.5 * strlen($string)) / 2;
imagestring($im, 3, $px, 9, $string, $orange);
imagepng($im);
imagedestroy($im);

?>
```

This example would be called from a page with a tag like: *\<img
src="button.php?text=text"\>*. The above `button.php` script then takes
this *"text"* string and overlays it on top of a base image which in
this case is *"images/button1.png"* and outputs the resulting image.
This is a very convenient way to avoid having to draw new button images
every time you want to change the text of a button. With this method
they are dynamically generated.

Adding watermarks to images using alpha channels
------------------------------------------------

**Example \#1 Adding watermarks to images using alpha channels**

``` php
<?php
// Load the stamp and the photo to apply the watermark to
$stamp = imagecreatefrompng('stamp.png');
$im = imagecreatefromjpeg('photo.jpeg');

// Set the margins for the stamp and get the height/width of the stamp image
$marge_right = 10;
$marge_bottom = 10;
$sx = imagesx($stamp);
$sy = imagesy($stamp);

// Copy the stamp image onto our photo using the margin offsets and the photo 
// width to calculate positioning of the stamp. 
imagecopy($im, $stamp, imagesx($im) - $sx - $marge_right, imagesy($im) - $sy - $marge_bottom, 0, 0, imagesx($stamp), imagesy($stamp));

// Output and free memory
header('Content-type: image/png');
imagepng($im);
imagedestroy($im);
?>
```

<img src="images/21009b70229598c6a80eef8b45bf282b-watermarks.png" width="320" height="240" alt="Adding watermarks to images using alpha channels" />

This example is a common way to add watermarks and stamps to photos and
copyrighted images. Note that the presence of an alpha channel in the
stamp image as the text is anti-aliased. This is preserved during
copying.

Using <span class="function">imagecopymerge</span> to create a translucent watermark
------------------------------------------------------------------------------------

**Example \#1 Using <span class="function">imagecopymerge</span> to
create a translucent watermark**

``` php
<?php
// Load the stamp and the photo to apply the watermark to
$im = imagecreatefromjpeg('photo.jpeg');

// First we create our stamp image manually from GD
$stamp = imagecreatetruecolor(100, 70);
imagefilledrectangle($stamp, 0, 0, 99, 69, 0x0000FF);
imagefilledrectangle($stamp, 9, 9, 90, 60, 0xFFFFFF);
imagestring($stamp, 5, 20, 20, 'libGD', 0x0000FF);
imagestring($stamp, 3, 20, 40, '(c) 2007-9', 0x0000FF);

// Set the margins for the stamp and get the height/width of the stamp image
$marge_right = 10;
$marge_bottom = 10;
$sx = imagesx($stamp);
$sy = imagesy($stamp);

// Merge the stamp onto our photo with an opacity of 50%
imagecopymerge($im, $stamp, imagesx($im) - $sx - $marge_right, imagesy($im) - $sy - $marge_bottom, 0, 0, imagesx($stamp), imagesy($stamp), 50);

// Save the image to file and free memory
imagepng($im, 'photo_stamp.png');
imagedestroy($im);

?>
```

<img src="images/21009b70229598c6a80eef8b45bf282b-watermark-merged.png" width="320" height="240" alt="Using imagecopymerge() to create a translucent watermark" />

This example uses <span class="function">imagecopymerge</span> to merge
the stamp with our original image. Using this we can set the opacity of
our stamp - in our example we've set it to 50% opacity. In practice this
would be useful in copyright protection as semi-transparent watermarks
are hard to remove yet allow viewers to see the image.
