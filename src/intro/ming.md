First of all: Ming is not an acronym. Ming is an open-source (LGPL)
library which allows you to create SWF ("Flash") format movies. Ming
supports almost all of Flash 4's features, including: shapes, gradients,
bitmaps (pngs and jpegs), morphs ("shape tweens"), text, buttons,
actions, sprites ("movie clips"), streaming mp3, and color transforms
--the only thing that's missing is sound events.

Note that all values specifying length, distance, size, etc. are in
"twips", twenty units per pixel. That's pretty much arbitrary, though,
since the player scales the movie to whatever pixel size is specified in
the embed/object tag, or the entire frame if not embedded.

Ming offers a number of advantages over the existing PHP/libswf module.
You can use Ming anywhere you can compile the code, whereas libswf is
closed-source and only available for a few platforms, Windows not one of
them. Ming provides some insulation from the mundane details of the SWF
file format, wrapping the movie elements in PHP objects. Also, Ming is
still being maintained; if there's a feature that you want to see, just
let us know at
<a href="http://www.libming.org/" class="link external">» http://www.libming.org/</a>.

**Warning**

This extension is *EXPERIMENTAL*. The behaviour of this extension
including the names of its functions and any other documentation
surrounding this extension may change without notice in a future release
of PHP. This extension should be used at your own risk.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 5.3.0.
