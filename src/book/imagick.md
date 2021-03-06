Image Processing (ImageMagick)
==============================

**Table of Contents**

-   [Introduction](/intro/imagick.html)
-   [Installing/Configuring](/imagick/setup.html)
    -   [Requirements](/imagick/setup.html#Requirements)
    -   [Installation](/imagick/setup.html#Installation)
    -   [Runtime
        Configuration](/imagick/setup.html#Runtime%20Configuration)
    -   [Resource Types](/imagick/setup.html#Resource%20Types)
-   [Predefined Constants](/imagick/constants.html)
-   [Examples](/imagick/examples.html)
    -   [Basic usage](/imagick/examples.html#Basic%20usage)
-   [Imagick](/class/imagick.html) — The Imagick class
    -   [Imagick::adaptiveBlurImage](/class/imagick.html#Imagick::adaptiveBlurImage)
        — Adds adaptive blur filter to image
    -   [Imagick::adaptiveResizeImage](/class/imagick.html#Imagick::adaptiveResizeImage)
        — Adaptively resize image with data dependent triangulation
    -   [Imagick::adaptiveSharpenImage](/class/imagick.html#Imagick::adaptiveSharpenImage)
        — Adaptively sharpen the image
    -   [Imagick::adaptiveThresholdImage](/class/imagick.html#Imagick::adaptiveThresholdImage)
        — Selects a threshold for each pixel based on a range of
        intensity
    -   [Imagick::addImage](/class/imagick.html#Imagick::addImage) —
        Adds new image to Imagick object image list
    -   [Imagick::addNoiseImage](/class/imagick.html#Imagick::addNoiseImage)
        — Adds random noise to the image
    -   [Imagick::affineTransformImage](/class/imagick.html#Imagick::affineTransformImage)
        — Transforms an image
    -   [Imagick::animateImages](/class/imagick.html#Imagick::animateImages)
        — Animates an image or images
    -   [Imagick::annotateImage](/class/imagick.html#Imagick::annotateImage)
        — Annotates an image with text
    -   [Imagick::appendImages](/class/imagick.html#Imagick::appendImages)
        — Append a set of images
    -   [Imagick::autoLevelImage](/class/imagick.html#Imagick::autoLevelImage)
        — Description
    -   [Imagick::averageImages](/class/imagick.html#Imagick::averageImages)
        — Average a set of images
    -   [Imagick::blackThresholdImage](/class/imagick.html#Imagick::blackThresholdImage)
        — Forces all pixels below the threshold into black
    -   [Imagick::blueShiftImage](/class/imagick.html#Imagick::blueShiftImage)
        — Description
    -   [Imagick::blurImage](/class/imagick.html#Imagick::blurImage) —
        Adds blur filter to image
    -   [Imagick::borderImage](/class/imagick.html#Imagick::borderImage)
        — Surrounds the image with a border
    -   [Imagick::brightnessContrastImage](/class/imagick.html#Imagick::brightnessContrastImage)
        — Description
    -   [Imagick::charcoalImage](/class/imagick.html#Imagick::charcoalImage)
        — Simulates a charcoal drawing
    -   [Imagick::chopImage](/class/imagick.html#Imagick::chopImage) —
        Removes a region of an image and trims
    -   [Imagick::clampImage](/class/imagick.html#Imagick::clampImage) —
        Description
    -   [Imagick::clear](/class/imagick.html#Imagick::clear) — Clears
        all resources associated to Imagick object
    -   [Imagick::clipImage](/class/imagick.html#Imagick::clipImage) —
        Clips along the first path from the 8BIM profile
    -   [Imagick::clipImagePath](/class/imagick.html#Imagick::clipImagePath)
        — Description
    -   [Imagick::clipPathImage](/class/imagick.html#Imagick::clipPathImage)
        — Clips along the named paths from the 8BIM profile
    -   [Imagick::clone](/class/imagick.html#Imagick::clone) — Makes an
        exact copy of the Imagick object
    -   [Imagick::clutImage](/class/imagick.html#Imagick::clutImage) —
        Replaces colors in the image
    -   [Imagick::coalesceImages](/class/imagick.html#Imagick::coalesceImages)
        — Composites a set of images
    -   [Imagick::colorFloodfillImage](/class/imagick.html#Imagick::colorFloodfillImage)
        — Changes the color value of any pixel that matches target
    -   [Imagick::colorizeImage](/class/imagick.html#Imagick::colorizeImage)
        — Blends the fill color with the image
    -   [Imagick::colorMatrixImage](/class/imagick.html#Imagick::colorMatrixImage)
        — Description
    -   [Imagick::combineImages](/class/imagick.html#Imagick::combineImages)
        — Combines one or more images into a single image
    -   [Imagick::commentImage](/class/imagick.html#Imagick::commentImage)
        — Adds a comment to your image
    -   [Imagick::compareImageChannels](/class/imagick.html#Imagick::compareImageChannels)
        — Returns the difference in one or more images
    -   [Imagick::compareImageLayers](/class/imagick.html#Imagick::compareImageLayers)
        — Returns the maximum bounding region between images
    -   [Imagick::compareImages](/class/imagick.html#Imagick::compareImages)
        — Compares an image to a reconstructed image
    -   [Imagick::compositeImage](/class/imagick.html#Imagick::compositeImage)
        — Composite one image onto another
    -   [Imagick::\_\_construct](/class/imagick.html#Imagick::__construct)
        — The Imagick constructor
    -   [Imagick::contrastImage](/class/imagick.html#Imagick::contrastImage)
        — Change the contrast of the image
    -   [Imagick::contrastStretchImage](/class/imagick.html#Imagick::contrastStretchImage)
        — Enhances the contrast of a color image
    -   [Imagick::convolveImage](/class/imagick.html#Imagick::convolveImage)
        — Applies a custom convolution kernel to the image
    -   [Imagick::count](/class/imagick.html#Imagick::count) — Get the
        number of images
    -   [Imagick::cropImage](/class/imagick.html#Imagick::cropImage) —
        Extracts a region of the image
    -   [Imagick::cropThumbnailImage](/class/imagick.html#Imagick::cropThumbnailImage)
        — Creates a crop thumbnail
    -   [Imagick::current](/class/imagick.html#Imagick::current) —
        Returns a reference to the current Imagick object
    -   [Imagick::cycleColormapImage](/class/imagick.html#Imagick::cycleColormapImage)
        — Displaces an image's colormap
    -   [Imagick::decipherImage](/class/imagick.html#Imagick::decipherImage)
        — Deciphers an image
    -   [Imagick::deconstructImages](/class/imagick.html#Imagick::deconstructImages)
        — Returns certain pixel differences between images
    -   [Imagick::deleteImageArtifact](/class/imagick.html#Imagick::deleteImageArtifact)
        — Delete image artifact
    -   [Imagick::deleteImageProperty](/class/imagick.html#Imagick::deleteImageProperty)
        — Description
    -   [Imagick::deskewImage](/class/imagick.html#Imagick::deskewImage)
        — Removes skew from the image
    -   [Imagick::despeckleImage](/class/imagick.html#Imagick::despeckleImage)
        — Reduces the speckle noise in an image
    -   [Imagick::destroy](/class/imagick.html#Imagick::destroy) —
        Destroys the Imagick object
    -   [Imagick::displayImage](/class/imagick.html#Imagick::displayImage)
        — Displays an image
    -   [Imagick::displayImages](/class/imagick.html#Imagick::displayImages)
        — Displays an image or image sequence
    -   [Imagick::distortImage](/class/imagick.html#Imagick::distortImage)
        — Distorts an image using various distortion methods
    -   [Imagick::drawImage](/class/imagick.html#Imagick::drawImage) —
        Renders the ImagickDraw object on the current image
    -   [Imagick::edgeImage](/class/imagick.html#Imagick::edgeImage) —
        Enhance edges within the image
    -   [Imagick::embossImage](/class/imagick.html#Imagick::embossImage)
        — Returns a grayscale image with a three-dimensional effect
    -   [Imagick::encipherImage](/class/imagick.html#Imagick::encipherImage)
        — Enciphers an image
    -   [Imagick::enhanceImage](/class/imagick.html#Imagick::enhanceImage)
        — Improves the quality of a noisy image
    -   [Imagick::equalizeImage](/class/imagick.html#Imagick::equalizeImage)
        — Equalizes the image histogram
    -   [Imagick::evaluateImage](/class/imagick.html#Imagick::evaluateImage)
        — Applies an expression to an image
    -   [Imagick::exportImagePixels](/class/imagick.html#Imagick::exportImagePixels)
        — Exports raw image pixels
    -   [Imagick::extentImage](/class/imagick.html#Imagick::extentImage)
        — Set image size
    -   [Imagick::filter](/class/imagick.html#Imagick::filter) —
        Description
    -   [Imagick::flattenImages](/class/imagick.html#Imagick::flattenImages)
        — Merges a sequence of images
    -   [Imagick::flipImage](/class/imagick.html#Imagick::flipImage) —
        Creates a vertical mirror image
    -   [Imagick::floodFillPaintImage](/class/imagick.html#Imagick::floodFillPaintImage)
        — Changes the color value of any pixel that matches target
    -   [Imagick::flopImage](/class/imagick.html#Imagick::flopImage) —
        Creates a vertical mirror image
    -   [Imagick::forwardFourierTransformImage](/class/imagick.html#Imagick::forwardFourierTransformImage)
        — Description
    -   [Imagick::frameImage](/class/imagick.html#Imagick::frameImage) —
        Adds a simulated three-dimensional border
    -   [Imagick::functionImage](/class/imagick.html#Imagick::functionImage)
        — Applies a function on the image
    -   [Imagick::fxImage](/class/imagick.html#Imagick::fxImage) —
        Evaluate expression for each pixel in the image
    -   [Imagick::gammaImage](/class/imagick.html#Imagick::gammaImage) —
        Gamma-corrects an image
    -   [Imagick::gaussianBlurImage](/class/imagick.html#Imagick::gaussianBlurImage)
        — Blurs an image
    -   [Imagick::getColorspace](/class/imagick.html#Imagick::getColorspace)
        — Gets the colorspace
    -   [Imagick::getCompression](/class/imagick.html#Imagick::getCompression)
        — Gets the object compression type
    -   [Imagick::getCompressionQuality](/class/imagick.html#Imagick::getCompressionQuality)
        — Gets the object compression quality
    -   [Imagick::getCopyright](/class/imagick.html#Imagick::getCopyright)
        — Returns the ImageMagick API copyright as a string
    -   [Imagick::getFilename](/class/imagick.html#Imagick::getFilename)
        — The filename associated with an image sequence
    -   [Imagick::getFont](/class/imagick.html#Imagick::getFont) — Gets
        font
    -   [Imagick::getFormat](/class/imagick.html#Imagick::getFormat) —
        Returns the format of the Imagick object
    -   [Imagick::getGravity](/class/imagick.html#Imagick::getGravity) —
        Gets the gravity
    -   [Imagick::getHomeURL](/class/imagick.html#Imagick::getHomeURL) —
        Returns the ImageMagick home URL
    -   [Imagick::getImage](/class/imagick.html#Imagick::getImage) —
        Returns a new Imagick object
    -   [Imagick::getImageAlphaChannel](/class/imagick.html#Imagick::getImageAlphaChannel)
        — Gets the image alpha channel
    -   [Imagick::getImageArtifact](/class/imagick.html#Imagick::getImageArtifact)
        — Get image artifact
    -   [Imagick::getImageAttribute](/class/imagick.html#Imagick::getImageAttribute)
        — Description
    -   [Imagick::getImageBackgroundColor](/class/imagick.html#Imagick::getImageBackgroundColor)
        — Returns the image background color
    -   [Imagick::getImageBlob](/class/imagick.html#Imagick::getImageBlob)
        — Returns the image sequence as a blob
    -   [Imagick::getImageBluePrimary](/class/imagick.html#Imagick::getImageBluePrimary)
        — Returns the chromaticy blue primary point
    -   [Imagick::getImageBorderColor](/class/imagick.html#Imagick::getImageBorderColor)
        — Returns the image border color
    -   [Imagick::getImageChannelDepth](/class/imagick.html#Imagick::getImageChannelDepth)
        — Gets the depth for a particular image channel
    -   [Imagick::getImageChannelDistortion](/class/imagick.html#Imagick::getImageChannelDistortion)
        — Compares image channels of an image to a reconstructed image
    -   [Imagick::getImageChannelDistortions](/class/imagick.html#Imagick::getImageChannelDistortions)
        — Gets channel distortions
    -   [Imagick::getImageChannelExtrema](/class/imagick.html#Imagick::getImageChannelExtrema)
        — Gets the extrema for one or more image channels
    -   [Imagick::getImageChannelKurtosis](/class/imagick.html#Imagick::getImageChannelKurtosis)
        — The getImageChannelKurtosis purpose
    -   [Imagick::getImageChannelMean](/class/imagick.html#Imagick::getImageChannelMean)
        — Gets the mean and standard deviation
    -   [Imagick::getImageChannelRange](/class/imagick.html#Imagick::getImageChannelRange)
        — Gets channel range
    -   [Imagick::getImageChannelStatistics](/class/imagick.html#Imagick::getImageChannelStatistics)
        — Returns statistics for each channel in the image
    -   [Imagick::getImageClipMask](/class/imagick.html#Imagick::getImageClipMask)
        — Gets image clip mask
    -   [Imagick::getImageColormapColor](/class/imagick.html#Imagick::getImageColormapColor)
        — Returns the color of the specified colormap index
    -   [Imagick::getImageColors](/class/imagick.html#Imagick::getImageColors)
        — Gets the number of unique colors in the image
    -   [Imagick::getImageColorspace](/class/imagick.html#Imagick::getImageColorspace)
        — Gets the image colorspace
    -   [Imagick::getImageCompose](/class/imagick.html#Imagick::getImageCompose)
        — Returns the composite operator associated with the image
    -   [Imagick::getImageCompression](/class/imagick.html#Imagick::getImageCompression)
        — Gets the current image's compression type
    -   [Imagick::getImageCompressionQuality](/class/imagick.html#Imagick::getImageCompressionQuality)
        — Gets the current image's compression quality
    -   [Imagick::getImageDelay](/class/imagick.html#Imagick::getImageDelay)
        — Gets the image delay
    -   [Imagick::getImageDepth](/class/imagick.html#Imagick::getImageDepth)
        — Gets the image depth
    -   [Imagick::getImageDispose](/class/imagick.html#Imagick::getImageDispose)
        — Gets the image disposal method
    -   [Imagick::getImageDistortion](/class/imagick.html#Imagick::getImageDistortion)
        — Compares an image to a reconstructed image
    -   [Imagick::getImageExtrema](/class/imagick.html#Imagick::getImageExtrema)
        — Gets the extrema for the image
    -   [Imagick::getImageFilename](/class/imagick.html#Imagick::getImageFilename)
        — Returns the filename of a particular image in a sequence
    -   [Imagick::getImageFormat](/class/imagick.html#Imagick::getImageFormat)
        — Returns the format of a particular image in a sequence
    -   [Imagick::getImageGamma](/class/imagick.html#Imagick::getImageGamma)
        — Gets the image gamma
    -   [Imagick::getImageGeometry](/class/imagick.html#Imagick::getImageGeometry)
        — Gets the width and height as an associative array
    -   [Imagick::getImageGravity](/class/imagick.html#Imagick::getImageGravity)
        — Gets the image gravity
    -   [Imagick::getImageGreenPrimary](/class/imagick.html#Imagick::getImageGreenPrimary)
        — Returns the chromaticy green primary point
    -   [Imagick::getImageHeight](/class/imagick.html#Imagick::getImageHeight)
        — Returns the image height
    -   [Imagick::getImageHistogram](/class/imagick.html#Imagick::getImageHistogram)
        — Gets the image histogram
    -   [Imagick::getImageIndex](/class/imagick.html#Imagick::getImageIndex)
        — Gets the index of the current active image
    -   [Imagick::getImageInterlaceScheme](/class/imagick.html#Imagick::getImageInterlaceScheme)
        — Gets the image interlace scheme
    -   [Imagick::getImageInterpolateMethod](/class/imagick.html#Imagick::getImageInterpolateMethod)
        — Returns the interpolation method
    -   [Imagick::getImageIterations](/class/imagick.html#Imagick::getImageIterations)
        — Gets the image iterations
    -   [Imagick::getImageLength](/class/imagick.html#Imagick::getImageLength)
        — Returns the image length in bytes
    -   [Imagick::getImageMatte](/class/imagick.html#Imagick::getImageMatte)
        — Return if the image has a matte channel
    -   [Imagick::getImageMatteColor](/class/imagick.html#Imagick::getImageMatteColor)
        — Returns the image matte color
    -   [Imagick::getImageMimeType](/class/imagick.html#Imagick::getImageMimeType)
        — Description
    -   [Imagick::getImageOrientation](/class/imagick.html#Imagick::getImageOrientation)
        — Gets the image orientation
    -   [Imagick::getImagePage](/class/imagick.html#Imagick::getImagePage)
        — Returns the page geometry
    -   [Imagick::getImagePixelColor](/class/imagick.html#Imagick::getImagePixelColor)
        — Returns the color of the specified pixel
    -   [Imagick::getImageProfile](/class/imagick.html#Imagick::getImageProfile)
        — Returns the named image profile
    -   [Imagick::getImageProfiles](/class/imagick.html#Imagick::getImageProfiles)
        — Returns the image profiles
    -   [Imagick::getImageProperties](/class/imagick.html#Imagick::getImageProperties)
        — Returns the image properties
    -   [Imagick::getImageProperty](/class/imagick.html#Imagick::getImageProperty)
        — Returns the named image property
    -   [Imagick::getImageRedPrimary](/class/imagick.html#Imagick::getImageRedPrimary)
        — Returns the chromaticity red primary point
    -   [Imagick::getImageRegion](/class/imagick.html#Imagick::getImageRegion)
        — Extracts a region of the image
    -   [Imagick::getImageRenderingIntent](/class/imagick.html#Imagick::getImageRenderingIntent)
        — Gets the image rendering intent
    -   [Imagick::getImageResolution](/class/imagick.html#Imagick::getImageResolution)
        — Gets the image X and Y resolution
    -   [Imagick::getImagesBlob](/class/imagick.html#Imagick::getImagesBlob)
        — Returns all image sequences as a blob
    -   [Imagick::getImageScene](/class/imagick.html#Imagick::getImageScene)
        — Gets the image scene
    -   [Imagick::getImageSignature](/class/imagick.html#Imagick::getImageSignature)
        — Generates an SHA-256 message digest
    -   [Imagick::getImageSize](/class/imagick.html#Imagick::getImageSize)
        — Returns the image length in bytes
    -   [Imagick::getImageTicksPerSecond](/class/imagick.html#Imagick::getImageTicksPerSecond)
        — Gets the image ticks-per-second
    -   [Imagick::getImageTotalInkDensity](/class/imagick.html#Imagick::getImageTotalInkDensity)
        — Gets the image total ink density
    -   [Imagick::getImageType](/class/imagick.html#Imagick::getImageType)
        — Gets the potential image type
    -   [Imagick::getImageUnits](/class/imagick.html#Imagick::getImageUnits)
        — Gets the image units of resolution
    -   [Imagick::getImageVirtualPixelMethod](/class/imagick.html#Imagick::getImageVirtualPixelMethod)
        — Returns the virtual pixel method
    -   [Imagick::getImageWhitePoint](/class/imagick.html#Imagick::getImageWhitePoint)
        — Returns the chromaticity white point
    -   [Imagick::getImageWidth](/class/imagick.html#Imagick::getImageWidth)
        — Returns the image width
    -   [Imagick::getInterlaceScheme](/class/imagick.html#Imagick::getInterlaceScheme)
        — Gets the object interlace scheme
    -   [Imagick::getIteratorIndex](/class/imagick.html#Imagick::getIteratorIndex)
        — Gets the index of the current active image
    -   [Imagick::getNumberImages](/class/imagick.html#Imagick::getNumberImages)
        — Returns the number of images in the object
    -   [Imagick::getOption](/class/imagick.html#Imagick::getOption) —
        Returns a value associated with the specified key
    -   [Imagick::getPackageName](/class/imagick.html#Imagick::getPackageName)
        — Returns the ImageMagick package name
    -   [Imagick::getPage](/class/imagick.html#Imagick::getPage) —
        Returns the page geometry
    -   [Imagick::getPixelIterator](/class/imagick.html#Imagick::getPixelIterator)
        — Returns a MagickPixelIterator
    -   [Imagick::getPixelRegionIterator](/class/imagick.html#Imagick::getPixelRegionIterator)
        — Get an ImagickPixelIterator for an image section
    -   [Imagick::getPointSize](/class/imagick.html#Imagick::getPointSize)
        — Gets point size
    -   [Imagick::getQuantum](/class/imagick.html#Imagick::getQuantum) —
        Description
    -   [Imagick::getQuantumDepth](/class/imagick.html#Imagick::getQuantumDepth)
        — Gets the quantum depth
    -   [Imagick::getQuantumRange](/class/imagick.html#Imagick::getQuantumRange)
        — Returns the Imagick quantum range
    -   [Imagick::getRegistry](/class/imagick.html#Imagick::getRegistry)
        — Description
    -   [Imagick::getReleaseDate](/class/imagick.html#Imagick::getReleaseDate)
        — Returns the ImageMagick release date
    -   [Imagick::getResource](/class/imagick.html#Imagick::getResource)
        — Returns the specified resource's memory usage
    -   [Imagick::getResourceLimit](/class/imagick.html#Imagick::getResourceLimit)
        — Returns the specified resource limit
    -   [Imagick::getSamplingFactors](/class/imagick.html#Imagick::getSamplingFactors)
        — Gets the horizontal and vertical sampling factor
    -   [Imagick::getSize](/class/imagick.html#Imagick::getSize) —
        Returns the size associated with the Imagick object
    -   [Imagick::getSizeOffset](/class/imagick.html#Imagick::getSizeOffset)
        — Returns the size offset
    -   [Imagick::getVersion](/class/imagick.html#Imagick::getVersion) —
        Returns the ImageMagick API version
    -   [Imagick::haldClutImage](/class/imagick.html#Imagick::haldClutImage)
        — Replaces colors in the image
    -   [Imagick::hasNextImage](/class/imagick.html#Imagick::hasNextImage)
        — Checks if the object has more images
    -   [Imagick::hasPreviousImage](/class/imagick.html#Imagick::hasPreviousImage)
        — Checks if the object has a previous image
    -   [Imagick::identifyFormat](/class/imagick.html#Imagick::identifyFormat)
        — Description
    -   [Imagick::identifyImage](/class/imagick.html#Imagick::identifyImage)
        — Identifies an image and fetches attributes
    -   [Imagick::implodeImage](/class/imagick.html#Imagick::implodeImage)
        — Creates a new image as a copy
    -   [Imagick::importImagePixels](/class/imagick.html#Imagick::importImagePixels)
        — Imports image pixels
    -   [Imagick::inverseFourierTransformImage](/class/imagick.html#Imagick::inverseFourierTransformImage)
        — Description
    -   [Imagick::labelImage](/class/imagick.html#Imagick::labelImage) —
        Adds a label to an image
    -   [Imagick::levelImage](/class/imagick.html#Imagick::levelImage) —
        Adjusts the levels of an image
    -   [Imagick::linearStretchImage](/class/imagick.html#Imagick::linearStretchImage)
        — Stretches with saturation the image intensity
    -   [Imagick::liquidRescaleImage](/class/imagick.html#Imagick::liquidRescaleImage)
        — Animates an image or images
    -   [Imagick::listRegistry](/class/imagick.html#Imagick::listRegistry)
        — Description
    -   [Imagick::magnifyImage](/class/imagick.html#Imagick::magnifyImage)
        — Scales an image proportionally 2x
    -   [Imagick::mapImage](/class/imagick.html#Imagick::mapImage) —
        Replaces the colors of an image with the closest color from a
        reference image
    -   [Imagick::matteFloodfillImage](/class/imagick.html#Imagick::matteFloodfillImage)
        — Changes the transparency value of a color
    -   [Imagick::medianFilterImage](/class/imagick.html#Imagick::medianFilterImage)
        — Applies a digital filter
    -   [Imagick::mergeImageLayers](/class/imagick.html#Imagick::mergeImageLayers)
        — Merges image layers
    -   [Imagick::minifyImage](/class/imagick.html#Imagick::minifyImage)
        — Scales an image proportionally to half its size
    -   [Imagick::modulateImage](/class/imagick.html#Imagick::modulateImage)
        — Control the brightness, saturation, and hue
    -   [Imagick::montageImage](/class/imagick.html#Imagick::montageImage)
        — Creates a composite image
    -   [Imagick::morphImages](/class/imagick.html#Imagick::morphImages)
        — Method morphs a set of images
    -   [Imagick::morphology](/class/imagick.html#Imagick::morphology) —
        Description
    -   [Imagick::mosaicImages](/class/imagick.html#Imagick::mosaicImages)
        — Forms a mosaic from images
    -   [Imagick::motionBlurImage](/class/imagick.html#Imagick::motionBlurImage)
        — Simulates motion blur
    -   [Imagick::negateImage](/class/imagick.html#Imagick::negateImage)
        — Negates the colors in the reference image
    -   [Imagick::newImage](/class/imagick.html#Imagick::newImage) —
        Creates a new image
    -   [Imagick::newPseudoImage](/class/imagick.html#Imagick::newPseudoImage)
        — Creates a new image
    -   [Imagick::nextImage](/class/imagick.html#Imagick::nextImage) —
        Moves to the next image
    -   [Imagick::normalizeImage](/class/imagick.html#Imagick::normalizeImage)
        — Enhances the contrast of a color image
    -   [Imagick::oilPaintImage](/class/imagick.html#Imagick::oilPaintImage)
        — Simulates an oil painting
    -   [Imagick::opaquePaintImage](/class/imagick.html#Imagick::opaquePaintImage)
        — Changes the color value of any pixel that matches target
    -   [Imagick::optimizeImageLayers](/class/imagick.html#Imagick::optimizeImageLayers)
        — Removes repeated portions of images to optimize
    -   [Imagick::orderedPosterizeImage](/class/imagick.html#Imagick::orderedPosterizeImage)
        — Performs an ordered dither
    -   [Imagick::paintFloodfillImage](/class/imagick.html#Imagick::paintFloodfillImage)
        — Changes the color value of any pixel that matches target
    -   [Imagick::paintOpaqueImage](/class/imagick.html#Imagick::paintOpaqueImage)
        — Change any pixel that matches color
    -   [Imagick::paintTransparentImage](/class/imagick.html#Imagick::paintTransparentImage)
        — Changes any pixel that matches color with the color defined by
        fill
    -   [Imagick::pingImage](/class/imagick.html#Imagick::pingImage) —
        Fetch basic attributes about the image
    -   [Imagick::pingImageBlob](/class/imagick.html#Imagick::pingImageBlob)
        — Quickly fetch attributes
    -   [Imagick::pingImageFile](/class/imagick.html#Imagick::pingImageFile)
        — Get basic image attributes in a lightweight manner
    -   [Imagick::polaroidImage](/class/imagick.html#Imagick::polaroidImage)
        — Simulates a Polaroid picture
    -   [Imagick::posterizeImage](/class/imagick.html#Imagick::posterizeImage)
        — Reduces the image to a limited number of color level
    -   [Imagick::previewImages](/class/imagick.html#Imagick::previewImages)
        — Quickly pin-point appropriate parameters for image processing
    -   [Imagick::previousImage](/class/imagick.html#Imagick::previousImage)
        — Move to the previous image in the object
    -   [Imagick::profileImage](/class/imagick.html#Imagick::profileImage)
        — Adds or removes a profile from an image
    -   [Imagick::quantizeImage](/class/imagick.html#Imagick::quantizeImage)
        — Analyzes the colors within a reference image
    -   [Imagick::quantizeImages](/class/imagick.html#Imagick::quantizeImages)
        — Analyzes the colors within a sequence of images
    -   [Imagick::queryFontMetrics](/class/imagick.html#Imagick::queryFontMetrics)
        — Returns an array representing the font metrics
    -   [Imagick::queryFonts](/class/imagick.html#Imagick::queryFonts) —
        Returns the configured fonts
    -   [Imagick::queryFormats](/class/imagick.html#Imagick::queryFormats)
        — Returns formats supported by Imagick
    -   [Imagick::radialBlurImage](/class/imagick.html#Imagick::radialBlurImage)
        — Radial blurs an image
    -   [Imagick::raiseImage](/class/imagick.html#Imagick::raiseImage) —
        Creates a simulated 3d button-like effect
    -   [Imagick::randomThresholdImage](/class/imagick.html#Imagick::randomThresholdImage)
        — Creates a high-contrast, two-color image
    -   [Imagick::readImage](/class/imagick.html#Imagick::readImage) —
        Reads image from filename
    -   [Imagick::readImageBlob](/class/imagick.html#Imagick::readImageBlob)
        — Reads image from a binary string
    -   [Imagick::readImageFile](/class/imagick.html#Imagick::readImageFile)
        — Reads image from open filehandle
    -   [Imagick::readimages](/class/imagick.html#Imagick::readimages) —
        Description
    -   [Imagick::recolorImage](/class/imagick.html#Imagick::recolorImage)
        — Recolors image
    -   [Imagick::reduceNoiseImage](/class/imagick.html#Imagick::reduceNoiseImage)
        — Smooths the contours of an image
    -   [Imagick::remapImage](/class/imagick.html#Imagick::remapImage) —
        Remaps image colors
    -   [Imagick::removeImage](/class/imagick.html#Imagick::removeImage)
        — Removes an image from the image list
    -   [Imagick::removeImageProfile](/class/imagick.html#Imagick::removeImageProfile)
        — Removes the named image profile and returns it
    -   [Imagick::render](/class/imagick.html#Imagick::render) — Renders
        all preceding drawing commands
    -   [Imagick::resampleImage](/class/imagick.html#Imagick::resampleImage)
        — Resample image to desired resolution
    -   [Imagick::resetImagePage](/class/imagick.html#Imagick::resetImagePage)
        — Reset image page
    -   [Imagick::resizeImage](/class/imagick.html#Imagick::resizeImage)
        — Scales an image
    -   [Imagick::rollImage](/class/imagick.html#Imagick::rollImage) —
        Offsets an image
    -   [Imagick::rotateImage](/class/imagick.html#Imagick::rotateImage)
        — Rotates an image
    -   [Imagick::rotationalBlurImage](/class/imagick.html#Imagick::rotationalBlurImage)
        — Description
    -   [Imagick::roundCorners](/class/imagick.html#Imagick::roundCorners)
        — Rounds image corners
    -   [Imagick::sampleImage](/class/imagick.html#Imagick::sampleImage)
        — Scales an image with pixel sampling
    -   [Imagick::scaleImage](/class/imagick.html#Imagick::scaleImage) —
        Scales the size of an image
    -   [Imagick::segmentImage](/class/imagick.html#Imagick::segmentImage)
        — Segments an image
    -   [Imagick::selectiveBlurImage](/class/imagick.html#Imagick::selectiveBlurImage)
        — Description
    -   [Imagick::separateImageChannel](/class/imagick.html#Imagick::separateImageChannel)
        — Separates a channel from the image
    -   [Imagick::sepiaToneImage](/class/imagick.html#Imagick::sepiaToneImage)
        — Sepia tones an image
    -   [Imagick::setBackgroundColor](/class/imagick.html#Imagick::setBackgroundColor)
        — Sets the object's default background color
    -   [Imagick::setColorspace](/class/imagick.html#Imagick::setColorspace)
        — Set colorspace
    -   [Imagick::setCompression](/class/imagick.html#Imagick::setCompression)
        — Sets the object's default compression type
    -   [Imagick::setCompressionQuality](/class/imagick.html#Imagick::setCompressionQuality)
        — Sets the object's default compression quality
    -   [Imagick::setFilename](/class/imagick.html#Imagick::setFilename)
        — Sets the filename before you read or write the image
    -   [Imagick::setFirstIterator](/class/imagick.html#Imagick::setFirstIterator)
        — Sets the Imagick iterator to the first image
    -   [Imagick::setFont](/class/imagick.html#Imagick::setFont) — Sets
        font
    -   [Imagick::setFormat](/class/imagick.html#Imagick::setFormat) —
        Sets the format of the Imagick object
    -   [Imagick::setGravity](/class/imagick.html#Imagick::setGravity) —
        Sets the gravity
    -   [Imagick::setImage](/class/imagick.html#Imagick::setImage) —
        Replaces image in the object
    -   [Imagick::setImageAlphaChannel](/class/imagick.html#Imagick::setImageAlphaChannel)
        — Sets image alpha channel
    -   [Imagick::setImageArtifact](/class/imagick.html#Imagick::setImageArtifact)
        — Set image artifact
    -   [Imagick::setImageAttribute](/class/imagick.html#Imagick::setImageAttribute)
        — Description
    -   [Imagick::setImageBackgroundColor](/class/imagick.html#Imagick::setImageBackgroundColor)
        — Sets the image background color
    -   [Imagick::setImageBias](/class/imagick.html#Imagick::setImageBias)
        — Sets the image bias for any method that convolves an image
    -   [Imagick::setImageBiasQuantum](/class/imagick.html#Imagick::setImageBiasQuantum)
        — Description
    -   [Imagick::setImageBluePrimary](/class/imagick.html#Imagick::setImageBluePrimary)
        — Sets the image chromaticity blue primary point
    -   [Imagick::setImageBorderColor](/class/imagick.html#Imagick::setImageBorderColor)
        — Sets the image border color
    -   [Imagick::setImageChannelDepth](/class/imagick.html#Imagick::setImageChannelDepth)
        — Sets the depth of a particular image channel
    -   [Imagick::setImageClipMask](/class/imagick.html#Imagick::setImageClipMask)
        — Sets image clip mask
    -   [Imagick::setImageColormapColor](/class/imagick.html#Imagick::setImageColormapColor)
        — Sets the color of the specified colormap index
    -   [Imagick::setImageColorspace](/class/imagick.html#Imagick::setImageColorspace)
        — Sets the image colorspace
    -   [Imagick::setImageCompose](/class/imagick.html#Imagick::setImageCompose)
        — Sets the image composite operator
    -   [Imagick::setImageCompression](/class/imagick.html#Imagick::setImageCompression)
        — Sets the image compression
    -   [Imagick::setImageCompressionQuality](/class/imagick.html#Imagick::setImageCompressionQuality)
        — Sets the image compression quality
    -   [Imagick::setImageDelay](/class/imagick.html#Imagick::setImageDelay)
        — Sets the image delay
    -   [Imagick::setImageDepth](/class/imagick.html#Imagick::setImageDepth)
        — Sets the image depth
    -   [Imagick::setImageDispose](/class/imagick.html#Imagick::setImageDispose)
        — Sets the image disposal method
    -   [Imagick::setImageExtent](/class/imagick.html#Imagick::setImageExtent)
        — Sets the image size
    -   [Imagick::setImageFilename](/class/imagick.html#Imagick::setImageFilename)
        — Sets the filename of a particular image
    -   [Imagick::setImageFormat](/class/imagick.html#Imagick::setImageFormat)
        — Sets the format of a particular image
    -   [Imagick::setImageGamma](/class/imagick.html#Imagick::setImageGamma)
        — Sets the image gamma
    -   [Imagick::setImageGravity](/class/imagick.html#Imagick::setImageGravity)
        — Sets the image gravity
    -   [Imagick::setImageGreenPrimary](/class/imagick.html#Imagick::setImageGreenPrimary)
        — Sets the image chromaticity green primary point
    -   [Imagick::setImageIndex](/class/imagick.html#Imagick::setImageIndex)
        — Set the iterator position
    -   [Imagick::setImageInterlaceScheme](/class/imagick.html#Imagick::setImageInterlaceScheme)
        — Sets the image compression
    -   [Imagick::setImageInterpolateMethod](/class/imagick.html#Imagick::setImageInterpolateMethod)
        — Sets the image interpolate pixel method
    -   [Imagick::setImageIterations](/class/imagick.html#Imagick::setImageIterations)
        — Sets the image iterations
    -   [Imagick::setImageMatte](/class/imagick.html#Imagick::setImageMatte)
        — Sets the image matte channel
    -   [Imagick::setImageMatteColor](/class/imagick.html#Imagick::setImageMatteColor)
        — Sets the image matte color
    -   [Imagick::setImageOpacity](/class/imagick.html#Imagick::setImageOpacity)
        — Sets the image opacity level
    -   [Imagick::setImageOrientation](/class/imagick.html#Imagick::setImageOrientation)
        — Sets the image orientation
    -   [Imagick::setImagePage](/class/imagick.html#Imagick::setImagePage)
        — Sets the page geometry of the image
    -   [Imagick::setImageProfile](/class/imagick.html#Imagick::setImageProfile)
        — Adds a named profile to the Imagick object
    -   [Imagick::setImageProperty](/class/imagick.html#Imagick::setImageProperty)
        — Sets an image property
    -   [Imagick::setImageRedPrimary](/class/imagick.html#Imagick::setImageRedPrimary)
        — Sets the image chromaticity red primary point
    -   [Imagick::setImageRenderingIntent](/class/imagick.html#Imagick::setImageRenderingIntent)
        — Sets the image rendering intent
    -   [Imagick::setImageResolution](/class/imagick.html#Imagick::setImageResolution)
        — Sets the image resolution
    -   [Imagick::setImageScene](/class/imagick.html#Imagick::setImageScene)
        — Sets the image scene
    -   [Imagick::setImageTicksPerSecond](/class/imagick.html#Imagick::setImageTicksPerSecond)
        — Sets the image ticks-per-second
    -   [Imagick::setImageType](/class/imagick.html#Imagick::setImageType)
        — Sets the image type
    -   [Imagick::setImageUnits](/class/imagick.html#Imagick::setImageUnits)
        — Sets the image units of resolution
    -   [Imagick::setImageVirtualPixelMethod](/class/imagick.html#Imagick::setImageVirtualPixelMethod)
        — Sets the image virtual pixel method
    -   [Imagick::setImageWhitePoint](/class/imagick.html#Imagick::setImageWhitePoint)
        — Sets the image chromaticity white point
    -   [Imagick::setInterlaceScheme](/class/imagick.html#Imagick::setInterlaceScheme)
        — Sets the image compression
    -   [Imagick::setIteratorIndex](/class/imagick.html#Imagick::setIteratorIndex)
        — Set the iterator position
    -   [Imagick::setLastIterator](/class/imagick.html#Imagick::setLastIterator)
        — Sets the Imagick iterator to the last image
    -   [Imagick::setOption](/class/imagick.html#Imagick::setOption) —
        Set an option
    -   [Imagick::setPage](/class/imagick.html#Imagick::setPage) — Sets
        the page geometry of the Imagick object
    -   [Imagick::setPointSize](/class/imagick.html#Imagick::setPointSize)
        — Sets point size
    -   [Imagick::setProgressMonitor](/class/imagick.html#Imagick::setProgressMonitor)
        — Description
    -   [Imagick::setRegistry](/class/imagick.html#Imagick::setRegistry)
        — Description
    -   [Imagick::setResolution](/class/imagick.html#Imagick::setResolution)
        — Sets the image resolution
    -   [Imagick::setResourceLimit](/class/imagick.html#Imagick::setResourceLimit)
        — Sets the limit for a particular resource
    -   [Imagick::setSamplingFactors](/class/imagick.html#Imagick::setSamplingFactors)
        — Sets the image sampling factors
    -   [Imagick::setSize](/class/imagick.html#Imagick::setSize) — Sets
        the size of the Imagick object
    -   [Imagick::setSizeOffset](/class/imagick.html#Imagick::setSizeOffset)
        — Sets the size and offset of the Imagick object
    -   [Imagick::setType](/class/imagick.html#Imagick::setType) — Sets
        the image type attribute
    -   [Imagick::shadeImage](/class/imagick.html#Imagick::shadeImage) —
        Creates a 3D effect
    -   [Imagick::shadowImage](/class/imagick.html#Imagick::shadowImage)
        — Simulates an image shadow
    -   [Imagick::sharpenImage](/class/imagick.html#Imagick::sharpenImage)
        — Sharpens an image
    -   [Imagick::shaveImage](/class/imagick.html#Imagick::shaveImage) —
        Shaves pixels from the image edges
    -   [Imagick::shearImage](/class/imagick.html#Imagick::shearImage) —
        Creating a parallelogram
    -   [Imagick::sigmoidalContrastImage](/class/imagick.html#Imagick::sigmoidalContrastImage)
        — Adjusts the contrast of an image
    -   [Imagick::sketchImage](/class/imagick.html#Imagick::sketchImage)
        — Simulates a pencil sketch
    -   [Imagick::smushImages](/class/imagick.html#Imagick::smushImages)
        — Description
    -   [Imagick::solarizeImage](/class/imagick.html#Imagick::solarizeImage)
        — Applies a solarizing effect to the image
    -   [Imagick::sparseColorImage](/class/imagick.html#Imagick::sparseColorImage)
        — Interpolates colors
    -   [Imagick::spliceImage](/class/imagick.html#Imagick::spliceImage)
        — Splices a solid color into the image
    -   [Imagick::spreadImage](/class/imagick.html#Imagick::spreadImage)
        — Randomly displaces each pixel in a block
    -   [Imagick::statisticImage](/class/imagick.html#Imagick::statisticImage)
        — Description
    -   [Imagick::steganoImage](/class/imagick.html#Imagick::steganoImage)
        — Hides a digital watermark within the image
    -   [Imagick::stereoImage](/class/imagick.html#Imagick::stereoImage)
        — Composites two images
    -   [Imagick::stripImage](/class/imagick.html#Imagick::stripImage) —
        Strips an image of all profiles and comments
    -   [Imagick::subImageMatch](/class/imagick.html#Imagick::subImageMatch)
        — Description
    -   [Imagick::swirlImage](/class/imagick.html#Imagick::swirlImage) —
        Swirls the pixels about the center of the image
    -   [Imagick::textureImage](/class/imagick.html#Imagick::textureImage)
        — Repeatedly tiles the texture image
    -   [Imagick::thresholdImage](/class/imagick.html#Imagick::thresholdImage)
        — Changes the value of individual pixels based on a threshold
    -   [Imagick::thumbnailImage](/class/imagick.html#Imagick::thumbnailImage)
        — Changes the size of an image
    -   [Imagick::tintImage](/class/imagick.html#Imagick::tintImage) —
        Applies a color vector to each pixel in the image
    -   [Imagick::\_\_toString](/class/imagick.html#Imagick::__toString)
        — Returns the image as a string
    -   [Imagick::transformImage](/class/imagick.html#Imagick::transformImage)
        — Convenience method for setting crop size and the image
        geometry
    -   [Imagick::transformImageColorspace](/class/imagick.html#Imagick::transformImageColorspace)
        — Transforms an image to a new colorspace
    -   [Imagick::transparentPaintImage](/class/imagick.html#Imagick::transparentPaintImage)
        — Paints pixels transparent
    -   [Imagick::transposeImage](/class/imagick.html#Imagick::transposeImage)
        — Creates a vertical mirror image
    -   [Imagick::transverseImage](/class/imagick.html#Imagick::transverseImage)
        — Creates a horizontal mirror image
    -   [Imagick::trimImage](/class/imagick.html#Imagick::trimImage) —
        Remove edges from the image
    -   [Imagick::uniqueImageColors](/class/imagick.html#Imagick::uniqueImageColors)
        — Discards all but one of any pixel color
    -   [Imagick::unsharpMaskImage](/class/imagick.html#Imagick::unsharpMaskImage)
        — Sharpens an image
    -   [Imagick::valid](/class/imagick.html#Imagick::valid) — Checks if
        the current item is valid
    -   [Imagick::vignetteImage](/class/imagick.html#Imagick::vignetteImage)
        — Adds vignette filter to the image
    -   [Imagick::waveImage](/class/imagick.html#Imagick::waveImage) —
        Applies wave filter to the image
    -   [Imagick::whiteThresholdImage](/class/imagick.html#Imagick::whiteThresholdImage)
        — Force all pixels above the threshold into white
    -   [Imagick::writeImage](/class/imagick.html#Imagick::writeImage) —
        Writes an image to the specified filename
    -   [Imagick::writeImageFile](/class/imagick.html#Imagick::writeImageFile)
        — Writes an image to a filehandle
    -   [Imagick::writeImages](/class/imagick.html#Imagick::writeImages)
        — Writes an image or image sequence
    -   [Imagick::writeImagesFile](/class/imagick.html#Imagick::writeImagesFile)
        — Writes frames to a filehandle
-   [ImagickDraw](/class/imagickdraw.html) — The ImagickDraw class
    -   [ImagickDraw::affine](/class/imagickdraw.html#ImagickDraw::affine)
        — Adjusts the current affine transformation matrix
    -   [ImagickDraw::annotation](/class/imagickdraw.html#ImagickDraw::annotation)
        — Draws text on the image
    -   [ImagickDraw::arc](/class/imagickdraw.html#ImagickDraw::arc) —
        Draws an arc
    -   [ImagickDraw::bezier](/class/imagickdraw.html#ImagickDraw::bezier)
        — Draws a bezier curve
    -   [ImagickDraw::circle](/class/imagickdraw.html#ImagickDraw::circle)
        — Draws a circle
    -   [ImagickDraw::clear](/class/imagickdraw.html#ImagickDraw::clear)
        — Clears the ImagickDraw
    -   [ImagickDraw::clone](/class/imagickdraw.html#ImagickDraw::clone)
        — Makes an exact copy of the specified ImagickDraw object
    -   [ImagickDraw::color](/class/imagickdraw.html#ImagickDraw::color)
        — Draws color on image
    -   [ImagickDraw::comment](/class/imagickdraw.html#ImagickDraw::comment)
        — Adds a comment
    -   [ImagickDraw::composite](/class/imagickdraw.html#ImagickDraw::composite)
        — Composites an image onto the current image
    -   [ImagickDraw::\_\_construct](/class/imagickdraw.html#ImagickDraw::__construct)
        — The ImagickDraw constructor
    -   [ImagickDraw::destroy](/class/imagickdraw.html#ImagickDraw::destroy)
        — Frees all associated resources
    -   [ImagickDraw::ellipse](/class/imagickdraw.html#ImagickDraw::ellipse)
        — Draws an ellipse on the image
    -   [ImagickDraw::getClipPath](/class/imagickdraw.html#ImagickDraw::getClipPath)
        — Obtains the current clipping path ID
    -   [ImagickDraw::getClipRule](/class/imagickdraw.html#ImagickDraw::getClipRule)
        — Returns the current polygon fill rule
    -   [ImagickDraw::getClipUnits](/class/imagickdraw.html#ImagickDraw::getClipUnits)
        — Returns the interpretation of clip path units
    -   [ImagickDraw::getFillColor](/class/imagickdraw.html#ImagickDraw::getFillColor)
        — Returns the fill color
    -   [ImagickDraw::getFillOpacity](/class/imagickdraw.html#ImagickDraw::getFillOpacity)
        — Returns the opacity used when drawing
    -   [ImagickDraw::getFillRule](/class/imagickdraw.html#ImagickDraw::getFillRule)
        — Returns the fill rule
    -   [ImagickDraw::getFont](/class/imagickdraw.html#ImagickDraw::getFont)
        — Returns the font
    -   [ImagickDraw::getFontFamily](/class/imagickdraw.html#ImagickDraw::getFontFamily)
        — Returns the font family
    -   [ImagickDraw::getFontSize](/class/imagickdraw.html#ImagickDraw::getFontSize)
        — Returns the font pointsize
    -   [ImagickDraw::getFontStretch](/class/imagickdraw.html#ImagickDraw::getFontStretch)
        — Description
    -   [ImagickDraw::getFontStyle](/class/imagickdraw.html#ImagickDraw::getFontStyle)
        — Returns the font style
    -   [ImagickDraw::getFontWeight](/class/imagickdraw.html#ImagickDraw::getFontWeight)
        — Returns the font weight
    -   [ImagickDraw::getGravity](/class/imagickdraw.html#ImagickDraw::getGravity)
        — Returns the text placement gravity
    -   [ImagickDraw::getStrokeAntialias](/class/imagickdraw.html#ImagickDraw::getStrokeAntialias)
        — Returns the current stroke antialias setting
    -   [ImagickDraw::getStrokeColor](/class/imagickdraw.html#ImagickDraw::getStrokeColor)
        — Returns the color used for stroking object outlines
    -   [ImagickDraw::getStrokeDashArray](/class/imagickdraw.html#ImagickDraw::getStrokeDashArray)
        — Returns an array representing the pattern of dashes and gaps
        used to stroke paths
    -   [ImagickDraw::getStrokeDashOffset](/class/imagickdraw.html#ImagickDraw::getStrokeDashOffset)
        — Returns the offset into the dash pattern to start the dash
    -   [ImagickDraw::getStrokeLineCap](/class/imagickdraw.html#ImagickDraw::getStrokeLineCap)
        — Returns the shape to be used at the end of open subpaths when
        they are stroked
    -   [ImagickDraw::getStrokeLineJoin](/class/imagickdraw.html#ImagickDraw::getStrokeLineJoin)
        — Returns the shape to be used at the corners of paths when they
        are stroked
    -   [ImagickDraw::getStrokeMiterLimit](/class/imagickdraw.html#ImagickDraw::getStrokeMiterLimit)
        — Returns the stroke miter limit
    -   [ImagickDraw::getStrokeOpacity](/class/imagickdraw.html#ImagickDraw::getStrokeOpacity)
        — Returns the opacity of stroked object outlines
    -   [ImagickDraw::getStrokeWidth](/class/imagickdraw.html#ImagickDraw::getStrokeWidth)
        — Returns the width of the stroke used to draw object outlines
    -   [ImagickDraw::getTextAlignment](/class/imagickdraw.html#ImagickDraw::getTextAlignment)
        — Returns the text alignment
    -   [ImagickDraw::getTextAntialias](/class/imagickdraw.html#ImagickDraw::getTextAntialias)
        — Returns the current text antialias setting
    -   [ImagickDraw::getTextDecoration](/class/imagickdraw.html#ImagickDraw::getTextDecoration)
        — Returns the text decoration
    -   [ImagickDraw::getTextEncoding](/class/imagickdraw.html#ImagickDraw::getTextEncoding)
        — Returns the code set used for text annotations
    -   [ImagickDraw::getTextInterlineSpacing](/class/imagickdraw.html#ImagickDraw::getTextInterlineSpacing)
        — Description
    -   [ImagickDraw::getTextInterwordSpacing](/class/imagickdraw.html#ImagickDraw::getTextInterwordSpacing)
        — Description
    -   [ImagickDraw::getTextKerning](/class/imagickdraw.html#ImagickDraw::getTextKerning)
        — Description
    -   [ImagickDraw::getTextUnderColor](/class/imagickdraw.html#ImagickDraw::getTextUnderColor)
        — Returns the text under color
    -   [ImagickDraw::getVectorGraphics](/class/imagickdraw.html#ImagickDraw::getVectorGraphics)
        — Returns a string containing vector graphics
    -   [ImagickDraw::line](/class/imagickdraw.html#ImagickDraw::line) —
        Draws a line
    -   [ImagickDraw::matte](/class/imagickdraw.html#ImagickDraw::matte)
        — Paints on the image's opacity channel
    -   [ImagickDraw::pathClose](/class/imagickdraw.html#ImagickDraw::pathClose)
        — Adds a path element to the current path
    -   [ImagickDraw::pathCurveToAbsolute](/class/imagickdraw.html#ImagickDraw::pathCurveToAbsolute)
        — Draws a cubic Bezier curve
    -   [ImagickDraw::pathCurveToQuadraticBezierAbsolute](/class/imagickdraw.html#ImagickDraw::pathCurveToQuadraticBezierAbsolute)
        — Draws a quadratic Bezier curve
    -   [ImagickDraw::pathCurveToQuadraticBezierRelative](/class/imagickdraw.html#ImagickDraw::pathCurveToQuadraticBezierRelative)
        — Draws a quadratic Bezier curve
    -   [ImagickDraw::pathCurveToQuadraticBezierSmoothAbsolute](/class/imagickdraw.html#ImagickDraw::pathCurveToQuadraticBezierSmoothAbsolute)
        — Draws a quadratic Bezier curve
    -   [ImagickDraw::pathCurveToQuadraticBezierSmoothRelative](/class/imagickdraw.html#ImagickDraw::pathCurveToQuadraticBezierSmoothRelative)
        — Draws a quadratic Bezier curve
    -   [ImagickDraw::pathCurveToRelative](/class/imagickdraw.html#ImagickDraw::pathCurveToRelative)
        — Draws a cubic Bezier curve
    -   [ImagickDraw::pathCurveToSmoothAbsolute](/class/imagickdraw.html#ImagickDraw::pathCurveToSmoothAbsolute)
        — Draws a cubic Bezier curve
    -   [ImagickDraw::pathCurveToSmoothRelative](/class/imagickdraw.html#ImagickDraw::pathCurveToSmoothRelative)
        — Draws a cubic Bezier curve
    -   [ImagickDraw::pathEllipticArcAbsolute](/class/imagickdraw.html#ImagickDraw::pathEllipticArcAbsolute)
        — Draws an elliptical arc
    -   [ImagickDraw::pathEllipticArcRelative](/class/imagickdraw.html#ImagickDraw::pathEllipticArcRelative)
        — Draws an elliptical arc
    -   [ImagickDraw::pathFinish](/class/imagickdraw.html#ImagickDraw::pathFinish)
        — Terminates the current path
    -   [ImagickDraw::pathLineToAbsolute](/class/imagickdraw.html#ImagickDraw::pathLineToAbsolute)
        — Draws a line path
    -   [ImagickDraw::pathLineToHorizontalAbsolute](/class/imagickdraw.html#ImagickDraw::pathLineToHorizontalAbsolute)
        — Draws a horizontal line path
    -   [ImagickDraw::pathLineToHorizontalRelative](/class/imagickdraw.html#ImagickDraw::pathLineToHorizontalRelative)
        — Draws a horizontal line
    -   [ImagickDraw::pathLineToRelative](/class/imagickdraw.html#ImagickDraw::pathLineToRelative)
        — Draws a line path
    -   [ImagickDraw::pathLineToVerticalAbsolute](/class/imagickdraw.html#ImagickDraw::pathLineToVerticalAbsolute)
        — Draws a vertical line
    -   [ImagickDraw::pathLineToVerticalRelative](/class/imagickdraw.html#ImagickDraw::pathLineToVerticalRelative)
        — Draws a vertical line path
    -   [ImagickDraw::pathMoveToAbsolute](/class/imagickdraw.html#ImagickDraw::pathMoveToAbsolute)
        — Starts a new sub-path
    -   [ImagickDraw::pathMoveToRelative](/class/imagickdraw.html#ImagickDraw::pathMoveToRelative)
        — Starts a new sub-path
    -   [ImagickDraw::pathStart](/class/imagickdraw.html#ImagickDraw::pathStart)
        — Declares the start of a path drawing list
    -   [ImagickDraw::point](/class/imagickdraw.html#ImagickDraw::point)
        — Draws a point
    -   [ImagickDraw::polygon](/class/imagickdraw.html#ImagickDraw::polygon)
        — Draws a polygon
    -   [ImagickDraw::polyline](/class/imagickdraw.html#ImagickDraw::polyline)
        — Draws a polyline
    -   [ImagickDraw::pop](/class/imagickdraw.html#ImagickDraw::pop) —
        Destroys the current ImagickDraw in the stack, and returns to
        the previously pushed ImagickDraw
    -   [ImagickDraw::popClipPath](/class/imagickdraw.html#ImagickDraw::popClipPath)
        — Terminates a clip path definition
    -   [ImagickDraw::popDefs](/class/imagickdraw.html#ImagickDraw::popDefs)
        — Terminates a definition list
    -   [ImagickDraw::popPattern](/class/imagickdraw.html#ImagickDraw::popPattern)
        — Terminates a pattern definition
    -   [ImagickDraw::push](/class/imagickdraw.html#ImagickDraw::push) —
        Clones the current ImagickDraw and pushes it to the stack
    -   [ImagickDraw::pushClipPath](/class/imagickdraw.html#ImagickDraw::pushClipPath)
        — Starts a clip path definition
    -   [ImagickDraw::pushDefs](/class/imagickdraw.html#ImagickDraw::pushDefs)
        — Indicates that following commands create named elements for
        early processing
    -   [ImagickDraw::pushPattern](/class/imagickdraw.html#ImagickDraw::pushPattern)
        — Indicates that subsequent commands up to a
        ImagickDraw::opPattern() command comprise the definition of a
        named pattern
    -   [ImagickDraw::rectangle](/class/imagickdraw.html#ImagickDraw::rectangle)
        — Draws a rectangle
    -   [ImagickDraw::render](/class/imagickdraw.html#ImagickDraw::render)
        — Renders all preceding drawing commands onto the image
    -   [ImagickDraw::resetVectorGraphics](/class/imagickdraw.html#ImagickDraw::resetVectorGraphics)
        — Description
    -   [ImagickDraw::rotate](/class/imagickdraw.html#ImagickDraw::rotate)
        — Applies the specified rotation to the current coordinate space
    -   [ImagickDraw::roundRectangle](/class/imagickdraw.html#ImagickDraw::roundRectangle)
        — Draws a rounded rectangle
    -   [ImagickDraw::scale](/class/imagickdraw.html#ImagickDraw::scale)
        — Adjusts the scaling factor
    -   [ImagickDraw::setClipPath](/class/imagickdraw.html#ImagickDraw::setClipPath)
        — Associates a named clipping path with the image
    -   [ImagickDraw::setClipRule](/class/imagickdraw.html#ImagickDraw::setClipRule)
        — Set the polygon fill rule to be used by the clipping path
    -   [ImagickDraw::setClipUnits](/class/imagickdraw.html#ImagickDraw::setClipUnits)
        — Sets the interpretation of clip path units
    -   [ImagickDraw::setFillAlpha](/class/imagickdraw.html#ImagickDraw::setFillAlpha)
        — Sets the opacity to use when drawing using the fill color or
        fill texture
    -   [ImagickDraw::setFillColor](/class/imagickdraw.html#ImagickDraw::setFillColor)
        — Sets the fill color to be used for drawing filled objects
    -   [ImagickDraw::setFillOpacity](/class/imagickdraw.html#ImagickDraw::setFillOpacity)
        — Sets the opacity to use when drawing using the fill color or
        fill texture
    -   [ImagickDraw::setFillPatternURL](/class/imagickdraw.html#ImagickDraw::setFillPatternURL)
        — Sets the URL to use as a fill pattern for filling objects
    -   [ImagickDraw::setFillRule](/class/imagickdraw.html#ImagickDraw::setFillRule)
        — Sets the fill rule to use while drawing polygons
    -   [ImagickDraw::setFont](/class/imagickdraw.html#ImagickDraw::setFont)
        — Sets the fully-specified font to use when annotating with text
    -   [ImagickDraw::setFontFamily](/class/imagickdraw.html#ImagickDraw::setFontFamily)
        — Sets the font family to use when annotating with text
    -   [ImagickDraw::setFontSize](/class/imagickdraw.html#ImagickDraw::setFontSize)
        — Sets the font pointsize to use when annotating with text
    -   [ImagickDraw::setFontStretch](/class/imagickdraw.html#ImagickDraw::setFontStretch)
        — Sets the font stretch to use when annotating with text
    -   [ImagickDraw::setFontStyle](/class/imagickdraw.html#ImagickDraw::setFontStyle)
        — Sets the font style to use when annotating with text
    -   [ImagickDraw::setFontWeight](/class/imagickdraw.html#ImagickDraw::setFontWeight)
        — Sets the font weight
    -   [ImagickDraw::setGravity](/class/imagickdraw.html#ImagickDraw::setGravity)
        — Sets the text placement gravity
    -   [ImagickDraw::setResolution](/class/imagickdraw.html#ImagickDraw::setResolution)
        — Description
    -   [ImagickDraw::setStrokeAlpha](/class/imagickdraw.html#ImagickDraw::setStrokeAlpha)
        — Specifies the opacity of stroked object outlines
    -   [ImagickDraw::setStrokeAntialias](/class/imagickdraw.html#ImagickDraw::setStrokeAntialias)
        — Controls whether stroked outlines are antialiased
    -   [ImagickDraw::setStrokeColor](/class/imagickdraw.html#ImagickDraw::setStrokeColor)
        — Sets the color used for stroking object outlines
    -   [ImagickDraw::setStrokeDashArray](/class/imagickdraw.html#ImagickDraw::setStrokeDashArray)
        — Specifies the pattern of dashes and gaps used to stroke paths
    -   [ImagickDraw::setStrokeDashOffset](/class/imagickdraw.html#ImagickDraw::setStrokeDashOffset)
        — Specifies the offset into the dash pattern to start the dash
    -   [ImagickDraw::setStrokeLineCap](/class/imagickdraw.html#ImagickDraw::setStrokeLineCap)
        — Specifies the shape to be used at the end of open subpaths
        when they are stroked
    -   [ImagickDraw::setStrokeLineJoin](/class/imagickdraw.html#ImagickDraw::setStrokeLineJoin)
        — Specifies the shape to be used at the corners of paths when
        they are stroked
    -   [ImagickDraw::setStrokeMiterLimit](/class/imagickdraw.html#ImagickDraw::setStrokeMiterLimit)
        — Specifies the miter limit
    -   [ImagickDraw::setStrokeOpacity](/class/imagickdraw.html#ImagickDraw::setStrokeOpacity)
        — Specifies the opacity of stroked object outlines
    -   [ImagickDraw::setStrokePatternURL](/class/imagickdraw.html#ImagickDraw::setStrokePatternURL)
        — Sets the pattern used for stroking object outlines
    -   [ImagickDraw::setStrokeWidth](/class/imagickdraw.html#ImagickDraw::setStrokeWidth)
        — Sets the width of the stroke used to draw object outlines
    -   [ImagickDraw::setTextAlignment](/class/imagickdraw.html#ImagickDraw::setTextAlignment)
        — Specifies a text alignment
    -   [ImagickDraw::setTextAntialias](/class/imagickdraw.html#ImagickDraw::setTextAntialias)
        — Controls whether text is antialiased
    -   [ImagickDraw::setTextDecoration](/class/imagickdraw.html#ImagickDraw::setTextDecoration)
        — Specifies a decoration
    -   [ImagickDraw::setTextEncoding](/class/imagickdraw.html#ImagickDraw::setTextEncoding)
        — Specifies the text code set
    -   [ImagickDraw::setTextInterlineSpacing](/class/imagickdraw.html#ImagickDraw::setTextInterlineSpacing)
        — Description
    -   [ImagickDraw::setTextInterwordSpacing](/class/imagickdraw.html#ImagickDraw::setTextInterwordSpacing)
        — Description
    -   [ImagickDraw::setTextKerning](/class/imagickdraw.html#ImagickDraw::setTextKerning)
        — Description
    -   [ImagickDraw::setTextUnderColor](/class/imagickdraw.html#ImagickDraw::setTextUnderColor)
        — Specifies the color of a background rectangle
    -   [ImagickDraw::setVectorGraphics](/class/imagickdraw.html#ImagickDraw::setVectorGraphics)
        — Sets the vector graphics
    -   [ImagickDraw::setViewbox](/class/imagickdraw.html#ImagickDraw::setViewbox)
        — Sets the overall canvas size
    -   [ImagickDraw::skewX](/class/imagickdraw.html#ImagickDraw::skewX)
        — Skews the current coordinate system in the horizontal
        direction
    -   [ImagickDraw::skewY](/class/imagickdraw.html#ImagickDraw::skewY)
        — Skews the current coordinate system in the vertical direction
    -   [ImagickDraw::translate](/class/imagickdraw.html#ImagickDraw::translate)
        — Applies a translation to the current coordinate system
-   [ImagickPixel](/class/imagickpixel.html) — The ImagickPixel class
    -   [ImagickPixel::clear](/class/imagickpixel.html#ImagickPixel::clear)
        — Clears resources associated with this object
    -   [ImagickPixel::\_\_construct](/class/imagickpixel.html#ImagickPixel::__construct)
        — The ImagickPixel constructor
    -   [ImagickPixel::destroy](/class/imagickpixel.html#ImagickPixel::destroy)
        — Deallocates resources associated with this object
    -   [ImagickPixel::getColor](/class/imagickpixel.html#ImagickPixel::getColor)
        — Returns the color
    -   [ImagickPixel::getColorAsString](/class/imagickpixel.html#ImagickPixel::getColorAsString)
        — Returns the color as a string
    -   [ImagickPixel::getColorCount](/class/imagickpixel.html#ImagickPixel::getColorCount)
        — Returns the color count associated with this color
    -   [ImagickPixel::getColorQuantum](/class/imagickpixel.html#ImagickPixel::getColorQuantum)
        — Description
    -   [ImagickPixel::getColorValue](/class/imagickpixel.html#ImagickPixel::getColorValue)
        — Gets the normalized value of the provided color channel
    -   [ImagickPixel::getColorValueQuantum](/class/imagickpixel.html#ImagickPixel::getColorValueQuantum)
        — Description
    -   [ImagickPixel::getHSL](/class/imagickpixel.html#ImagickPixel::getHSL)
        — Returns the normalized HSL color of the ImagickPixel object
    -   [ImagickPixel::getIndex](/class/imagickpixel.html#ImagickPixel::getIndex)
        — Description
    -   [ImagickPixel::isPixelSimilar](/class/imagickpixel.html#ImagickPixel::isPixelSimilar)
        — Check the distance between this color and another
    -   [ImagickPixel::isPixelSimilarQuantum](/class/imagickpixel.html#ImagickPixel::isPixelSimilarQuantum)
        — Description
    -   [ImagickPixel::isSimilar](/class/imagickpixel.html#ImagickPixel::isSimilar)
        — Check the distance between this color and another
    -   [ImagickPixel::setColor](/class/imagickpixel.html#ImagickPixel::setColor)
        — Sets the color
    -   [ImagickPixel::setColorCount](/class/imagickpixel.html#ImagickPixel::setColorCount)
        — Description
    -   [ImagickPixel::setColorValue](/class/imagickpixel.html#ImagickPixel::setColorValue)
        — Sets the normalized value of one of the channels
    -   [ImagickPixel::setColorValueQuantum](/class/imagickpixel.html#ImagickPixel::setColorValueQuantum)
        — Description
    -   [ImagickPixel::setHSL](/class/imagickpixel.html#ImagickPixel::setHSL)
        — Sets the normalized HSL color
    -   [ImagickPixel::setIndex](/class/imagickpixel.html#ImagickPixel::setIndex)
        — Description
-   [ImagickPixelIterator](/class/imagickpixeliterator.html) — The
    ImagickPixelIterator class
    -   [ImagickPixelIterator::clear](/class/imagickpixeliterator.html#ImagickPixelIterator::clear)
        — Clear resources associated with a PixelIterator
    -   [ImagickPixelIterator::\_\_construct](/class/imagickpixeliterator.html#ImagickPixelIterator::__construct)
        — The ImagickPixelIterator constructor
    -   [ImagickPixelIterator::destroy](/class/imagickpixeliterator.html#ImagickPixelIterator::destroy)
        — Deallocates resources associated with a PixelIterator
    -   [ImagickPixelIterator::getCurrentIteratorRow](/class/imagickpixeliterator.html#ImagickPixelIterator::getCurrentIteratorRow)
        — Returns the current row of ImagickPixel objects
    -   [ImagickPixelIterator::getIteratorRow](/class/imagickpixeliterator.html#ImagickPixelIterator::getIteratorRow)
        — Returns the current pixel iterator row
    -   [ImagickPixelIterator::getNextIteratorRow](/class/imagickpixeliterator.html#ImagickPixelIterator::getNextIteratorRow)
        — Returns the next row of the pixel iterator
    -   [ImagickPixelIterator::getPreviousIteratorRow](/class/imagickpixeliterator.html#ImagickPixelIterator::getPreviousIteratorRow)
        — Returns the previous row
    -   [ImagickPixelIterator::newPixelIterator](/class/imagickpixeliterator.html#ImagickPixelIterator::newPixelIterator)
        — Returns a new pixel iterator
    -   [ImagickPixelIterator::newPixelRegionIterator](/class/imagickpixeliterator.html#ImagickPixelIterator::newPixelRegionIterator)
        — Returns a new pixel iterator
    -   [ImagickPixelIterator::resetIterator](/class/imagickpixeliterator.html#ImagickPixelIterator::resetIterator)
        — Resets the pixel iterator
    -   [ImagickPixelIterator::setIteratorFirstRow](/class/imagickpixeliterator.html#ImagickPixelIterator::setIteratorFirstRow)
        — Sets the pixel iterator to the first pixel row
    -   [ImagickPixelIterator::setIteratorLastRow](/class/imagickpixeliterator.html#ImagickPixelIterator::setIteratorLastRow)
        — Sets the pixel iterator to the last pixel row
    -   [ImagickPixelIterator::setIteratorRow](/class/imagickpixeliterator.html#ImagickPixelIterator::setIteratorRow)
        — Set the pixel iterator row
    -   [ImagickPixelIterator::syncIterator](/class/imagickpixeliterator.html#ImagickPixelIterator::syncIterator)
        — Syncs the pixel iterator
-   [ImagickKernel](/class/imagickkernel.html) — The ImagickKernel class
    -   [ImagickKernel::addKernel](/class/imagickkernel.html#ImagickKernel::addKernel)
        — Description
    -   [ImagickKernel::addUnityKernel](/class/imagickkernel.html#ImagickKernel::addUnityKernel)
        — Description
    -   [ImagickKernel::fromBuiltIn](/class/imagickkernel.html#ImagickKernel::fromBuiltIn)
        — Description
    -   [ImagickKernel::fromMatrix](/class/imagickkernel.html#ImagickKernel::fromMatrix)
        — Description
    -   [ImagickKernel::getMatrix](/class/imagickkernel.html#ImagickKernel::getMatrix)
        — Description
    -   [ImagickKernel::scale](/class/imagickkernel.html#ImagickKernel::scale)
        — Description
    -   [ImagickKernel::separate](/class/imagickkernel.html#ImagickKernel::separate)
        — Description

Class synopsis
--------------

**Imagick**

<span class="ooclass"> class **Imagick**</span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">adaptiveBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">adaptiveResizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$bestfit`<span class="initializer"> = **`false`**</span></span> \[,
<span class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">adaptiveSharpenImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">adaptiveThresholdImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span>
`$offset`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$source`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addNoiseImage</span> ( <span
class="methodparam"><span class="type">int</span> `$noise_type`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">affineTransformImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$matrix`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">animateImages</span> ( <span
class="methodparam"><span class="type">string</span> `$x_server`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">annotateImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$draw_settings`</span> , <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">appendImages</span> ( <span
class="methodparam"><span class="type">bool</span> `$stack`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">autoLevelImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">averageImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">blackThresholdImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$threshold`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">blueShiftImage</span> (\[ <span
class="methodparam"><span class="type">float</span> `$factor`<span
class="initializer"> = 1.5</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">blurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">borderImage</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">brightnessContrastImage</span> ( <span
class="methodparam"><span class="type">float</span> `$brightness`</span>
, <span class="methodparam"><span class="type">float</span>
`$contrast`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">charcoalImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">chopImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clampImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clipImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">clipImagePath</span> ( <span
class="methodparam"><span class="type">string</span> `$pathname`</span>
, <span class="methodparam"><span class="type">string</span>
`$inside`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clipPathImage</span> ( <span
class="methodparam"><span class="type">string</span> `$pathname`</span>
, <span class="methodparam"><span class="type">bool</span>
`$inside`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">clone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clutImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$lookup_table`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">coalesceImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">colorFloodfillImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">colorizeImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$colorize`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$opacity`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">colorMatrixImage</span> ( <span
class="methodparam"><span class="type">array</span> `$color_matrix`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">combineImages</span> ( <span
class="methodparam"><span class="type">int</span> `$channelType`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">commentImage</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">compareImageChannels</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span>
`$channelType`</span> , <span class="methodparam"><span
class="type">int</span> `$metricType`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">compareImageLayers</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">compareImages</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$compare`</span>
, <span class="methodparam"><span class="type">int</span>
`$metric`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">compositeImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$composite_object`</span> , <span class="methodparam"><span
class="type">int</span> `$composite`</span> , <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$files`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">contrastImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$sharpen`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">contrastStretchImage</span> ( <span
class="methodparam"><span class="type">float</span>
`$black_point`</span> , <span class="methodparam"><span
class="type">float</span> `$white_point`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">convolveImage</span> ( <span
class="methodparam"><span class="type">array</span> `$kernel`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> (\[ <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">cropImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">cropThumbnailImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$legacy`<span class="initializer"> = **`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">cycleColormapImage</span> ( <span
class="methodparam"><span class="type">int</span> `$displace`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">decipherImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">deconstructImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deskewImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">despeckleImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">displayImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$servername`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">displayImages</span> ( <span
class="methodparam"><span class="type">string</span>
`$servername`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">distortImage</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> ,
<span class="methodparam"><span class="type">array</span>
`$arguments`</span> , <span class="methodparam"><span
class="type">bool</span> `$bestfit`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">drawImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span> `$draw`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">edgeImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">embossImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">encipherImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">enhanceImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">equalizeImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">evaluateImage</span> ( <span
class="methodparam"><span class="type">int</span> `$op`</span> , <span
class="methodparam"><span class="type">float</span> `$constant`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">exportImagePixels</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">string</span>
`$map`</span> , <span class="methodparam"><span class="type">int</span>
`$STORAGE`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">extentImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">filter</span> ( <span class="methodparam"><span
class="type">ImagickKernel</span> `$ImagickKernel`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_UNDEFINED</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">flattenImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">flipImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">floodFillPaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$target`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">bool</span> `$invert`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">flopImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">forwardFourierTransformimage</span> ( <span
class="methodparam"><span class="type">bool</span> `$magnitude`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">frameImage</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$matte_color`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> ,
<span class="methodparam"><span class="type">int</span>
`$inner_bevel`</span> , <span class="methodparam"><span
class="type">int</span> `$outer_bevel`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">functionImage</span> ( <span
class="methodparam"><span class="type">int</span> `$function`</span> ,
<span class="methodparam"><span class="type">array</span>
`$arguments`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">fxImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$expression`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">gammaImage</span> ( <span
class="methodparam"><span class="type">float</span> `$gamma`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">gaussianBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getColorspace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCompression</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCompressionQuality</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getCopyright</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFont</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFormat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGravity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getHomeURL</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">getImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageAlphaChannel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageAttribute</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getImageBackgroundColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageBlob</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageBluePrimary</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getImageBorderColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageChannelDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getImageChannelDistortion</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$channel`</span> , <span
class="methodparam"><span class="type">int</span> `$metric`</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getImageChannelDistortions</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$metric`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageChannelExtrema</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageChannelKurtosis</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageChannelMean</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageChannelRange</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageChannelStatistics</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">getImageClipMask</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getImageColormapColor</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageColors</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageColorspace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageCompose</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageCompression</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageCompressionQuality</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageDelay</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageDepth</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageDispose</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getImageDistortion</span> ( <span
class="methodparam"><span class="type">MagickWand</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$metric`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageExtrema</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageFormat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getImageGamma</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageGeometry</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageGravity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageGreenPrimary</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageHeight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageHistogram</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageIndex</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageInterlaceScheme</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageInterpolateMethod</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageIterations</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageLength</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getImageMatte</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getImageMatteColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageMimeType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageOrientation</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImagePage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getImagePixelColor</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageProfiles</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$include_values`<span class="initializer"> = **`true`**</span></span>
\]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageProperties</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$include_values`<span class="initializer"> = **`true`**</span></span>
\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageRedPrimary</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">getImageRegion</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageRenderingIntent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageResolution</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImagesBlob</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageScene</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getImageSignature</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageTicksPerSecond</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getImageTotalInkDensity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageUnits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageVirtualPixelMethod</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getImageWhitePoint</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getImageWidth</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getInterlaceScheme</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getIteratorIndex</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getNumberImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getOption</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getPackageName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getPage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixelIterator</span> <span
class="methodname">getPixelIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixelIterator</span> <span
class="methodname">getPixelRegionIterator</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getPointSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getQuantum</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getQuantumDepth</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getQuantumRange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getRegistry</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getReleaseDate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getResource</span> ( <span class="methodparam"><span
class="type">int</span> `$type`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getResourceLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getSamplingFactors</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSizeOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">haldClutImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$clut`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasNextImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasPreviousImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">identifyFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$embedText`</span>
)

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">identifyImage</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$appendRawOutput`<span class="initializer"> = **`false`**</span></span>
\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">implodeImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">importImagePixels</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">string</span>
`$map`</span> , <span class="methodparam"><span class="type">int</span>
`$storage`</span> , <span class="methodparam"><span
class="type">array</span> `$pixels`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">inverseFourierTransformImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$complement`</span> , <span class="methodparam"><span
class="type">bool</span> `$magnitude`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">labelImage</span> ( <span
class="methodparam"><span class="type">string</span> `$label`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">levelImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$gamma`</span> , <span class="methodparam"><span
class="type">float</span> `$whitePoint`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">linearStretchImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$whitePoint`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">liquidRescaleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">float</span>
`$delta_x`</span> , <span class="methodparam"><span
class="type">float</span> `$rigidity`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">listRegistry</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">magnifyImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">mapImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$map`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$dither`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">matteFloodfillImage</span> ( <span
class="methodparam"><span class="type">float</span> `$alpha`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">medianFilterImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">mergeImageLayers</span> ( <span
class="methodparam"><span class="type">int</span> `$layer_method`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">minifyImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">modulateImage</span> ( <span
class="methodparam"><span class="type">float</span> `$brightness`</span>
, <span class="methodparam"><span class="type">float</span>
`$saturation`</span> , <span class="methodparam"><span
class="type">float</span> `$hue`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">montageImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span> `$draw`</span>
, <span class="methodparam"><span class="type">string</span>
`$tile_geometry`</span> , <span class="methodparam"><span
class="type">string</span> `$thumbnail_geometry`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> , <span
class="methodparam"><span class="type">string</span> `$frame`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">morphImages</span> ( <span
class="methodparam"><span class="type">int</span>
`$number_frames`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">morphology</span> ( <span
class="methodparam"><span class="type">int</span>
`$morphologyMethod`</span> , <span class="methodparam"><span
class="type">int</span> `$iterations`</span> , <span
class="methodparam"><span class="type">ImagickKernel</span>
`$ImagickKernel`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">mosaicImages</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">motionBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">negateImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$gray`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">newImage</span> ( <span
class="methodparam"><span class="type">int</span> `$cols`</span> , <span
class="methodparam"><span class="type">int</span> `$rows`</span> , <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$format`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">newPseudoImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">string</span>
`$pseudoString`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">nextImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">normalizeImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">oilPaintImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">opaquePaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$fill`</span>
, <span class="methodparam"><span class="type">float</span>
`$fuzz`</span> , <span class="methodparam"><span
class="type">bool</span> `$invert`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">optimizeImageLayers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">orderedPosterizeImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$threshold_map`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">paintFloodfillImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">paintOpaqueImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$fill`</span>
, <span class="methodparam"><span class="type">float</span>
`$fuzz`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">paintTransparentImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pingImage</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pingImageBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$image`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pingImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$fileName`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">polaroidImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$properties`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">posterizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$levels`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$dither`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">previewImages</span> ( <span
class="methodparam"><span class="type">int</span> `$preview`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">previousImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">profileImage</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$profile`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">quantizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$numberColors`</span>
, <span class="methodparam"><span class="type">int</span>
`$colorspace`</span> , <span class="methodparam"><span
class="type">int</span> `$treedepth`</span> , <span
class="methodparam"><span class="type">bool</span> `$dither`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$measureError`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">quantizeImages</span> ( <span
class="methodparam"><span class="type">int</span> `$numberColors`</span>
, <span class="methodparam"><span class="type">int</span>
`$colorspace`</span> , <span class="methodparam"><span
class="type">int</span> `$treedepth`</span> , <span
class="methodparam"><span class="type">bool</span> `$dither`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$measureError`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">queryFontMetrics</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$properties`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$multiline`</span>
\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">queryFonts</span> (\[ <span class="methodparam"><span
class="type">string</span> `$pattern`<span class="initializer"> =
"\*"</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">queryFormats</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">radialBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$angle`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">raiseImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">bool</span> `$raise`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">randomThresholdImage</span> ( <span
class="methodparam"><span class="type">float</span> `$low`</span> ,
<span class="methodparam"><span class="type">float</span> `$high`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readImage</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readImageBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$image`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$fileName`<span class="initializer"> =
**`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readImages</span> ( <span
class="methodparam"><span class="type">array</span> `$filenames`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">recolorImage</span> ( <span
class="methodparam"><span class="type">array</span> `$matrix`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reduceNoiseImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">remapImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">int</span> `$DITHER`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">removeImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">removeImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">render</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resampleImage</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> , <span
class="methodparam"><span class="type">int</span> `$filter`</span> ,
<span class="methodparam"><span class="type">float</span> `$blur`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resetImagePage</span> ( <span
class="methodparam"><span class="type">string</span> `$page`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">int</span> `$filter`</span>
, <span class="methodparam"><span class="type">float</span>
`$blur`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$bestfit`<span class="initializer"> =
**`false`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rollImage</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rotateImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
, <span class="methodparam"><span class="type">float</span>
`$degrees`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rotationalBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$angle`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">roundCorners</span> ( <span
class="methodparam"><span class="type">float</span> `$x_rounding`</span>
, <span class="methodparam"><span class="type">float</span>
`$y_rounding`</span> \[, <span class="methodparam"><span
class="type">float</span> `$stroke_width`<span class="initializer"> =
10</span></span> \[, <span class="methodparam"><span
class="type">float</span> `$displace`<span class="initializer"> =
5</span></span> \[, <span class="methodparam"><span
class="type">float</span> `$size_correction`<span class="initializer"> =
-6</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sampleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">scaleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$cols`</span> , <span
class="methodparam"><span class="type">int</span> `$rows`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$bestfit`<span
class="initializer"> = **`false`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">segmentImage</span> ( <span
class="methodparam"><span class="type">int</span> `$COLORSPACE`</span> ,
<span class="methodparam"><span class="type">float</span>
`$cluster_threshold`</span> , <span class="methodparam"><span
class="type">float</span> `$smooth_threshold`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$verbose`<span
class="initializer"> = **`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">selectiveBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$threshold`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">separateImageChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sepiaToneImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setBackgroundColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setColorspace</span> ( <span
class="methodparam"><span class="type">int</span> `$COLORSPACE`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCompression</span> ( <span
class="methodparam"><span class="type">int</span> `$compression`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCompressionQuality</span> ( <span
class="methodparam"><span class="type">int</span> `$quality`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFilename</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFirstIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFont</span> ( <span
class="methodparam"><span class="type">string</span> `$font`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$replace`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageAlphaChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
, <span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageAttribute</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageBackgroundColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageBias</span> ( <span
class="methodparam"><span class="type">float</span> `$bias`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setImageBiasQuantum</span> ( <span
class="methodparam"><span class="type">string</span> `$bias`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageBluePrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageBorderColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$border`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageChannelDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> ,
<span class="methodparam"><span class="type">int</span> `$depth`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageClipMask</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$clip_mask`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageColormapColor</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageColorspace</span> ( <span
class="methodparam"><span class="type">int</span> `$colorspace`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageCompose</span> ( <span
class="methodparam"><span class="type">int</span> `$compose`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageCompression</span> ( <span
class="methodparam"><span class="type">int</span> `$compression`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageCompressionQuality</span> ( <span
class="methodparam"><span class="type">int</span> `$quality`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageDelay</span> ( <span
class="methodparam"><span class="type">int</span> `$delay`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$depth`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageDispose</span> ( <span
class="methodparam"><span class="type">int</span> `$dispose`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageExtent</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageFilename</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageGamma</span> ( <span
class="methodparam"><span class="type">float</span> `$gamma`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageGreenPrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageInterlaceScheme</span> ( <span
class="methodparam"><span class="type">int</span>
`$interlace_scheme`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageInterpolateMethod</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageIterations</span> ( <span
class="methodparam"><span class="type">int</span> `$iterations`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageMatte</span> ( <span
class="methodparam"><span class="type">bool</span> `$matte`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageMatteColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$matte`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageOpacity</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageOrientation</span> ( <span
class="methodparam"><span class="type">int</span> `$orientation`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImagePage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$profile`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageRedPrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageRenderingIntent</span> ( <span
class="methodparam"><span class="type">int</span>
`$rendering_intent`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageScene</span> ( <span
class="methodparam"><span class="type">int</span> `$scene`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageTicksPerSecond</span> ( <span
class="methodparam"><span class="type">int</span>
`$ticks_per_second`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageType</span> ( <span
class="methodparam"><span class="type">int</span> `$image_type`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageUnits</span> ( <span
class="methodparam"><span class="type">int</span> `$units`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageVirtualPixelMethod</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setImageWhitePoint</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setInterlaceScheme</span> ( <span
class="methodparam"><span class="type">int</span>
`$interlace_scheme`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIteratorIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setLastIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setOption</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setPage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setPointSize</span> ( <span
class="methodparam"><span class="type">float</span> `$point_size`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setProgressMonitor</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setRegistry</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setResourceLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">int</span> `$limit`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSamplingFactors</span> ( <span
class="methodparam"><span class="type">array</span> `$factors`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSizeOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setType</span> ( <span
class="methodparam"><span class="type">int</span> `$image_type`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">shadeImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$gray`</span> ,
<span class="methodparam"><span class="type">float</span>
`$azimuth`</span> , <span class="methodparam"><span
class="type">float</span> `$elevation`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">shadowImage</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sharpenImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">shaveImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">shearImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
, <span class="methodparam"><span class="type">float</span>
`$x_shear`</span> , <span class="methodparam"><span
class="type">float</span> `$y_shear`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sigmoidalContrastImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$sharpen`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$beta`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sketchImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">smushImages</span> ( <span
class="methodparam"><span class="type">bool</span> `$stack`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">solarizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$threshold`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">sparseColorImage</span> ( <span
class="methodparam"><span class="type">int</span>
`$SPARSE_METHOD`</span> , <span class="methodparam"><span
class="type">array</span> `$arguments`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">spliceImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">spreadImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">statisticImage</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">steganoImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$watermark_wand`</span> , <span class="methodparam"><span
class="type">int</span> `$offset`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">stereoImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$offset_wand`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">stripImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">subImageMatch</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$Imagick`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$offset`</span> \[, <span class="methodparam"><span
class="type">float</span> `&$similarity`</span> \]\] )

<span class="type">bool</span> <span
class="methodname">swirlImage</span> ( <span class="methodparam"><span
class="type">float</span> `$degrees`</span> )

<span class="type">Imagick</span> <span
class="methodname">textureImage</span> ( <span class="methodparam"><span
class="type">Imagick</span> `$texture_wand`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">thresholdImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">thumbnailImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$bestfit`<span class="initializer"> = **`false`**</span></span> \[,
<span class="methodparam"><span class="type">bool</span> `$fill`<span
class="initializer"> = **`false`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$tint`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$opacity`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">transformImage</span> ( <span
class="methodparam"><span class="type">string</span> `$crop`</span> ,
<span class="methodparam"><span class="type">string</span>
`$geometry`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">transformImageColorspace</span> ( <span
class="methodparam"><span class="type">int</span> `$colorspace`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">transparentPaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> , <span
class="methodparam"><span class="type">bool</span> `$invert`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">transposeImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">transverseImage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">trimImage</span> ( <span
class="methodparam"><span class="type">float</span> `$fuzz`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">uniqueImageColors</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unsharpMaskImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$amount`</span> , <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">vignetteImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$whitePoint`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">waveImage</span> ( <span
class="methodparam"><span class="type">float</span> `$amplitude`</span>
, <span class="methodparam"><span class="type">float</span>
`$length`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">whiteThresholdImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$threshold`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writeImage</span> (\[ <span
class="methodparam"><span class="type">string</span> `$filename`<span
class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writeImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$format`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writeImages</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">bool</span>
`$adjoin`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writeImagesFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$format`</span> \] )

}

Image methods and global methods
--------------------------------

The Imagick class has the ability to hold and operate on multiple images
simultaneously. This is achieved through an internal stack. There is
always an internal pointer that points at the current image. Some
functions operate on all images in the Imagick class, but most operate
only on the current image in the internal stack. As a convention, method
names can contain the word Image to denote they affect only the current
image in the stack.

Class Methods
-------------

Because there are so many methods, here is a handy list of methods,
somewhat reduced to their general purpose:

| Image effects                                                   | Get methods                                                         | Set methods                                                         | Read/write images                                         | Other                                                       |
|-----------------------------------------------------------------|---------------------------------------------------------------------|---------------------------------------------------------------------|-----------------------------------------------------------|-------------------------------------------------------------|
| <span class="methodname">Imagick::adaptiveBlurImage</span>      | <span class="methodname">Imagick::getCompression</span>             | <span class="methodname">Imagick::setBackgroundColor</span>         | <span class="methodname">Imagick::\_\_construct</span>    | <span class="methodname">Imagick::clear</span>              |
| <span class="methodname">Imagick::adaptiveResizeImage</span>    | <span class="methodname">Imagick::getFilename</span>                | <span class="methodname">Imagick::setCompressionQuality</span>      | <span class="methodname">Imagick::addImage</span>         | <span class="methodname">Imagick::clone</span>              |
| <span class="methodname">Imagick::adaptiveSharpenImage</span>   | <span class="methodname">Imagick::getFormat</span>                  | <span class="methodname">Imagick::setCompression</span>             | <span class="methodname">Imagick::appendImages</span>     | <span class="methodname">Imagick::current</span>            |
| <span class="methodname">Imagick::adaptiveThresholdImage</span> | <span class="methodname">Imagick::getImageBackgroundColor</span>    | <span class="methodname">Imagick::setFilename</span>                | <span class="methodname">Imagick::getFilename</span>      | <span class="methodname">Imagick::destroy</span>            |
| <span class="methodname">Imagick::addNoiseImage</span>          | <span class="methodname">Imagick::getImageBlob</span>               | <span class="methodname">Imagick::getImagesBlob</span>              | <span class="methodname">Imagick::setFormat</span>        | <span class="methodname">Imagick::getFormat</span>          |
| <span class="methodname">Imagick::affinetransformimage</span>   | <span class="methodname">Imagick::getImageBluePrimary</span>        | <span class="methodname">Imagick::setImageBackgroundColor</span>    | <span class="methodname">Imagick::getImageFilename</span> | <span class="methodname">Imagick::getHomeURL</span>         |
| <span class="methodname">Imagick::annotateImage</span>          | <span class="methodname">Imagick::getImageBorderColor</span>        | <span class="methodname">Imagick::setFirstIterator</span>           | <span class="methodname">Imagick::getImageFormat</span>   | <span class="methodname">Imagick::commentImage</span>       |
| <span class="methodname">Imagick::averageImages</span>          | <span class="methodname">Imagick::getImageChannelDepth</span>       | <span class="methodname">Imagick::setImageBias</span>               | <span class="methodname">Imagick::getImage</span>         | <span class="methodname">Imagick::getNumberImages</span>    |
| <span class="methodname">Imagick::blackThresholdImage</span>    | <span class="methodname">Imagick::getImageChannelDistortion</span>  | <span class="methodname">Imagick::setImageBluePrimary</span>        | <span class="methodname">Imagick::setImageFilename</span> | <span class="methodname">Imagick::getReleaseDate</span>     |
| <span class="methodname">Imagick::blurImage</span>              | <span class="methodname">Imagick::getImageChannelExtrema</span>     | <span class="methodname">Imagick::setImageBorderColor</span>        | <span class="methodname">Imagick::setImageFormat</span>   | <span class="methodname">Imagick::getVersion</span>         |
| <span class="methodname">Imagick::borderImage</span>            | <span class="methodname">Imagick::getImageChannelMean</span>        | <span class="methodname">Imagick::setImageChannelDepth</span>       | <span class="methodname">Imagick::readImageFile</span>    | <span class="methodname">Imagick::hasNextImage</span>       |
| <span class="methodname">Imagick::charcoalImage</span>          | <span class="methodname">Imagick::getImageChannelStatistics</span>  | <span class="methodname">Imagick::setImageColormapColor</span>      | <span class="methodname">Imagick::readImage</span>        | <span class="methodname">Imagick::hasPreviousImage</span>   |
| <span class="methodname">Imagick::chopImage</span>              | <span class="methodname">Imagick::getImageColormapColor</span>      | <span class="methodname">Imagick::setImageColorSpace</span>         | <span class="methodname">Imagick::writeImages</span>      | <span class="methodname">Imagick::labelImage</span>         |
| <span class="methodname">Imagick::clipImage</span>              | <span class="methodname">Imagick::getImageColorspace</span>         | <span class="methodname">Imagick::setImageCompose</span>            | <span class="methodname">Imagick::writeImage</span>       | <span class="methodname">Imagick::newImage</span>           |
| <span class="methodname">Imagick::clipPathImage</span>          | <span class="methodname">Imagick::getImageColors</span>             | <span class="methodname">Imagick::setImageCompression</span>        |                                                           | <span class="methodname">Imagick::newPseudoImage</span>     |
| <span class="methodname">Imagick::coalesceImages</span>         | <span class="methodname">Imagick::getImageCompose</span>            | <span class="methodname">Imagick::setImageDelay</span>              |                                                           | <span class="methodname">Imagick::nextImage</span>          |
| <span class="methodname">Imagick::colorFloodFillImage</span>    | <span class="methodname">Imagick::getImageDelay</span>              | <span class="methodname">Imagick::setImageDepth</span>              |                                                           | <span class="methodname">Imagick::pingImageBlob</span>      |
| <span class="methodname">Imagick::colorizeImage</span>          | <span class="methodname">Imagick::getImageDepth</span>              | <span class="methodname">Imagick::setImageDispose</span>            |                                                           | <span class="methodname">Imagick::pingImageFile</span>      |
| <span class="methodname">Imagick::combineImages</span>          | <span class="methodname">Imagick::getImageDispose</span>            | <span class="methodname">Imagick::setImageDispose</span>            |                                                           | <span class="methodname">Imagick::pingImage</span>          |
| <span class="methodname">Imagick::compareImageChannels</span>   | <span class="methodname">Imagick::getImageDistortion</span>         | <span class="methodname">Imagick::setImageExtent</span>             |                                                           | <span class="methodname">Imagick::previousImage</span>      |
| <span class="methodname">Imagick::compareImageLayers</span>     | <span class="methodname">Imagick::getImageExtrema</span>            | <span class="methodname">Imagick::setImageFilename</span>           |                                                           | <span class="methodname">Imagick::profileImage</span>       |
| <span class="methodname">Imagick::compositeImage</span>         | <span class="methodname">Imagick::getImageFilename</span>           | <span class="methodname">Imagick::setImageFormat</span>             |                                                           | <span class="methodname">Imagick::queryFormats</span>       |
| <span class="methodname">Imagick::contrastImage</span>          | <span class="methodname">Imagick::getImageFormat</span>             | <span class="methodname">Imagick::setImageGamma</span>              |                                                           | <span class="methodname">Imagick::removeImageProfile</span> |
| <span class="methodname">Imagick::contrastStretchImage</span>   | <span class="methodname">Imagick::getImageGamma</span>              | <span class="methodname">Imagick::setImageGreenPrimary</span>       |                                                           | <span class="methodname">Imagick::removeImage</span>        |
| <span class="methodname">Imagick::convolveImage</span>          | <span class="methodname">Imagick::getImageGeometry</span>           | <span class="methodname">Imagick::setImageIndex</span>              |                                                           | <span class="methodname">Imagick::setFirstIterator</span>   |
| <span class="methodname">Imagick::cropImage</span>              | <span class="methodname">Imagick::getImageGreenPrimary</span>       | <span class="methodname">Imagick::setImageInterpolateMethod</span>  |                                                           | <span class="methodname">Imagick::setImageIndex</span>      |
| <span class="methodname">Imagick::cycleColormapImage</span>     | <span class="methodname">Imagick::getImageHeight</span>             | <span class="methodname">Imagick::setImageIterations</span>         |                                                           | <span class="methodname">Imagick::valid</span>              |
| <span class="methodname">Imagick::deconstructImages</span>      | <span class="methodname">Imagick::getImageHistogram</span>          | <span class="methodname">Imagick::setImageMatteColor</span>         |                                                           | <span class="methodname">Imagick::getCopyright</span>       |
| <span class="methodname">Imagick::drawImage</span>              | <span class="methodname">Imagick::getImageIndex</span>              | <span class="methodname">Imagick::setImageMatte</span>              |                                                           |                                                             |
| <span class="methodname">Imagick::edgeImage</span>              | <span class="methodname">Imagick::getImageInterlaceScheme</span>    | <span class="methodname">Imagick::setImagePage</span>               |                                                           |                                                             |
| <span class="methodname">Imagick::embossImage</span>            | <span class="methodname">Imagick::getImageInterpolateMethod</span>  | <span class="methodname">Imagick::setImageProfile</span>            |                                                           |                                                             |
| <span class="methodname">Imagick::enhanceImage</span>           | <span class="methodname">Imagick::getImageIterations</span>         | <span class="methodname">Imagick::setImageProperty</span>           |                                                           |                                                             |
| <span class="methodname">Imagick::equalizeImage</span>          | <span class="methodname">Imagick::getImageMatteColor</span>         | <span class="methodname">Imagick::setImageRedPrimary</span>         |                                                           |                                                             |
| <span class="methodname">Imagick::evaluateImage</span>          | <span class="methodname">Imagick::getImageMatte</span>              | <span class="methodname">Imagick::setImageRenderingIntent</span>    |                                                           |                                                             |
| <span class="methodname">Imagick::flattenImages</span>          | <span class="methodname">Imagick::getImagePage</span>               | <span class="methodname">Imagick::setImageResolution</span>         |                                                           |                                                             |
| <span class="methodname">Imagick::flipImage</span>              | <span class="methodname">Imagick::getImagePixelColor</span>         | <span class="methodname">Imagick::setImageScene</span>              |                                                           |                                                             |
| <span class="methodname">Imagick::flopImage</span>              | <span class="methodname">Imagick::getImageProfile</span>            | <span class="methodname">Imagick::setImageTicksPerSecond</span>     |                                                           |                                                             |
|                                                                 | <span class="methodname">Imagick::getImageProperty</span>           | <span class="methodname">Imagick::setImageType</span>               |                                                           |                                                             |
| <span class="methodname">Imagick::fxImage</span>                | <span class="methodname">Imagick::getImageRedPrimary</span>         | <span class="methodname">Imagick::setImageUnits</span>              |                                                           |                                                             |
| <span class="methodname">Imagick::gammaImage</span>             | <span class="methodname">Imagick::getImageRegion</span>             | <span class="methodname">Imagick::setImageVirtualPixelMethod</span> |                                                           |                                                             |
| <span class="methodname">Imagick::gaussianBlurImage</span>      | <span class="methodname">Imagick::getImageRenderingIntent</span>    | <span class="methodname">Imagick::setImageWhitepoint</span>         |                                                           |                                                             |
| <span class="methodname">Imagick::implodeImage</span>           | <span class="methodname">Imagick::getImageResolution</span>         | <span class="methodname">Imagick::setInterlaceScheme</span>         |                                                           |                                                             |
| <span class="methodname">Imagick::levelImage</span>             | <span class="methodname">Imagick::getImageScene</span>              | <span class="methodname">Imagick::setOption</span>                  |                                                           |                                                             |
| <span class="methodname">Imagick::linearStretchImage</span>     | <span class="methodname">Imagick::getImageSignature</span>          | <span class="methodname">Imagick::setPage</span>                    |                                                           |                                                             |
| <span class="methodname">Imagick::magnifyImage</span>           | <span class="methodname">Imagick::getImageTicksPerSecond</span>     | <span class="methodname">Imagick::setResolution</span>              |                                                           |                                                             |
| <span class="methodname">Imagick::matteFloodFillImage</span>    | <span class="methodname">Imagick::getImageTotalInkDensity</span>    | <span class="methodname">Imagick::setResourceLimit</span>           |                                                           |                                                             |
| <span class="methodname">Imagick::medianFilterImage</span>      | <span class="methodname">Imagick::getImageType</span>               | <span class="methodname">Imagick::setSamplingFactors</span>         |                                                           |                                                             |
| <span class="methodname">Imagick::minifyImage</span>            | <span class="methodname">Imagick::getImageUnits</span>              | <span class="methodname">Imagick::setSizeOffset</span>              |                                                           |                                                             |
| <span class="methodname">Imagick::modulateImage</span>          | <span class="methodname">Imagick::getImageVirtualPixelMethod</span> | <span class="methodname">Imagick::setSize</span>                    |                                                           |                                                             |
| <span class="methodname">Imagick::montageImage</span>           | <span class="methodname">Imagick::getImageWhitepoint</span>         | <span class="methodname">Imagick::setType</span>                    |                                                           |                                                             |
| <span class="methodname">Imagick::morphImages</span>            | <span class="methodname">Imagick::getImageWidth</span>              |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::mosaicImages</span>           | <span class="methodname">Imagick::getImage</span>                   |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::motionBlurImage</span>        | <span class="methodname">Imagick::getInterlaceScheme</span>         |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::negateImage</span>            | <span class="methodname">Imagick::getNumberImages</span>            |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::normalizeImage</span>         | <span class="methodname">Imagick::getOption</span>                  |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::oilPaintImage</span>          | <span class="methodname">Imagick::getPackageName</span>             |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::optimizeImageLayers</span>    | <span class="methodname">Imagick::getPage</span>                    |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::paintOpaqueImage</span>       | <span class="methodname">Imagick::getPixelIterator</span>           |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::paintTransparentImage</span>  | <span class="methodname">Imagick::getPixelRegionIterator</span>     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::posterizeImage</span>         | <span class="methodname">Imagick::getQuantumDepth</span>            |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::radialBlurImage</span>        | <span class="methodname">Imagick::getQuantumRange</span>            |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::raiseImage</span>             | <span class="methodname">Imagick::getResourceLimit</span>           |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::randomThresholdImage</span>   | <span class="methodname">Imagick::getResource</span>                |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::reduceNoiseImage</span>       | <span class="methodname">Imagick::getSamplingFactors</span>         |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::render</span>                 | <span class="methodname">Imagick::getSizeOffset</span>              |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::resampleImage</span>          | <span class="methodname">Imagick::getSize</span>                    |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::resizeImage</span>            | <span class="methodname">Imagick::identifyImage</span>              |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::rollImage</span>              | <span class="methodname">Imagick::getImageSize</span>               |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::rotateImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::sampleImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::scaleImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::separateImageChannel</span>   |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::sepiaToneImage</span>         |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::shadeImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::shadowImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::sharpenImage</span>           |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::shaveImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::shearImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::sigmoidalContrastImage</span> |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::sketchImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::solarizeImage</span>          |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::spliceImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::spreadImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::steganoImage</span>           |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::stereoImage</span>            |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::stripImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::swirlImage</span>             |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::textureImage</span>           |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::thresholdImage</span>         |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::thumbnailImage</span>         |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::tintImage</span>              |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::transverseImage</span>        |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::trimImage</span>              |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::uniqueImageColors</span>      |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::unsharpMaskImage</span>       |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::vignetteImage</span>          |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::waveImage</span>              |                                                                     |                                                                     |                                                           |                                                             |
| <span class="methodname">Imagick::whiteThresholdImage</span>    |                                                                     |                                                                     |                                                           |                                                             |

Imagick::adaptiveBlurImage
==========================

Adds adaptive blur filter to image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::adaptiveBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adds an adaptive blur filter to image. The intensity of an adaptive blur
depends is dramatically decreased at edge of the image, whereas a
standard blur is uniform across the image. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel.
Provide a value of 0 and the radius will be chosen automagically.

`sigma`  
The standard deviation of the Gaussian, in pixels.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::adaptiveBlurImage</span>:**

Adaptively blur an image, then display to the browser.

``` php
<?php

header('Content-type: image/jpeg');

$image = new Imagick('test.jpg');

$image->adaptiveBlurImage(5,3);
echo $image;

?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-adaptiveBlurImage.gif" width="120" height="67" alt="Output of example : Using Imagick::adaptiveBlurImage()" />

### See Also

-   <span class="function">Imagick::blurImage</span>
-   <span class="function">Imagick::motionBlurImage</span>
-   <span class="function">Imagick::radialBlurImage</span>

Imagick::adaptiveResizeImage
============================

Adaptively resize image with data dependent triangulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::adaptiveResizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$bestfit`<span class="initializer"> = **`false`**</span></span> \[,
<span class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\] )

Adaptively resize image with data-dependent triangulation. Avoids
blurring across sharp color changes. Most useful when used to shrink
images slightly to a slightly smaller "web size"; may not look good when
a full-sized image is adaptively resized to a thumbnail. This method is
available if Imagick has been compiled against ImageMagick version 6.2.9
or newer.

> **Note**: <span class="simpara"> The behavior of the parameter
> `bestfit` changed in Imagick 3.0.0. Before this version given
> dimensions 400x400 an image of dimensions 200x150 would be left
> untouched. In Imagick 3.0.0 and later the image would be scaled up to
> size 400x300 as this is the "best fit" for the given dimensions. If
> `bestfit` parameter is used both width and height must be given.
> </span>

### Parameters

`columns`  
The number of columns in the scaled image.

`rows`  
The number of rows in the scaled image.

`bestfit`  
Whether to fit the image inside a bounding box.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Added optional fit parameter.                                                                          |
| PECL imagick 2.1.0 | This method now supports proportional scaling. Pass zero as either parameter for proportional scaling. |

### Examples

**Example \#1 Using <span
class="function">Imagick::adaptiveResizeImage</span>**

Resize an image to a standard size for the web. This method works best
when resizing to a size only slightly smaller than the previous image
size.

``` php
<?php
header('Content-type: image/jpeg');

$image = new Imagick('image.jpg');
$image->adaptiveResizeImage(1024,768);

echo $image;
?>
```

### See Also

-   <span class="function">Imagick::chopImage</span>
-   <span class="function">Imagick::cropImage</span>
-   <span class="function">Imagick::magnifyImage</span>
-   <span class="function">Imagick::minifyImage</span>
-   <span class="function">Imagick::resizeImage</span>
-   <span class="function">Imagick::scaleImage</span>
-   <span class="function">Imagick::shaveImage</span>
-   <span class="function">Imagick::thumbnailImage</span>
-   <span class="function">Imagick::trimImage</span>

Imagick::adaptiveSharpenImage
=============================

Adaptively sharpen the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::adaptiveSharpenImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adaptively sharpen the image by sharpening more intensely near image
edges and less intensely far from edges. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel.
Use 0 for auto-select.

`sigma`  
The standard deviation of the Gaussian, in pixels.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 A <span
class="function">Imagick::adaptiveSharpenImage</span> example**

Adaptively sharpen the image with radius 2 and sigma 1.

``` php
<?php
try {
    $image = new Imagick('image.png');
    $image->adaptiveSharpenImage(2,1);
} catch(ImagickException $e) {
    echo 'Error: ' , $e->getMessage();
    die();
}
header('Content-type: image/png');
echo $image;
?>
```

### See Also

-   <span class="function">Imagick::sharpenImage</span>

Imagick::adaptiveThresholdImage
===============================

Selects a threshold for each pixel based on a range of intensity

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::adaptiveThresholdImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span>
`$offset`</span> )

Selects an individual threshold for each pixel based on the range of
intensity values in its local neighborhood. This allows for thresholding
of an image whose global intensity histogram doesn't contain distinctive
peaks.

### Parameters

`width`  
Width of the local neighborhood.

`height`  
Height of the local neighborhood.

`offset`  
The mean offset

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::adaptiveThresholdImage</span>**

``` php
<?php
function adaptiveThresholdImage($imagePath, $width, $height, $adaptiveOffset) {
    $imagick = new \Imagick(realpath($imagePath));
    $adaptiveOffsetQuantum = intval($adaptiveOffset * \Imagick::getQuantum());
    $imagick->adaptiveThresholdImage($width, $height, $adaptiveOffsetQuantum);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::addImage
=================

Adds new image to Imagick object image list

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::addImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$source`</span> )

Adds new image to Imagick object from the current position of the source
object. After the operation iterator position is moved at the end of the
list.

### Parameters

`source`  
The source Imagick object

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::addNoiseImage
======================

Adds random noise to the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::addNoiseImage</span> ( <span
class="methodparam"><span class="type">int</span> `$noise_type`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adds random noise to the image.

### Parameters

`noise_type`  
The type of the noise. Refer to this list of
<a href="/imagick/constants.html#NOISE%20constants" class="link">noise constants</a>.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::addNoiseImage</span>**

``` php
<?php
function addNoiseImage($noiseType, $imagePath, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->addNoiseImage($noiseType, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::affineTransformImage
=============================

Transforms an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::affineTransformImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$matrix`</span> )

Transforms an image as dictated by the affine matrix.

### Parameters

`matrix`  
The affine matrix

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::affineTransformImage</span>**

``` php
<?php
function affineTransformImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $draw = new \ImagickDraw();

    $angle = deg2rad(40);

    $affineRotate = array(
        "sx" => cos($angle), "sy" => cos($angle), 
        "rx" => sin($angle), "ry" => -sin($angle), 
        "tx" => 0, "ty" => 0,
    );

    $draw->affine($affineRotate);

    $imagick->affineTransformImage($draw);

    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::animateImages
======================

Animates an image or images

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::animateImages</span> ( <span
class="methodparam"><span class="type">string</span> `$x_server`</span>
)

This method animates the image onto a local or remote X server. This
method is not available on Windows. This method is available if Imagick
has been compiled against ImageMagick version 6.3.6 or newer.

### Parameters

`x_server`  
X server address

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::displayImage</span>

Imagick::annotateImage
======================

Annotates an image with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::annotateImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$draw_settings`</span> , <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Annotates an image with text.

### Parameters

`draw_settings`  
The ImagickDraw object that contains settings for drawing the text

`x`  
Horizontal offset in pixels to the left of text

`y`  
Vertical offset in pixels to the baseline of text

`angle`  
The angle at which to write the text

`text`  
The string to draw

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span
class="function">Imagick::annotateImage</span>:**

Annotate text on an empty image

``` php
<?php
/* Create some objects */
$image = new Imagick();
$draw = new ImagickDraw();
$pixel = new ImagickPixel( 'gray' );

/* New image */
$image->newImage(800, 75, $pixel);

/* Black text */
$draw->setFillColor('black');

/* Font properties */
$draw->setFont('Bookman-DemiItalic');
$draw->setFontSize( 30 );

/* Create text */
$image->annotateImage($draw, 10, 45, 0, 'The quick brown fox jumps over the lazy dog');

/* Give image a format */
$image->setImageFormat('png');

/* Output the image with headers */
header('Content-type: image/png');
echo $image;

?>
```

### See Also

-   <span class="function">ImagickDraw::annotation</span>
-   <span class="function">ImagickDraw::setFont</span>

Imagick::appendImages
=====================

Append a set of images

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::appendImages</span> ( <span
class="methodparam"><span class="type">bool</span> `$stack`</span> )

Append a set of images into one larger image.

### Parameters

`stack`  
Whether to stack the images vertically. By default (or if **`false`** is
specified) images are stacked left-to-right. If `stack` is **`true`**,
images are stacked top-to-bottom.

### Return Values

Returns Imagick instance on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="methodname">Imagick::appendImages</span>
example**

``` php
<?php

/* Create new imagick object */
$im = new Imagick();

/* create red, green and blue images */
$im->newImage(100, 50, "red");
$im->newImage(100, 50, "green");
$im->newImage(100, 50, "blue");

/* Append the images into one */
$im->resetIterator();
$combined = $im->appendImages(true);

/* Output the image */
$combined->setImageFormat("png");
header("Content-Type: image/png");
echo $combined;
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-floodfillpaint_intermediate.png" width="100" height="150" alt="Output of example : Imagick::appendImages()" />

Imagick::autoLevelImage
=======================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::autoLevelImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adjusts the levels of a particular image channel by scaling the minimum
and maximum values to the full quantum range.

### Parameters

`channel`  
Which channel should the auto-levelling should be done on.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::autoLevelImage</span>**

``` php
<?php
function autoLevelImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->autoLevelImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::averageImages
======================

Average a set of images

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::averageImages</span> ( <span
class="methodparam">void</span> )

Average a set of images.

### Return Values

Returns a new Imagick object on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::blackThresholdImage
============================

Forces all pixels below the threshold into black

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::blackThresholdImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$threshold`</span>
)

Is like Imagick::thresholdImage() but forces all pixels below the
threshold into black while leaving all pixels above the threshold
unchanged.

### Parameters

`threshold`  
The threshold below which everything turns black

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                     |
|--------------------|-----------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as a parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span
class="function">Imagick::blackThresholdImage</span>**

``` php
<?php
function blackThresholdImage($imagePath, $thresholdColor) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->blackthresholdimage($thresholdColor);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::blueShiftImage
=======================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::blueShiftImage</span> (\[ <span
class="methodparam"><span class="type">float</span> `$factor`<span
class="initializer"> = 1.5</span></span> \] )

Mutes the colors of the image to simulate a scene at nighttime in the
moonlight.

### Parameters

`factor`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::blueShiftImage</span>**

``` php
<?php
function blueShiftImage($imagePath, $blueShift) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->blueShiftImage($blueShift);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::blurImage
==================

Adds blur filter to image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::blurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`</span> \] )

Adds blur filter to image. Optional third parameter to blur a specific
channel.

### Parameters

`radius`  
Blur radius

`sigma`  
Standard deviation

`channel`  
The
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">Channeltype</a>
constant. When not supplied, all channels are blurred.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span class="function">Imagick::blurImage</span>:**

Blur an image, then display to the browser.

``` php
<?php

header('Content-type: image/jpeg');

$image = new Imagick('test.jpg');

$image->blurImage(5,3);
echo $image;

?>
```

### See Also

-   <span class="function">Imagick::adaptiveBlurImage</span>
-   <span class="function">Imagick::motionBlurImage</span>
-   <span class="function">Imagick::radialBlurImage</span>

Imagick::borderImage
====================

Surrounds the image with a border

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::borderImage</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> )

Surrounds the image with a border of the color defined by the
bordercolor ImagickPixel object.

### Parameters

`bordercolor`  
ImagickPixel object or a string containing the border color

`width`  
Border width

`height`  
Border height

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span class="function">Imagick::borderImage</span>**

``` php
<?php
function borderImage($imagePath, $color, $width, $height) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->borderImage($color, $width, $height);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::brightnessContrastImage
================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::brightnessContrastImage</span> ( <span
class="methodparam"><span class="type">float</span> `$brightness`</span>
, <span class="methodparam"><span class="type">float</span>
`$contrast`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Change the brightness and/or contrast of an image. It converts the
brightness and contrast parameters into slope and intercept and calls a
polynomical function to apply to the image.

### Parameters

`brightness`  

`contrast`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::brightnessContrastImage</span>**

``` php
<?php
function brightnessContrastImage($imagePath, $brightness, $contrast, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->brightnessContrastImage($brightness, $contrast, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::charcoalImage
======================

Simulates a charcoal drawing

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::charcoalImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> )

Simulates a charcoal drawing.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel

`sigma`  
The standard deviation of the Gaussian, in pixels

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::charcoalImage</span>**

``` php
<?php
function charcoalImage($imagePath, $radius, $sigma) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->charcoalImage($radius, $sigma);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::chopImage
==================

Removes a region of an image and trims

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::chopImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Removes a region of an image and collapses the image to occupy the
removed portion.

### Parameters

`width`  
Width of the chopped area

`height`  
Height of the chopped area

`x`  
X origo of the chopped area

`y`  
Y origo of the chopped area

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span class="function">Imagick::chopImage</span>:**

Example of using Imagick::chopImage

``` php
<?php
/* Create some objects */
$image = new Imagick();
$pixel = new ImagickPixel( 'gray' );

/* New image */
$image->newImage(400, 200, $pixel);

/* Chop image */
$image->chopImage(200, 200, 0, 0);

/* Give image a format */
$image->setImageFormat('png');

/* Output the image with headers */
header('Content-type: image/png');
echo $image;

?>
```

### See Also

-   <span class="function">Imagick::cropImage</span>

Imagick::clampImage
===================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::clampImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Restricts the color range from 0 to the quantum depth.

### Parameters

`channel`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

Imagick::clear
==============

Clears all resources associated to Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::clear</span> ( <span
class="methodparam">void</span> )

Clears all resources associated to Imagick object

### Return Values

Returns **`true`** on success.

Imagick::clipImage
==================

Clips along the first path from the 8BIM profile

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::clipImage</span> ( <span
class="methodparam">void</span> )

Clips along the first path from the 8BIM profile, if present.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::clipImagePath
======================

Description

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Imagick::clipImagePath</span> ( <span
class="methodparam"><span class="type">string</span> `$pathname`</span>
, <span class="methodparam"><span class="type">string</span>
`$inside`</span> )

Clips along the named paths from the 8BIM profile, if present. Later
operations take effect inside the path. Id may be a number if preceded
with \#, to work on a numbered path, e.g., "\#1" to use the first path.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`pathname`  

`inside`  

### Return Values

Imagick::clipPathImage
======================

Clips along the named paths from the 8BIM profile

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::clipPathImage</span> ( <span
class="methodparam"><span class="type">string</span> `$pathname`</span>
, <span class="methodparam"><span class="type">bool</span>
`$inside`</span> )

Clips along the named paths from the 8BIM profile, if present. Later
operations take effect inside the path. It may be a number if preceded
with \#, to work on a numbered path, e.g., "\#1" to use the first path.

### Parameters

`pathname`  
The name of the path

`inside`  
If **`true`** later operations take effect inside clipping path.
Otherwise later operations take effect outside clipping path.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::clone
==============

Makes an exact copy of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::clone</span> ( <span
class="methodparam">void</span> )

Makes an exact copy of the Imagick object.

**Warning**

This function has been *DEPRECATED* as of imagick 3.1.0 in favour of
using the <a href="/language/oop5/cloning.html" class="link">clone</a>
keyword.

### Examples

**Example \#1 Imagick object cloning in different versions of imagick**

``` php
<?php
// Cloning an Imagick object in imagick 2.x and 3.0:
$newImage = $image->clone();

// Cloning an Imagick object from 3.1.0 on:
$newImage = clone $image;
?>
```

### Return Values

A copy of the Imagick object is returned.

### Changelog

| Version            | Description                                                                                                      |
|--------------------|------------------------------------------------------------------------------------------------------------------|
| PECL imagick 3.1.0 | The method was deprecated in favour of the <a href="/language/oop5/cloning.html" class="link">clone</a> keyword. |

Imagick::clutImage
==================

Replaces colors in the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::clutImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$lookup_table`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Replaces colors in the image from a color lookup table. Optional second
parameter to replace colors in a specific channel. This method is
available if Imagick has been compiled against ImageMagick version 6.3.6
or newer.

### Parameters

`lookup_table`  
Imagick object containing the color lookup table

`channel`  
The
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">Channeltype</a>
constant. When not supplied, default channels are replaced.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span class="function">Imagick::clutImage</span>:**

Replace colors in the image from a color lookup table.

``` php
<?php
$image = new Imagick('test.jpg');
$clut = new Imagick();
$clut->newImage(1, 1, new ImagickPixel('black'));
$image->clutImage($clut);
$image->writeImage('test_out.jpg');
?>
```

### See Also

-   <span class="function">Imagick::adaptiveBlurImage</span>
-   <span class="function">Imagick::motionBlurImage</span>
-   <span class="function">Imagick::radialBlurImage</span>

Imagick::coalesceImages
=======================

Composites a set of images

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::coalesceImages</span> ( <span
class="methodparam">void</span> )

Composites a set of images while respecting any page offsets and
disposal methods. GIF, MIFF, and MNG animation sequences typically start
with an image background and each subsequent image varies in size and
offset. Returns a new Imagick object where each image in the sequence is
the same size as the first and composited with the next image in the
sequence.

### Return Values

Returns a new Imagick object on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::colorFloodfillImage
============================

Changes the color value of any pixel that matches target

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::colorFloodfillImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

Changes the color value of any pixel that matches target and is an
immediate neighbor.

### Parameters

`fill`  
ImagickPixel object containing the fill color

`fuzz`  
The amount of fuzz. For example, set fuzz to 10 and the color red at
intensities of 100 and 102 respectively are now interpreted as the same
color for the purposes of the floodfill.

`bordercolor`  
ImagickPixel object containing the border color

`x`  
X start position of the floodfill

`y`  
Y start position of the floodfill

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                   |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as first and third parameter. Previous versions allow only an ImagickPixel object. |

Imagick::colorizeImage
======================

Blends the fill color with the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::colorizeImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$colorize`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$opacity`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \] )

Blends the fill color with each pixel in the image.

### Parameters

`colorize`  
ImagickPixel object or a string containing the colorize color

`opacity`  
ImagickPixel object or an float containing the opacity value. 1.0 is
fully opaque and 0.0 is fully transparent.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                                                                                 |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter and a float representing the opacity value as the second parameter. Previous versions allow only an ImagickPixel objects. |

### Examples

**Example \#1 <span class="function">Imagick::colorizeImage</span>**

``` php
<?php
function colorizeImage($imagePath, $color, $opacity) {
    $imagick = new \Imagick(realpath($imagePath));
    $opacity = $opacity / 255.0;
    $opacityColor = new \ImagickPixel("rgba(0, 0, 0, $opacity)");
    $imagick->colorizeImage($color, $opacityColor);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::colorMatrixImage
=========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::colorMatrixImage</span> ( <span
class="methodparam"><span class="type">array</span> `$color_matrix`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> )

Apply color transformation to an image. The method permits saturation
changes, hue rotation, luminance to alpha, and various other effects.
Although variable-sized transformation matrices can be used, typically
one uses a 5x5 matrix for an RGBA image and a 6x6 for CMYKA (or RGBA
with offsets). The matrix is similar to those used by Adobe Flash except
offsets are in column 6 rather than 5 (in support of CMYKA images) and
offsets are normalized (divide Flash offset by 255)

### Parameters

`color_matrix`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::colorMatrixImage</span>**

``` php
<?php
function colorMatrixImage($imagePath, $colorMatrix) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setImageOpacity(1);

    //A color matrix should look like:
    //    $colorMatrix = [
    //        1.5, 0.0, 0.0, 0.0, 0.0, -0.157,
    //        0.0, 1.0, 0.5, 0.0, 0.0, -0.157,
    //        0.0, 0.0, 1.5, 0.0, 0.0, -0.157,
    //        0.0, 0.0, 0.0, 1.0, 0.0,  0.0,
    //        0.0, 0.0, 0.0, 0.0, 1.0,  0.0,
    //        0.0, 0.0, 0.0, 0.0, 0.0,  1.0
    //    ];

    $background = new \Imagick();
    $background->newPseudoImage($imagick->getImageWidth(), $imagick->getImageHeight(),  "pattern:checkerboard");

    $background->setImageFormat('png');

    $imagick->setImageFormat('png');
    $imagick->colorMatrixImage($colorMatrix);
    
    $background->compositeImage($imagick, \Imagick::COMPOSITE_ATOP, 0, 0);

    header("Content-Type: image/png");
    echo $background->getImageBlob();
}

?>
```

Imagick::combineImages
======================

Combines one or more images into a single image

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::combineImages</span> ( <span
class="methodparam"><span class="type">int</span> `$channelType`</span>
)

Combines one or more images into a single image. The grayscale value of
the pixels of each image in the sequence is assigned in order to the
specified channels of the combined image. The typical ordering would be
image 1 =\> Red, 2 =\> Green, 3 =\> Blue, etc.

### Parameters

`channelType`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::commentImage
=====================

Adds a comment to your image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::commentImage</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

Adds a comment to your image.

### Parameters

`comment`  
The comment to add

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::commentImage</span>:**

Commenting an image and retrieving the comment:

``` php
<?php

/* Create new Imagick object */
$im = new imagick();

/* Create an empty image */
$im->newImage(100, 100, new ImagickPixel("red"));

/* Add comment to the image */
$im->commentImage("Hello World!");

/* Display the comment */
echo $im->getImageProperty("comment");

?>
```

Imagick::compareImageChannels
=============================

Returns the difference in one or more images

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::compareImageChannels</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$image`</span> ,
<span class="methodparam"><span class="type">int</span>
`$channelType`</span> , <span class="methodparam"><span
class="type">int</span> `$metricType`</span> )

Compares one or more images and returns the difference image.

### Parameters

`image`  
Imagick object containing the image to compare.

`channelType`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

`metricType`  
One of the
<a href="/imagick/constants.html#METRIC%20constants" class="link">metric type constants</a>.

### Return Values

Array consisting of *new\_wand* and *distortion*.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::compareImageLayers
===========================

Returns the maximum bounding region between images

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::compareImageLayers</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> )

Compares each image with the next in a sequence and returns the maximum
bounding region of any pixel differences it discovers. This method is
available if Imagick has been compiled against ImageMagick version 6.2.9
or newer.

### Parameters

`method`  
One of the
<a href="/imagick/constants.html#LAYERMETHOD%20constants" class="link">layer method constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::compareImageLayers</span>**

Comparing image layers

``` php
<?php
/* create new imagick object */
$im = new Imagick("test.gif");

/* optimize the image layers */
$result = $im->compareImageLayers(imagick::LAYERMETHOD_COALESCE);

/* work on the $result */
?>
```

### See Also

-   <span class="function">Imagick::optimizeImageLayers</span>
-   <span class="function">Imagick::writeImages</span>
-   <span class="function">Imagick::writeImage</span>

Imagick::compareImages
======================

Compares an image to a reconstructed image

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::compareImages</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$compare`</span>
, <span class="methodparam"><span class="type">int</span>
`$metric`</span> )

Returns an array containing a reconstructed image and the difference
between images.

### Parameters

`compare`  
An image to compare to.

`metric`  
Provide a valid metric type constant. Refer to this list of
<a href="/imagick/constants.html#METRIC%20constants" class="link">metric constants</a>.

### Return Values

Returns an array containing a reconstructed image and the difference
between images.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::compareImages</span>:**

Compare images and display the reconstructed image

``` php
<?php

$image1 = new imagick("image1.png");
$image2 = new imagick("image2.png");

$result = $image1->compareImages($image2, Imagick::METRIC_MEANSQUAREERROR);
$result[0]->setImageFormat("png");

header("Content-Type: image/png");
echo $result[0];

?>
```

Imagick::compositeImage
=======================

Composite one image onto another

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::compositeImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$composite_object`</span> , <span class="methodparam"><span
class="type">int</span> `$composite`</span> , <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Composite one image onto another at the specified offset. Any extra
arguments needed for the compose algorithm should passed to
setImageArtifact with 'compose:args' as the first parameter and the data
as the second parameter.

### Parameters

`composite_object`  
Imagick object which holds the composite image

`compose`  
Composite operator. See
<a href="/imagick/constants.html#Composite%20Operator%20Constants" class="link">Composite Operator Constants</a>

`x`  
The column offset of the composited image

`y`  
The row offset of the composited image

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span
class="function">Imagick::compositeImage</span>:**

Composite two images with the 'mathematics' compose method

``` php
<?php

// Equivalent to running the command
// convert src1.png src2.png -compose mathematics -define compose:args="1,0,-0.5,0.5" -composite output.png

$src1 = new \Imagick("./src1.png");
$src2 = new \Imagick("./src2.png");

$src1->setImageVirtualPixelMethod(Imagick::VIRTUALPIXELMETHOD_TRANSPARENT);
$src1->setImageArtifact('compose:args', "1,0,-0.5,0.5");
$src1->compositeImage($src2, Imagick::COMPOSITE_MATHEMATICS, 0, 0);
$src1->writeImage("./output.png");

?>
```

### See Also

-   <span class="function">Imagick::setImageArtifact</span>

Imagick::\_\_construct
======================

The Imagick constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Imagick::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$files`</span> \] )

Creates an Imagick instance for a specified image or set of images.

### Parameters

`files`  
The path to an image to load or an array of paths. Paths can include
wildcards for file names, or can be URLs.

### Return Values

Returns a new Imagick object on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::contrastImage
======================

Change the contrast of the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::contrastImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$sharpen`</span> )

Enhances the intensity differences between the lighter and darker
elements of the image. Set sharpen to a value other than 0 to increase
the image contrast otherwise the contrast is reduced.

### Parameters

`sharpen`  
The sharpen value

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::contrastImage</span>**

``` php
<?php
function contrastImage($imagePath, $contrastType) {
    $imagick = new \Imagick(realpath($imagePath));
    if ($contrastType != 2) {
        $imagick->contrastImage($contrastType);
    }

    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::contrastStretchImage
=============================

Enhances the contrast of a color image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::contrastStretchImage</span> ( <span
class="methodparam"><span class="type">float</span>
`$black_point`</span> , <span class="methodparam"><span
class="type">float</span> `$white_point`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Enhances the contrast of a color image by adjusting the pixels color to
span the entire range of colors available. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`black_point`  
The black point.

`white_point`  
The white point.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. **`Imagick::CHANNEL_ALL`**. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

Imagick::convolveImage
======================

Applies a custom convolution kernel to the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::convolveImage</span> ( <span
class="methodparam"><span class="type">array</span> `$kernel`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Applies a custom convolution kernel to the image.

### Parameters

`kernel`  
The convolution kernel

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::convolveImage</span>**

``` php
<?php
function convolveImage($imagePath, $bias, $kernelMatrix) {
    $imagick = new \Imagick(realpath($imagePath));    
    //$edgeFindingKernel = [-1, -1, -1, -1, 8, -1, -1, -1, -1,];
    $imagick->setImageBias($bias * \Imagick::getQuantum());
    $imagick->convolveImage($kernelMatrix);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::count
==============

Get the number of images

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::count</span> (\[ <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = 0</span></span> \] )

Returns the number of images.

### Parameters

`mode`  
An unused argument. Currently there is a non-particularly well defined
feature in PHP where calling count() on a countable object might (or
might not) require this method to accept a parameter. This parameter is
here to be conformant with the interface of countable, even though the
param is not used.

### Return Values

Returns the number of images.

Imagick::cropImage
==================

Extracts a region of the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::cropImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Extracts a region of the image.

### Parameters

`width`  
The width of the crop

`height`  
The height of the crop

`x`  
The X coordinate of the cropped region's top left corner

`y`  
The Y coordinate of the cropped region's top left corner

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::cropImage</span>**

``` php
<?php
function cropImage($imagePath, $startX, $startY, $width, $height) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->cropImage($width, $height, $startX, $startY);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::cropThumbnailImage
===========================

Creates a crop thumbnail

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::cropThumbnailImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$legacy`<span class="initializer"> = **`false`**</span></span> \] )

Creates a fixed size thumbnail by first scaling the image up or down and
cropping a specified area from the center.

### Parameters

`width`  
The width of the thumbnail

`height`  
The Height of the thumbnail

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::current
================

Returns a reference to the current Imagick object

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::current</span> ( <span
class="methodparam">void</span> )

Returns reference to the current imagick object with image pointer at
the correct sequence.

### Return Values

Returns self on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::cycleColormapImage
===========================

Displaces an image's colormap

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::cycleColormapImage</span> ( <span
class="methodparam"><span class="type">int</span> `$displace`</span> )

Displaces an image's colormap by a given number of positions. If you
cycle the colormap a number of times you can produce a psychedelic
effect.

### Parameters

`displace`  
The amount to displace the colormap.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::decipherImage
======================

Deciphers an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::decipherImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> )

Deciphers image that has been enciphered before. The image must be
enciphered using <span class="function">Imagick::encipherImage</span>.
This method is available if Imagick has been compiled against
ImageMagick version 6.3.9 or newer.

### Parameters

`passphrase`  
The passphrase

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::encipherImage</span>

Imagick::deconstructImages
==========================

Returns certain pixel differences between images

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::deconstructImages</span> ( <span
class="methodparam">void</span> )

Compares each image with the next in a sequence and returns the maximum
bounding region of any pixel differences it discovers.

### Return Values

Returns a new Imagick object on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::deleteImageArtifact
============================

Delete image artifact

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::deleteImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
)

Deletes an artifact associated with the image. The difference between
image properties and image artifacts is that properties are public and
artifacts are private. This method is available if Imagick has been
compiled against ImageMagick version 6.5.7 or newer.

### Parameters

`artifact`  
The name of the artifact to delete

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::setImageArtifact</span>
-   <span class="function">Imagick::getImageArtifact</span>

Imagick::deleteImageProperty
============================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::deleteImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Deletes an image property.

### Parameters

`name`  
The name of the property to delete.

### Return Values

Returns **`true`** on success.

Imagick::deskewImage
====================

Removes skew from the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::deskewImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
)

This method can be used to remove skew from for example scanned images
where the paper was not properly placed on the scanning surface. This
method is available if Imagick has been compiled against ImageMagick
version 6.4.5 or newer.

### Parameters

`threshold`  
Deskew threshold

### Return Values

### Examples

**Example \#1 <span class="function">Imagick::deskewImage</span>**

``` php
<?php
function deskewImage($threshold) {
    $imagick = new \Imagick(realpath("images/NYTimes-Page1-11-11-1918.jpg"));
    $deskewImagick = clone $imagick;
    
    //This is the only thing required for deskewing.
    $deskewImagick->deskewImage($threshold);

    //The rest of this example is to make the result obvious - because
    //otherwise the result is not obvious.
    $trim = 9;

    $deskewImagick->cropImage($deskewImagick->getImageWidth() - $trim, $deskewImagick->getImageHeight(), $trim, 0);
    $imagick->cropImage($imagick->getImageWidth() - $trim, $imagick->getImageHeight(), $trim, 0);
    $deskewImagick->resizeimage($deskewImagick->getImageWidth() / 2, $deskewImagick->getImageHeight() / 2, \Imagick::FILTER_LANCZOS, 1);
    $imagick->resizeimage($imagick->getImageWidth() / 2, $imagick->getImageHeight() / 2, \Imagick::FILTER_LANCZOS, 1);
    $newCanvas = new \Imagick();
    $newCanvas->newimage($imagick->getImageWidth() + $deskewImagick->getImageWidth() + 20, $imagick->getImageHeight(), 'red', 'jpg');
    $newCanvas->compositeimage($imagick, \Imagick::COMPOSITE_COPY, 5, 0);
    $newCanvas->compositeimage($deskewImagick, \Imagick::COMPOSITE_COPY, $imagick->getImageWidth() + 10, 0);

    header("Content-Type: image/jpg");
    echo $newCanvas->getImageBlob();
}

?>
```

Imagick::despeckleImage
=======================

Reduces the speckle noise in an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::despeckleImage</span> ( <span
class="methodparam">void</span> )

Reduces the speckle noise in an image while preserving the edges of the
original image.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::despeckleImage</span>**

``` php
<?php
function despeckleImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->despeckleImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::destroy
================

Destroys the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::destroy</span> ( <span
class="methodparam">void</span> )

Destroys the Imagick object and frees all resources associated with it.
This method is deprecated in favour of
<a href="/class/imagick.html#Imagick::clear" class="link">Imagick::clear</a>.

### Return Values

Returns **`true`** on success.

Imagick::displayImage
=====================

Displays an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::displayImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$servername`</span> )

This method displays an image on a X server.

### Parameters

`servername`  
The X server name

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::displayImages
======================

Displays an image or image sequence

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::displayImages</span> ( <span
class="methodparam"><span class="type">string</span>
`$servername`</span> )

Displays an image or image sequence on a X server.

### Parameters

`servername`  
The X server name

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::distortImage
=====================

Distorts an image using various distortion methods

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::distortImage</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> ,
<span class="methodparam"><span class="type">array</span>
`$arguments`</span> , <span class="methodparam"><span
class="type">bool</span> `$bestfit`</span> )

Distorts an image using various distortion methods, by mapping color
lookups of the source image to a new destination image usually of the
same size as the source image, unless 'bestfit' is set to **`true`**.

If 'bestfit' is enabled, and distortion allows it, the destination image
is adjusted to ensure the whole source 'image' will just fit within the
final destination image, which will be sized and offset accordingly.
Also in many cases the virtual offset of the source image will be taken
into account in the mapping.

This method is available if Imagick has been compiled against
ImageMagick version 6.3.6 or newer.

### Parameters

`method`  
The method of image distortion. See
<a href="/imagick/constants.html#DISTORTION%20constants" class="link">distortion constants</a>

`arguments`  
The arguments for this distortion method

`bestfit`  
Attempt to resize destination to fit distorted source

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::distortImage</span>:**

Distort an image and display to the browser.

``` php
<?php
/* Create new object */
$im = new Imagick();

/* Create new checkerboard pattern */
$im->newPseudoImage(100, 100, "pattern:checkerboard");

/* Set the image format to png */
$im->setImageFormat('png');

/* Fill new visible areas with transparent */
$im->setImageVirtualPixelMethod(Imagick::VIRTUALPIXELMETHOD_TRANSPARENT);

/* Activate matte */
$im->setImageMatte(true);

/* Control points for the distortion */
$controlPoints = array( 10, 10, 
                        10, 5,

                        10, $im->getImageHeight() - 20,
                        10, $im->getImageHeight() - 5,

                        $im->getImageWidth() - 10, 10,
                        $im->getImageWidth() - 10, 20,

                        $im->getImageWidth() - 10, $im->getImageHeight() - 10,
                        $im->getImageWidth() - 10, $im->getImageHeight() - 30);

/* Perform the distortion */                       
$im->distortImage(Imagick::DISTORTION_PERSPECTIVE, $controlPoints, true);

/* Ouput the image */
header("Content-Type: image/png");
echo $im;
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-distortImage.png" width="111" height="150" alt="Output of example : Using Imagick::distortImage()" />

### See Also

-   <span class="function">Imagick::blurImage</span>
-   <span class="function">Imagick::motionBlurImage</span>
-   <span class="function">Imagick::radialBlurImage</span>

Imagick::drawImage
==================

Renders the ImagickDraw object on the current image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::drawImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span> `$draw`</span>
)

Renders the ImagickDraw object on the current image.

### Parameters

`draw`  
The drawing operations to render on the image.

### Return Values

Returns **`true`** on success.

Imagick::edgeImage
==================

Enhance edges within the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::edgeImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Enhance edges within the image with a convolution filter of the given
radius. Use radius 0 and it will be auto-selected.

### Parameters

`radius`  
The radius of the operation.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::edgeImage</span>**

``` php
<?php
function edgeImage($imagePath, $radius) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->edgeImage($radius);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::embossImage
====================

Returns a grayscale image with a three-dimensional effect

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::embossImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> )

Returns a grayscale image with a three-dimensional effect. We convolve
the image with a Gaussian operator of the given radius and standard
deviation (sigma). For reasonable results, radius should be larger than
sigma. Use a radius of 0 and it will choose a suitable radius for you.

### Parameters

`radius`  
The radius of the effect

`sigma`  
The sigma of the effect

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::embossImage</span>**

``` php
<?php
function embossImage($imagePath, $radius, $sigma) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->embossImage($radius, $sigma);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::encipherImage
======================

Enciphers an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::encipherImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> )

Converts plain pixels to enciphered pixels. The image is not readable
until it has been deciphered using <span
class="function">Imagick::decipherImage</span> This method is available
if Imagick has been compiled against ImageMagick version 6.3.9 or newer.

### Parameters

`passphrase`  
The passphrase

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::decipherImage</span>

Imagick::enhanceImage
=====================

Improves the quality of a noisy image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::enhanceImage</span> ( <span
class="methodparam">void</span> )

Applies a digital filter that improves the quality of a noisy image.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::enhanceImage</span>**

``` php
<?php
function enhanceImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->enhanceImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::equalizeImage
======================

Equalizes the image histogram

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::equalizeImage</span> ( <span
class="methodparam">void</span> )

Equalizes the image histogram.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::equalizeImage</span>**

``` php
<?php
function equalizeImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->equalizeImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::evaluateImage
======================

Applies an expression to an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::evaluateImage</span> ( <span
class="methodparam"><span class="type">int</span> `$op`</span> , <span
class="methodparam"><span class="type">float</span> `$constant`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Applys an arithmetic, relational, or logical expression to an image. Use
these operators to lighten or darken an image, to increase or decrease
contrast in an image, or to produce the "negative" of an image.

### Parameters

`op`  
The evaluation operator

`constant`  
The value of the operator

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Examples

**Example \#1 Using <span
class="function">Imagick::evaluateImage</span>**

Using evaluateImage to reduce opacity in an image.

``` php
<?php
// Create new object with the image
$im = new Imagick('example-alpha.png');

// Reduce the alpha by 50%
$im->evaluateImage(Imagick::EVALUATE_DIVIDE, 2, Imagick::CHANNEL_ALPHA);

// Output the image
header("Content-Type: image/png");
echo $im;
?>
```

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::exportImagePixels
==========================

Exports raw image pixels

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::exportImagePixels</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">string</span>
`$map`</span> , <span class="methodparam"><span class="type">int</span>
`$STORAGE`</span> )

Exports image pixels into an array. The map defines the ordering of the
exported pixels. The size of the returned array is *width \* height \*
strlen(map)*. This method is available if Imagick has been compiled
against ImageMagick version 6.4.7 or newer.

### Parameters

`x`  
X-coordinate of the exported area

`y`  
Y-coordinate of the exported area

`width`  
Width of the exported aread

`height`  
Height of the exported area

`map`  
Ordering of the exported pixels. For example *"RGB"*. Valid characters
for the map are R, G, B, A, O, C, Y, M, K, I and P.

`STORAGE`  
Refer to this list of
<a href="/imagick/constants.html#PIXEL%20constants" class="link">pixel type constants</a>

### Examples

**Example \#1 Using <span
class="function">Imagick::exportImagePixels</span>**

Export image pixels into an array

``` php
<?php

/* Create new object */
$im = new Imagick();

/* Create new image */
$im->newPseudoImage(0, 0, "magick:rose");

/* Export the image pixels */
$pixels = $im->exportImagePixels(10, 10, 2, 2, "RGB", Imagick::PIXEL_CHAR);

/* Output */
var_dump($pixels);
?>
```

The above example will output:

    array(12) {
      [0]=>
      int(72)
      [1]=>
      int(64)
      [2]=>
      int(57)
      [3]=>
      int(69)
      [4]=>
      int(59)
      [5]=>
      int(43)
      [6]=>
      int(124)
      [7]=>
      int(120)
      [8]=>
      int(-96)
      [9]=>
      int(91)
      [10]=>
      int(84)
      [11]=>
      int(111)
    }

### Return Values

Returns an array containing the pixels values.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::extentImage
====================

Set image size

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::extentImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Comfortability method for setting image size. The method sets the image
size and allows setting x,y coordinates where the new area begins. This
method is available if Imagick has been compiled against ImageMagick
version 6.3.1 or newer.

**Caution**

Prior to ImageMagick 6.5.7-8 (1623), $x was positive when shifting to
the left and negative when shifting to the right, and $y was positive
when shifting an image up and negative when shifting an image down.
Somewhere betwen ImageMagick 6.3.7 (1591) and ImageMagick 6.5.7-8
(1623), the axes of $x and $y were flipped, so that $x was negative when
shifting to the left and positive when shifting to the right, and $y was
negative when shifting an image up and positive when shifting an image
down. Somewhere between ImageMagick 6.5.7-8 (1623) and ImageMagick
6.6.9-7 (1641), the axes of $x and $y were flipped back to
pre-ImageMagick 6.5.7-8 (1623) functionality.

### Parameters

`width`  
The new width

`height`  
The new height

`x`  
X position for the new size

`y`  
Y position for the new size

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::resizeImage</span>
-   <span class="function">Imagick::thumbnailImage</span>
-   <span class="function">Imagick::cropImage</span>

Imagick::filter
===============

Description

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::filter</span> ( <span
class="methodparam"><span class="type">ImagickKernel</span>
`$ImagickKernel`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_UNDEFINED</span></span> \] )

Applies a custom convolution kernel to the image.

### Parameters

`ImagickKernel`  
An instance of ImagickKernel that represents either a single kernel or a
linked series of kernels.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::filter</span>**

``` php
<?php
function filter($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $matrix = [
        [-1, 0, -1],
        [0,  5,  0],
        [-1, 0, -1],
    ];
    
    $kernel = \ImagickKernel::fromMatrix($matrix);
    $strength = 0.5;    
    $kernel->scale($strength, \Imagick::NORMALIZE_KERNEL_VALUE);    
    $kernel->addUnityKernel(1 - $strength);

    $imagick->filter($kernel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::flattenImages
======================

Merges a sequence of images

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::flattenImages</span> ( <span
class="methodparam">void</span> )

Merges a sequence of images. This is useful for combining Photoshop
layers into a single image.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::flipImage
==================

Creates a vertical mirror image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::flipImage</span> ( <span
class="methodparam">void</span> )

Creates a vertical mirror image by reflecting the pixels around the
central x-axis.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::flipImage</span>**

``` php
<?php
function flipImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->flipImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::floodFillPaintImage
============================

Changes the color value of any pixel that matches target

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::floodFillPaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$target`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> , <span class="methodparam"><span
class="type">bool</span> `$invert`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes the color value of any pixel that matches target and is an
immediate neighbor. This method is a replacement for deprecated <span
class="function">Imagick::paintFloodFillImage</span>. This method is
available if Imagick has been compiled against ImageMagick version 6.3.8
or newer.

### Parameters

`fill`  
ImagickPixel object or a string containing the fill color

`fuzz`  
The amount of fuzz. For example, set fuzz to 10 and the color red at
intensities of 100 and 102 respectively are now interpreted as the same
color.

`target`  
ImagickPixel object or a string containing the target color to paint

`x`  
X start position of the floodfill

`y`  
Y start position of the floodfill

`invert`  
If **`true`** paints any pixel that does not match the target color.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="methodname">Imagick::floodfillPaintImage</span> example**

``` php
<?php

/* Create new imagick object */
$im = new Imagick();

/* create red, green and blue images */
$im->newImage(100, 50, "red");
$im->newImage(100, 50, "green");
$im->newImage(100, 50, "blue");

/* Append the images into one */
$im->resetIterator();
$combined = $im->appendImages(true);

/* Save the intermediate image for comparison */
$combined->writeImage("floodfillpaint_intermediate.png");

/* The target pixel to paint */
$x = 1;
$y = 1;

/* Get the color we are painting */
$target = $combined->getImagePixelColor($x, $y);

/* Paints pixel in position 1,1 black and all neighboring 
   pixels that match the target color */
$combined->floodfillPaintImage("black", 1, $target, $x, $y, false);

/* Save the result */
$combined->writeImage("floodfillpaint_result.png");
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-floodfillpaint_intermediate.png" width="100" height="150" alt="Output of example : Imagick::floodfillPaintImage()" />

<img src="images/c0d23d2d6769e53e24a1b3136c064577-floodfillpaint_result.png" width="100" height="150" alt="Output of example : Imagick::floodfillPaintImage()" />

Imagick::flopImage
==================

Creates a vertical mirror image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::flopImage</span> ( <span
class="methodparam">void</span> )

Creates a vertical mirror image by reflecting the pixels around the
central y-axis.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::flopImage</span>**

``` php
<?php
function flopImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->flopImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::forwardFourierTransformImage
=====================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::forwardFourierTransformimage</span> (
<span class="methodparam"><span class="type">bool</span>
`$magnitude`</span> )

Implements the discrete Fourier transform (DFT) of the image either as a
magnitude / phase or real / imaginary image pair.

### Parameters

`magnitude`  
If true, return as magnitude / phase pair otherwise a real / imaginary
image pair.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::forwardFourierTransformImage</span>**

``` php
<?php
//Utility function for forwardTransformImage
function createMask() {
    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(0);
    $draw->setStrokeColor('rgb(255, 255, 255)');
    $draw->setFillColor('rgb(255, 255, 255)');

    //Draw a circle on the y-axis, with it's centre
    //at x, y that touches the origin
    $draw->circle(250, 250, 220, 250);

    $imagick = new \Imagick();
    $imagick->newImage(512, 512, "black");
    $imagick->drawImage($draw);
    $imagick->gaussianBlurImage(20, 20);
    $imagick->autoLevelImage();

    return $imagick;
}


function forwardFourierTransformImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->resizeimage(512, 512, \Imagick::FILTER_LANCZOS, 1);

    $mask = createMask();
    $imagick->forwardFourierTransformImage(true);

    @$imagick->setimageindex(0);
    $magnitude = $imagick->getimage();

    @$imagick->setimageindex(1);
    $imagickPhase = $imagick->getimage();

    if (true) {
        $imagickPhase->compositeImage($mask, \Imagick::COMPOSITE_MULTIPLY, 0, 0);
    }

    if (false) {
        $output = clone $imagickPhase;
        $output->setimageformat('png');
        header("Content-Type: image/png");
        echo $output->getImageBlob();
    }

    $magnitude->inverseFourierTransformImage($imagickPhase, true);

    $magnitude->setimageformat('png');
    header("Content-Type: image/png");
    echo $magnitude->getImageBlob();
}

?>
```

Imagick::frameImage
===================

Adds a simulated three-dimensional border

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::frameImage</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$matte_color`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> ,
<span class="methodparam"><span class="type">int</span>
`$inner_bevel`</span> , <span class="methodparam"><span
class="type">int</span> `$outer_bevel`</span> )

Adds a simulated three-dimensional border around the image. The width
and height specify the border width of the vertical and horizontal sides
of the frame. The inner and outer bevels indicate the width of the inner
and outer shadows of the frame.

### Parameters

`matte_color`  
ImagickPixel object or a string representing the matte color

`width`  
The width of the border

`height`  
The height of the border

`inner_bevel`  
The inner bevel width

`outer_bevel`  
The outer bevel width

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span class="function">Imagick::frameImage</span>**

``` php
<?php
function frameImage($imagePath, $color, $width, $height, $innerBevel, $outerBevel) {
    $imagick = new \Imagick(realpath($imagePath));

    $width = $width + $innerBevel + $outerBevel;
    $height = $height + $innerBevel + $outerBevel;

    $imagick->frameimage(
        $color,
        $width,
        $height,
        $innerBevel,
        $outerBevel
    );
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::functionImage
======================

Applies a function on the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::functionImage</span> ( <span
class="methodparam"><span class="type">int</span> `$function`</span> ,
<span class="methodparam"><span class="type">array</span>
`$arguments`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Applies an arithmetic, relational, or logical expression to a pseudo
image.

See also
<a href="http://www.imagemagick.org/Usage/transform/#function" class="link external">» ImageMagick v6 Examples - Image Transformations — Function, Multi-Argument Evaluate</a>

This method is available if Imagick has been compiled against
ImageMagick version 6.4.9 or newer.

### Parameters

`function`  
Refer to this list of
<a href="/imagick/constants.html#FUNCTION%20constants" class="link">function constants</a>

`arguments`  
Array of arguments to pass to this function.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Create a sinusoidal gradient**

``` php
<?php
$imagick = new Imagick();
$imagick->newPseudoImage(200, 200, 'gradient:black-white');
$arguments = array(3, -90);
$imagick->functionImage(Imagick::FUNCTION_SINUSOID, $arguments);

header("Content-Type: image/png");
$imagick->setImageFormat("png");
echo $imagick->getImageBlob();
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-functionImage_sinusoidal.png" width="200" height="200" alt="Output of create a sinusoidal gradient" />

**Example \#2 Create a gradient from the polynomial (4x^2 - 4x + 1)**

``` php
<?php
$imagick = new Imagick();
$imagick->newPseudoImage(200, 200, 'gradient:black-white');
$arguments = array(4, -4, 1);
$imagick->functionImage(Imagick::FUNCTION_POLYNOMIAL, $arguments);

header("Content-Type: image/png");
$imagick->setimageformat("png");
echo $imagick->getImageBlob();
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-functionImage_polynomial.png" width="200" height="200" alt="Output of create a polynomial gradient" />

**Example \#3 Create a complex gradient from the polynomial (4x^2 - 4x^2
+ 1) modulated by a sinusoidal gradient**

``` php
<?php
$imagick1 = new Imagick();
$imagick1->newPseudoImage(200, 200, 'gradient:black-white');
$arguments = array(9, -90);
$imagick1->functionImage(Imagick::FUNCTION_SINUSOID, $arguments);

$imagick2 = new Imagick();
$imagick2->newPseudoImage(200, 200, 'gradient:black-white');
$arguments = array(0.5, 0);
$imagick2->functionImage(Imagick::FUNCTION_SINUSOID, $arguments);
$imagick1->compositeimage($imagick2, Imagick::COMPOSITE_MULTIPLY, 0, 0);

header("Content-Type: image/png");
$imagick1->setImageFormat("png");
echo $imagick1->getImageBlob();
?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-functionImage_multiplied.png" width="200" height="200" alt="Output of create complex gradient" />

Imagick::fxImage
================

Evaluate expression for each pixel in the image

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::fxImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$expression`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Evaluate expression for each pixel in the image. Consult
<a href="http://www.imagemagick.org/script/fx.php" class="link external">» The Fx Special Effects Image Operator</a>
for more information.

### Parameters

`expression`  
The expression.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::fxImage</span>**

``` php
<?php
function fxImage() {
    $imagick = new \Imagick();
    $imagick->newPseudoImage(200, 200, "xc:white");

    $fx = 'xx=i-w/2; yy=j-h/2; rr=hypot(xx,yy); (.5-rr/140)*1.2+.5';
    $fxImage = $imagick->fxImage($fx);

    header("Content-Type: image/png");
    $fxImage->setimageformat('png');
    echo $fxImage->getImageBlob();
}

?>
```

Imagick::gammaImage
===================

Gamma-corrects an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::gammaImage</span> ( <span
class="methodparam"><span class="type">float</span> `$gamma`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Gamma-corrects an image. The same image viewed on different devices will
have perceptual differences in the way the image's intensities are
represented on the screen. Specify individual gamma levels for the red,
green, and blue channels, or adjust all three with the gamma parameter.
Values typically range from 0.8 to 2.3.

### Parameters

`gamma`  
The amount of gamma-correction.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::gammaImage</span>**

``` php
<?php
function gammaImage($imagePath, $gamma, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->gammaImage($gamma, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::gaussianBlurImage
==========================

Blurs an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::gaussianBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Blurs an image. We convolve the image with a Gaussian operator of the
given radius and standard deviation (sigma). For reasonable results, the
radius should be larger than sigma. Use a radius of 0 and selects a
suitable radius for you.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel.

`sigma`  
The standard deviation of the Gaussian, in pixels.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::gaussianBlurImage</span>**

``` php
<?php
function gaussianBlurImage($imagePath, $radius, $sigma, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->gaussianBlurImage($radius, $sigma, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::getColorspace
======================

Gets the colorspace

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getColorspace</span> ( <span
class="methodparam">void</span> )

Gets the global colorspace value. This method is available if Imagick
has been compiled against ImageMagick version 6.5.7 or newer.

### Return Values

Returns an integer which can be compared against
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>.

Imagick::getCompression
=======================

Gets the object compression type

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getCompression</span> ( <span
class="methodparam">void</span> )

Gets the object compression type.

### Return Values

Returns the compression constant

Imagick::getCompressionQuality
==============================

Gets the object compression quality

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getCompressionQuality</span> ( <span
class="methodparam">void</span> )

Gets the object compression quality.

### Return Values

Returns integer describing the compression quality

Imagick::getCopyright
=====================

Returns the ImageMagick API copyright as a string

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Imagick::getCopyright</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick API copyright as a string.

### Return Values

Returns a string containing the copyright notice of Imagemagick and
Magickwand C API.

Imagick::getFilename
====================

The filename associated with an image sequence

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getFilename</span> ( <span
class="methodparam">void</span> )

Returns the filename associated with an image sequence.

### Return Values

Returns a string on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getFont
================

Gets font

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getFont</span> ( <span
class="methodparam">void</span> )

Returns the objects font property. This method is available if Imagick
has been compiled against ImageMagick version 6.3.7 or newer.

### Return Values

Returns the string containing the font name or **`false`** if not font
is set.

### See Also

-   <span class="function">Imagick::setFont</span>
-   <span class="function">ImagickDraw::setFont</span>
-   <span class="function">ImagickDraw::getFont</span>

Imagick::getFormat
==================

Returns the format of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getFormat</span> ( <span
class="methodparam">void</span> )

Returns the format of the Imagick object.

### Return Values

Returns the format of the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getGravity
===================

Gets the gravity

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getGravity</span> ( <span
class="methodparam">void</span> )

Gets the global gravity property for the Imagick object. This method is
available if Imagick has been compiled against ImageMagick version 6.4.0
or newer.

### Return Values

Returns the gravity property. Refer to the list of
<a href="/imagick/constants.html#GRAVITY%20constants" class="link">gravity constants</a>.

Imagick::getHomeURL
===================

Returns the ImageMagick home URL

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Imagick::getHomeURL</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick home URL.

### Return Values

Returns a link to the imagemagick homepage.

Imagick::getImage
=================

Returns a new Imagick object

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::getImage</span> ( <span
class="methodparam">void</span> )

Returns a new Imagick object with the current image sequence.

### Return Values

Returns a new Imagick object with the current image sequence.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageAlphaChannel
=============================

Gets the image alpha channel

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageAlphaChannel</span> ( <span
class="methodparam">void</span> )

Gets the image alpha channel value. The returned value is one of the
<a href="/imagick/constants.html#ALPHACHANNEL%20constants" class="link">alpha channel constants</a>.
This method is available if Imagick has been compiled against
ImageMagick version 6.4.0 or newer.

### Return Values

Returns a constant defining the current alpha channel value. Refer to
this list of
<a href="/imagick/constants.html#ALPHACHANNEL%20constants" class="link">alpha channel constants</a>.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageArtifact
=========================

Get image artifact

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
)

Gets an artifact associated with the image. The difference between image
properties and image artifacts is that properties are public and
artifacts are private. This method is available if Imagick has been
compiled against ImageMagick version 6.5.7 or newer.

### Parameters

`artifact`  
The name of the artifact

### Return Values

Returns the artifact value on success.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::setImageArtifact</span>
-   <span class="function">Imagick::deleteImageArtifact</span>

Imagick::getImageAttribute
==========================

Description

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageAttribute</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Returns a named attribute.

### Parameters

`key`  
The key of the attribute to get.

### Return Values

Imagick::getImageBackgroundColor
================================

Returns the image background color

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">Imagick::getImageBackgroundColor</span> ( <span
class="methodparam">void</span> )

Returns the image background color.

### Return Values

Returns an ImagickPixel set to the background color of the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageBlob
=====================

Returns the image sequence as a blob

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageBlob</span> ( <span
class="methodparam">void</span> )

Implements direct to memory image formats. It returns the image sequence
as a string. The format of the image determines the format of the
returned blob (GIF, JPEG, PNG, etc.). To return a different image
format, use Imagick::setImageFormat().

### Return Values

Returns a string containing the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageBluePrimary
============================

Returns the chromaticy blue primary point

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageBluePrimary</span> ( <span
class="methodparam">void</span> )

Returns the chromaticity blue primary point for the image.

### Parameters

`x`  
The chromaticity blue primary x-point.

`y`  
The chromaticity blue primary y-point.

### Return Values

Array consisting of "x" and "y" coordinates of point.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageBorderColor
============================

Returns the image border color

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">Imagick::getImageBorderColor</span> ( <span
class="methodparam">void</span> )

Returns the image border color.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelDepth
=============================

Gets the depth for a particular image channel

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageChannelDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Gets the depth for a particular image channel.

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

Imagick::getImageChannelDistortion
==================================

Compares image channels of an image to a reconstructed image

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getImageChannelDistortion</span> (
<span class="methodparam"><span class="type">Imagick</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$channel`</span> , <span
class="methodparam"><span class="type">int</span> `$metric`</span> )

Compares one or more image channels of an image to a reconstructed image
and returns the specified distortion metric.

### Parameters

`reference`  
Imagick object to compare to.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

`metric`  
One of the
<a href="/imagick/constants.html#METRIC%20constants" class="link">metric type constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelDistortions
===================================

Gets channel distortions

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getImageChannelDistortions</span> (
<span class="methodparam"><span class="type">Imagick</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$metric`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Compares one or more image channels of an image to a reconstructed image
and returns the specified distortion metrics This method is available if
Imagick has been compiled against ImageMagick version 6.4.4 or newer.

### Parameters

`reference`  
Imagick object containing the reference image

`metric`  
Refer to this list of
<a href="/imagick/constants.html#METRIC%20constants" class="link">metric type constants</a>.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns a double describing the channel distortion.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelExtrema
===============================

Gets the extrema for one or more image channels

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageChannelExtrema</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Gets the extrema for one or more image channels. Return value is an
associative array with the keys "minima" and "maxima".

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelKurtosis
================================

The getImageChannelKurtosis purpose

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageChannelKurtosis</span> (\[
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Get the kurtosis and skewness of a specific channel. This method is
available if Imagick has been compiled against ImageMagick version 6.4.9
or newer.

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns an array with *kurtosis* and *skewness* members.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelMean
============================

Gets the mean and standard deviation

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageChannelMean</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Gets the mean and standard deviation of one or more image channels.

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns an array with *"mean"* and *"standardDeviation"* members.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelRange
=============================

Gets channel range

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageChannelRange</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Gets the range for one or more image channels. This method is available
if Imagick has been compiled against ImageMagick version 6.4.0 or newer.

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns an array containing minima and maxima values of the channel(s).

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageChannelStatistics
==================================

Returns statistics for each channel in the image

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageChannelStatistics</span> (
<span class="methodparam">void</span> )

Returns statistics for each channel in the image. The statistics include
the channel depth, its minima and maxima, the mean, and the standard
deviation.

### Return Values

Returns **`true`** on success.

Imagick::getImageClipMask
=========================

Gets image clip mask

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::getImageClipMask</span> ( <span
class="methodparam">void</span> )

Returns the image clip mask. The clip mask is an Imagick object
containing the clip mask. This method is available if Imagick has been
compiled against ImageMagick version 6.3.6 or newer.

### Return Values

Returns an Imagick object containing the clip mask.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageColormapColor
==============================

Returns the color of the specified colormap index

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">Imagick::getImageColormapColor</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Returns the color of the specified colormap index.

### Parameters

`index`  
The offset into the image colormap.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageColors
=======================

Gets the number of unique colors in the image

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageColors</span> ( <span
class="methodparam">void</span> )

Gets the number of unique colors in the image.

### Return Values

Returns an <span class="type">int</span>, the number of unique colors in
the image.

Imagick::getImageColorspace
===========================

Gets the image colorspace

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageColorspace</span> ( <span
class="methodparam">void</span> )

Gets the image colorspace.

### Return Values

Returns an integer which can be compared against
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>.

Imagick::getImageCompose
========================

Returns the composite operator associated with the image

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageCompose</span> ( <span
class="methodparam">void</span> )

Returns the composite operator associated with the image.

### Return Values

Returns **`true`** on success.

Imagick::getImageCompression
============================

Gets the current image's compression type

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageCompression</span> ( <span
class="methodparam">void</span> )

Gets the current image's compression type.

### Return Values

Returns the compression constant

Imagick::getImageCompressionQuality
===================================

Gets the current image's compression quality

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageCompressionQuality</span> ( <span
class="methodparam">void</span> )

Gets the current image's compression quality

### Return Values

Returns integer describing the images compression quality

Imagick::getImageDelay
======================

Gets the image delay

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageDelay</span> ( <span
class="methodparam">void</span> )

Gets the image delay.

### Return Values

Returns the image delay.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageDepth
======================

Gets the image depth

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageDepth</span> ( <span
class="methodparam">void</span> )

Gets the image depth.

### Return Values

The image depth.

Imagick::getImageDispose
========================

Gets the image disposal method

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageDispose</span> ( <span
class="methodparam">void</span> )

Gets the image disposal method.

### Return Values

Returns the dispose method on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageDistortion
===========================

Compares an image to a reconstructed image

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getImageDistortion</span> ( <span
class="methodparam"><span class="type">MagickWand</span>
`$reference`</span> , <span class="methodparam"><span
class="type">int</span> `$metric`</span> )

Compares an image to a reconstructed image and returns the specified
distortion metric.

### Parameters

`reference`  
Imagick object to compare to.

`metric`  
One of the
<a href="/imagick/constants.html#METRIC%20constants" class="link">metric type constants</a>.

### Return Values

Returns the distortion metric used on the image (or the best guess
thereof).

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageExtrema
========================

Gets the extrema for the image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageExtrema</span> ( <span
class="methodparam">void</span> )

Gets the extrema for the image. Returns an associative array with the
keys "min" and "max".

### Return Values

Returns an associative array with the keys "min" and "max".

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageFilename
=========================

Returns the filename of a particular image in a sequence

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageFilename</span> ( <span
class="methodparam">void</span> )

Returns the filename of a particular image in a sequence.

### Return Values

Returns a string with the filename of the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageFormat
=======================

Returns the format of a particular image in a sequence

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageFormat</span> ( <span
class="methodparam">void</span> )

Returns the format of a particular image in a sequence.

### Return Values

Returns a string containing the image format on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageGamma
======================

Gets the image gamma

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getImageGamma</span> ( <span
class="methodparam">void</span> )

Gets the image gamma.

### Return Values

Returns the image gamma on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageGeometry
=========================

Gets the width and height as an associative array

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageGeometry</span> ( <span
class="methodparam">void</span> )

Returns the width and height as an associative array.

### Return Values

Returns an array with the width/height of the image.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::getImageGeometry</span>**

``` php
<?php
function getImageGeometry($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::getImageGravity
========================

Gets the image gravity

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageGravity</span> ( <span
class="methodparam">void</span> )

Gets the current gravity value of the image. Unlike <span
class="function">Imagick::getGravity</span>, this method returns the
gravity defined for the current image sequence. This method is available
if Imagick has been compiled against ImageMagick version 6.4.4 or newer.

### Return Values

Returns the images gravity property. Refer to the list of
<a href="/imagick/constants.html#GRAVITY%20constants" class="link">gravity constants</a>.

Imagick::getImageGreenPrimary
=============================

Returns the chromaticy green primary point

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageGreenPrimary</span> ( <span
class="methodparam">void</span> )

Returns the chromaticity green primary point. Returns an array with the
keys "x" and "y".

### Return Values

Returns an array with the keys "x" and "y" on success, throws an
ImagickException on failure.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageHeight
=======================

Returns the image height

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageHeight</span> ( <span
class="methodparam">void</span> )

Returns the image height.

### Return Values

Returns the image height in pixels.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageHistogram
==========================

Gets the image histogram

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageHistogram</span> ( <span
class="methodparam">void</span> )

Returns the image histogram as an array of ImagickPixel objects.

### Return Values

Returns the image histogram as an array of ImagickPixel objects.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Generates <span
class="function">Imagick::getImageHistogram</span>**

``` php
<?php
function getColorStatistics($histogramElements, $colorChannel) {
    $colorStatistics = [];

    foreach ($histogramElements as $histogramElement) {
        $color = $histogramElement->getColorValue($colorChannel);
        $color = intval($color * 255);
        $count = $histogramElement->getColorCount();

        if (array_key_exists($color, $colorStatistics)) {
            $colorStatistics[$color] += $count;
        }
        else {
            $colorStatistics[$color] = $count;
        }
    }

    ksort($colorStatistics);
    
    return $colorStatistics;
}
    


function getImageHistogram($imagePath) {

    $backgroundColor = 'black';

    $draw = new \ImagickDraw();
    $draw->setStrokeWidth(0); //make the lines be as thin as possible

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    $histogramWidth = 256;
    $histogramHeight = 100; // the height for each RGB segment

    $imagick = new \Imagick(realpath($imagePath));
    //Resize the image to be small, otherwise PHP tends to run out of memory
    //This might lead to bad results for images that are pathologically 'pixelly'
    $imagick->adaptiveResizeImage(200, 200, true);
    $histogramElements = $imagick->getImageHistogram();

    $histogram = new \Imagick();
    $histogram->newpseudoimage($histogramWidth, $histogramHeight * 3, 'xc:black');
    $histogram->setImageFormat('png');

    $getMax = function ($carry, $item)  {
        if ($item > $carry) {
            return $item;
        }
        return $carry;
    };

    $colorValues = [
        'red' => getColorStatistics($histogramElements, \Imagick::COLOR_RED),
        'lime' => getColorStatistics($histogramElements, \Imagick::COLOR_GREEN),
        'blue' => getColorStatistics($histogramElements, \Imagick::COLOR_BLUE),
    ];

    $max = array_reduce($colorValues['red'] , $getMax, 0);
    $max = array_reduce($colorValues['lime'] , $getMax, $max);
    $max = array_reduce($colorValues['blue'] , $getMax, $max);

    $scale =  $histogramHeight / $max;

    $count = 0;
    foreach ($colorValues as $color => $values) {
        $draw->setstrokecolor($color);

        $offset = ($count + 1) * $histogramHeight;

        foreach ($values as $index => $value) {
            $draw->line($index, $offset, $index, $offset - ($value * $scale));
        }
        $count++;
    }

    $histogram->drawImage($draw);
    
    header( "Content-Type: image/png" );
    echo $histogram;
}

?>
```

Imagick::getImageIndex
======================

Gets the index of the current active image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageIndex</span> ( <span
class="methodparam">void</span> )

Returns the index of the current active image within the Imagick object.
This method has been deprecated. See <span
class="function">Imagick::getIteratorIndex</span>.

### Return Values

Returns an integer containing the index of the image in the stack.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageInterlaceScheme
================================

Gets the image interlace scheme

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageInterlaceScheme</span> ( <span
class="methodparam">void</span> )

Gets the image interlace scheme.

### Return Values

Returns the interlace scheme as an integer on success. Throw an <span
class="classname">ImagickException</span> on error.

Imagick::getImageInterpolateMethod
==================================

Returns the interpolation method

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageInterpolateMethod</span> ( <span
class="methodparam">void</span> )

Returns the interpolation method for the specified image. The method is
one of the **`Imagick::INTERPOLATE_*`** constants.

### Return Values

Returns the interpolate method on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageIterations
===========================

Gets the image iterations

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageIterations</span> ( <span
class="methodparam">void</span> )

Gets the image iterations.

### Return Values

Returns the image iterations as an integer.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageLength
=======================

Returns the image length in bytes

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageLength</span> ( <span
class="methodparam">void</span> )

Returns the image length in bytes

### Return Values

Returns an int containing the current image size.

### Examples

**Example \#1 Using <span
class="function">Imagick::getImageLength</span>:**

Getting image length in bytes

``` php
<?php
$image = new Imagick('test.jpg');
echo $image->getImageLength() . ' bytes';
?>
```

Imagick::getImageMatte
======================

Return if the image has a matte channel

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::getImageMatte</span> ( <span
class="methodparam">void</span> )

Returns **`true`** if the image has a matte channel otherwise false.
This method is available if Imagick has been compiled against
ImageMagick version 6.2.9 or newer.

### Return Values

Returns **`true`** on success.

Imagick::getImageMatteColor
===========================

Returns the image matte color

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">Imagick::getImageMatteColor</span> ( <span
class="methodparam">void</span> )

Returns the image matte color.

### Return Values

Returns ImagickPixel object on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageMimeType
=========================

Description

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageMimeType</span> ( <span
class="methodparam">void</span> )

Returns the image mime-type.

### Parameters

This function has no parameters.

### Return Values

Imagick::getImageOrientation
============================

Gets the image orientation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageOrientation</span> ( <span
class="methodparam">void</span> )

Gets the image orientation. The return value is one of the
<a href="/imagick/constants.html#ORIENTATION%20constants" class="link">orientation constants</a>.

### Return Values

Returns an int on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImagePage
=====================

Returns the page geometry

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImagePage</span> ( <span
class="methodparam">void</span> )

Returns the page geometry associated with the image in an array with the
keys "width", "height", "x", and "y".

### Return Values

Returns the page geometry associated with the image in an array with the
keys "width", "height", "x", and "y".

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImagePixelColor
===========================

Returns the color of the specified pixel

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">Imagick::getImagePixelColor</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> )

Returns the color of the specified pixel.

### Parameters

`x`  
The x-coordinate of the pixel

`y`  
The y-coordinate of the pixel

### Return Values

Returns an ImagickPixel instance for the color at the coordinates given.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageProfile
========================

Returns the named image profile

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Returns the named image profile.

### Parameters

`name`  
The name of the profile to return.

### Return Values

Returns a string containing the image profile.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageProfiles
=========================

Returns the image profiles

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageProfiles</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$include_values`<span class="initializer"> = **`true`**</span></span>
\]\] )

Returns all associated profiles that match the pattern. If **`false`**
is passed as second parameter only the profile names are returned. This
method is available if Imagick has been compiled against ImageMagick
version 6.3.6 or newer.

### Parameters

`pattern`  
The pattern for profile names.

`include_values`  
Whether to return only profile names. If **`false`** then only profile
names will be returned.

### Return Values

Returns an array containing the image profiles or profile names.

Imagick::getImageProperties
===========================

Returns the image properties

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageProperties</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$include_values`<span class="initializer"> = **`true`**</span></span>
\]\] )

Returns all associated properties that match the pattern. If **`false`**
is passed as second parameter only the property names are returned. This
method is available if Imagick has been compiled against ImageMagick
version 6.3.6 or newer.

### Parameters

`pattern`  
The pattern for property names.

`include_values`  
Whether to return only property names. If **`false`** then only property
names will be returned.

### Return Values

Returns an array containing the image properties or property names.

### Examples

**Example \#1 Using <span
class="function">Imagick::getImageProperties</span>:**

An example of extracting EXIF information.

``` php
<?php

/* Create the object */
$im = new imagick("/path/to/example.jpg");

/* Get the EXIF information */
$exifArray = $im->getImageProperties("exif:*");

/* Loop trough the EXIF properties */
foreach ($exifArray as $name => $property)
{
    echo "{$name} => {$property}<br />\n"; 
}

?>
```

Imagick::getImageProperty
=========================

Returns the named image property

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Returns the named image property. This method is available if Imagick
has been compiled against ImageMagick version 6.3.2 or newer.

### Parameters

`name`  
name of the property (for example Exif:DateTime)

### Examples

**Example \#1 Using <span
class="function">Imagick::getImageProperty</span>:**

Setting and getting image property

``` php
<?php
$image = new Imagick();
$image->newImage(300, 200, "black");

$image->setImageProperty('Exif:Make', 'Imagick');
echo $image->getImageProperty('Exif:Make');
?>
```

### See Also

-   <span class="function">Imagick::setImageProperty</span>

### Return Values

Returns a string containing the image property, false if a property with
the given name does not exist.

Imagick::getImageRedPrimary
===========================

Returns the chromaticity red primary point

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageRedPrimary</span> ( <span
class="methodparam">void</span> )

Returns the chromaticity red primary point as an array with the keys "x"
and "y".

### Return Values

Returns the chromaticity red primary point as an array with the keys "x"
and "y". Throw an <span class="classname">ImagickException</span> on
error.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageRegion
=======================

Extracts a region of the image

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::getImageRegion</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Extracts a region of the image and returns it as a new Imagick object.

### Parameters

`width`  
The width of the extracted region.

`height`  
The height of the extracted region.

`x`  
X-coordinate of the top-left corner of the extracted region.

`y`  
Y-coordinate of the top-left corner of the extracted region.

### Return Values

Extracts a region of the image and returns it as a new wand.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageRenderingIntent
================================

Gets the image rendering intent

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageRenderingIntent</span> ( <span
class="methodparam">void</span> )

Gets the image rendering intent.

### Return Values

Returns the image
<a href="/imagick/constants.html#RENDERINGINTENT%20constants" class="link">rendering intent</a>.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageResolution
===========================

Gets the image X and Y resolution

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageResolution</span> ( <span
class="methodparam">void</span> )

Gets the image X and Y resolution.

### Return Values

Returns the resolution as an array.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImagesBlob
======================

Returns all image sequences as a blob

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImagesBlob</span> ( <span
class="methodparam">void</span> )

Implements direct to memory image formats. It returns all image
sequences as a string. The format of the image determines the format of
the returned blob (GIF, JPEG, PNG, etc.). To return a different image
format, use Imagick::setImageFormat().

### Return Values

Returns a string containing the images. On failure, throws
ImagickException.

Imagick::getImageScene
======================

Gets the image scene

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageScene</span> ( <span
class="methodparam">void</span> )

Gets the image scene.

### Return Values

Returns the image scene.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageSignature
==========================

Generates an SHA-256 message digest

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getImageSignature</span> ( <span
class="methodparam">void</span> )

Generates an SHA-256 message digest for the image pixel stream.

### Return Values

Returns a string containing the SHA-256 hash of the file.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageSize
=====================

Returns the image length in bytes

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageSize</span> ( <span
class="methodparam">void</span> )

Returns the image length in bytes. Deprecated in favour of
<a href="/class/imagick.html#Imagick::getImageLength" class="link">Imagick::getImageLength()</a>

### Return Values

Returns an int containing the current image size.

Imagick::getImageTicksPerSecond
===============================

Gets the image ticks-per-second

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageTicksPerSecond</span> ( <span
class="methodparam">void</span> )

Gets the image ticks-per-second.

### Return Values

Returns the image ticks-per-second.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageTotalInkDensity
================================

Gets the image total ink density

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getImageTotalInkDensity</span> ( <span
class="methodparam">void</span> )

Gets the image total ink density.

### Return Values

Returns the image total ink density of the image. Throw an <span
class="classname">ImagickException</span> on error.

Imagick::getImageType
=====================

Gets the potential image type

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageType</span> ( <span
class="methodparam">void</span> )

Gets the potential image type.

### Return Values

Returns the potential image type.

-   <span class="simpara"> **`imagick::IMGTYPE_UNDEFINED`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_BILEVEL`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_GRAYSCALE`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_GRAYSCALEMATTE`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_PALETTE`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_PALETTEMATTE`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_TRUECOLOR`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_TRUECOLORMATTE`** </span>
-   <span class="simpara"> **`imagick::IMGTYPE_COLORSEPARATION`**
    </span>
-   <span class="simpara"> **`imagick::IMGTYPE_COLORSEPARATIONMATTE`**
    </span>
-   <span class="simpara"> **`imagick::IMGTYPE_OPTIMIZE`** </span>

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageUnits
======================

Gets the image units of resolution

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageUnits</span> ( <span
class="methodparam">void</span> )

Gets the image units of resolution.

### Return Values

Returns the image units of resolution.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageVirtualPixelMethod
===================================

Returns the virtual pixel method

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageVirtualPixelMethod</span> ( <span
class="methodparam">void</span> )

Returns the virtual pixel method for the specified image.

### Return Values

Returns the virtual pixel method on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageWhitePoint
===========================

Returns the chromaticity white point

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getImageWhitePoint</span> ( <span
class="methodparam">void</span> )

Returns the chromaticity white point as an associative array with the
keys "x" and "y".

### Return Values

Returns the chromaticity white point as an associative array with the
keys "x" and "y".

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getImageWidth
======================

Returns the image width

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getImageWidth</span> ( <span
class="methodparam">void</span> )

Returns the image width.

### Return Values

Returns the image width.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getInterlaceScheme
===========================

Gets the object interlace scheme

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getInterlaceScheme</span> ( <span
class="methodparam">void</span> )

Gets the object interlace scheme.

### Return Values

Gets the wand
<a href="/imagick/constants.html#INTERLACE%20constants" class="link">interlace scheme</a>.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getIteratorIndex
=========================

Gets the index of the current active image

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getIteratorIndex</span> ( <span
class="methodparam">void</span> )

Returns the index of the current active image within the Imagick object.
This method is available if Imagick has been compiled against
ImageMagick version 6.2.9 or newer.

### Return Values

Returns an integer containing the index of the image in the stack.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::getIteratorIndex</span>:**

Create images, set and get the iterator index

``` php
<?php
$im = new Imagick();
$im->newImage(100, 100, new ImagickPixel("red"));
$im->newImage(100, 100, new ImagickPixel("green"));
$im->newImage(100, 100, new ImagickPixel("blue"));

$im->setIteratorIndex(1);
echo $im->getIteratorIndex();
?>
```

### See Also

-   <span class="function">Imagick::setIteratorIndex</span>
-   <span class="function">Imagick::getImageIndex</span>
-   <span class="function">Imagick::setImageIndex</span>

Imagick::getNumberImages
========================

Returns the number of images in the object

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getNumberImages</span> ( <span
class="methodparam">void</span> )

Returns the number of images associated with Imagick object.

### Return Values

Returns the number of images associated with Imagick object.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getOption
==================

Returns a value associated with the specified key

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::getOption</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Returns a value associated within the object for the specified key.

### Parameters

`key`  
The name of the option

### Return Values

Returns a value associated with a wand and the specified key.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getPackageName
=======================

Returns the ImageMagick package name

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Imagick::getPackageName</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick package name.

### Return Values

Returns the ImageMagick package name as a string.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getPage
================

Returns the page geometry

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getPage</span> ( <span
class="methodparam">void</span> )

Returns the page geometry associated with the Imagick object in an
associative array with the keys "width", "height", "x", and "y".

### Return Values

Returns the page geometry associated with the Imagick object in an
associative array with the keys "width", "height", "x", and "y",
throwing ImagickException on error.

Imagick::getPixelIterator
=========================

Returns a MagickPixelIterator

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixelIterator</span> <span
class="methodname">Imagick::getPixelIterator</span> ( <span
class="methodparam">void</span> )

Returns a MagickPixelIterator.

### Return Values

Returns an ImagickPixelIterator on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::getPixelIterator</span>**

``` php
<?php
function getPixelIterator($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imageIterator = $imagick->getPixelIterator();

    foreach ($imageIterator as $row => $pixels) { /* Loop through pixel rows */
        foreach ($pixels as $column => $pixel) { /* Loop through the pixels in the row (columns) */
            /** @var $pixel \ImagickPixel */
            if ($column % 2) {
                $pixel->setColor("rgba(0, 0, 0, 0)"); /* Paint every second pixel black*/
            }
        }
        $imageIterator->syncIterator(); /* Sync the iterator, this is important to do on each iteration */
    }

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

Imagick::getPixelRegionIterator
===============================

Get an ImagickPixelIterator for an image section

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixelIterator</span> <span
class="methodname">Imagick::getPixelRegionIterator</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

Get an ImagickPixelIterator for an image section.

### Parameters

`x`  
The x-coordinate of the region.

`y`  
The y-coordinate of the region.

`columns`  
The width of the region.

`rows`  
The height of the region.

### Return Values

Returns an ImagickPixelIterator for an image section.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span
class="methodname">Imagick::getPixelRegionIterator</span> example**

Iterate over the pixels in the top left of the image, changing them to
be black.

``` php
<?php
$im = new Imagick(realpath("./testImage.png"));
$areaIterator = $im->getPixelRegionIterator(0, 0, 10, 10);

foreach ($areaIterator as $rowIterator) {
    foreach ($rowIterator as $pixel) {
        // Paint every pixel black
        $pixel->setColor("rgba(0, 0, 0, 0)");
    }
    $areaIterator->syncIterator();
}
$im->writeImage("./output.png");
?>
```

Imagick::getPointSize
=====================

Gets point size

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">Imagick::getPointSize</span> ( <span
class="methodparam">void</span> )

Returns the objects point size property. This method is available if
Imagick has been compiled against ImageMagick version 6.3.7 or newer.

### Return Values

Returns a <span class="type">float</span> containing the point size.

### See Also

-   <span class="function">Imagick::setPointSize</span>

Imagick::getQuantum
===================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Imagick::getQuantum</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick quantum range as an integer.

### Parameters

This function has no parameters.

### Return Values

Imagick::getQuantumDepth
========================

Gets the quantum depth

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::getQuantumDepth</span> ( <span
class="methodparam">void</span> )

Returns the Imagick quantum depth.

### Return Values

Returns an array with *"quantumDepthLong"* and *"quantumDepthString"*
members.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getQuantumRange
========================

Returns the Imagick quantum range

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::getQuantumRange</span> ( <span
class="methodparam">void</span> )

Returns the quantum range for the Imagick instance.

### Return Values

Returns an associative array containing the quantum range as an <span
class="type">int</span> (*"quantumRangeLong"*) and as a <span
class="type">string</span> (*"quantumRangeString"*).

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getRegistry
====================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Imagick::getRegistry</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Get the StringRegistry entry for the named key or false if not set.

### Parameters

`key`  
The entry to get.

### Return Values

Imagick::getReleaseDate
=======================

Returns the ImageMagick release date

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Imagick::getReleaseDate</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick release date as a string.

### Return Values

Returns the ImageMagick release date as a string.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getResource
====================

Returns the specified resource's memory usage

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Imagick::getResource</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> )

Returns the specified resource's memory usage in megabytes.

### Parameters

`type`  
Refer to the list of
<a href="/imagick/constants.html#RESOURCETYPE%20constants" class="link">resourcetype constants</a>.

### Return Values

Returns the specified resource's memory usage in megabytes.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getResourceLimit
=========================

Returns the specified resource limit

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Imagick::getResourceLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> )

Returns the specified resource limit.

### Parameters

`type`  
One of the
<a href="/imagick/constants.html#RESOURCETYPE%20constants" class="link">resourcetype constants</a>.
The unit depends on the type of the resource being limited.

### Return Values

Returns the specified resource limit in megabytes.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="methodname">Imagick::setResourceLimit</span>

Imagick::getSamplingFactors
===========================

Gets the horizontal and vertical sampling factor

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getSamplingFactors</span> ( <span
class="methodparam">void</span> )

Gets the horizontal and vertical sampling factor.

### Return Values

Returns an associative array with the horizontal and vertical sampling
factors of the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getSize
================

Returns the size associated with the Imagick object

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::getSize</span> ( <span
class="methodparam">void</span> )

Get the size in pixels associated with the Imagick object, previously
set by <span class="function">Imagick::setSize</span>.

> **Note**:
>
> This method just returns the size that was set using <span
> class="function">Imagick::setSize</span>. If you want to get the
> actual width / height of the image, use <span
> class="function">Imagick::getImageWidth</span> and <span
> class="function">Imagick::getImageHeight</span>.

### Return Values

Returns the size associated with the Imagick object as an array with the
keys "columns" and "rows".

### Examples

**Example \#1 Getting the size of a raw RGB image set at 200x400, after
scaling to 400x800 (compared to width / height)**

``` php
<?php
//Set size first and then load the raw image
$img = new Imagick();
$img->setSize(200, 400);
$img->readImage("image.rgb");

$img->scaleImage(400, 800);

$size = $img->getSize();
print_r($size);

echo "$img->getImageWidth()."x".$img->getImageHeight();
?>
```

The above example will output:

    Array
    (
        [columns] => 200
        [rows] => 400
    )
    400x800

Imagick::getSizeOffset
======================

Returns the size offset

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Imagick::getSizeOffset</span> ( <span
class="methodparam">void</span> )

Returns the size offset associated with the Imagick object. This method
is available if Imagick has been compiled against ImageMagick version
6.2.9 or newer.

### Return Values

Returns the size offset associated with the Imagick object.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::getVersion
===================

Returns the ImageMagick API version

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::getVersion</span> ( <span
class="methodparam">void</span> )

Returns the ImageMagick API version as a string and as a number.

### Return Values

Returns the ImageMagick API version as a string and as a number.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::haldClutImage
======================

Replaces colors in the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::haldClutImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$clut`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Replaces colors in the image using a Hald lookup table. Hald images can
be created using HALD color coder.

### Parameters

`clut`  
Imagick object containing the Hald lookup image.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::haldClutImage</span>**

``` php
<?php
function haldClutImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagickPalette = new \Imagick(realpath("images/hald/hald_8.png"));
    $imagickPalette->sepiatoneImage(55);
    $imagick->haldClutImage($imagickPalette);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::hasNextImage
=====================

Checks if the object has more images

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::hasNextImage</span> ( <span
class="methodparam">void</span> )

Returns **`true`** if the object has more images when traversing the
list in the forward direction.

### Return Values

Returns **`true`** if the object has more images when traversing the
list in the forward direction, returns **`false`** if there are none.

Imagick::hasPreviousImage
=========================

Checks if the object has a previous image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::hasPreviousImage</span> ( <span
class="methodparam">void</span> )

Returns **`true`** if the object has more images when traversing the
list in the reverse direction

### Return Values

Returns **`true`** if the object has more images when traversing the
list in the reverse direction, returns **`false`** if there are none.

Imagick::identifyFormat
=======================

Description

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">Imagick::identifyFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$embedText`</span>
)

Replaces any embedded formatting characters with the appropriate image
property and returns the interpreted text. See
http://www.imagemagick.org/script/escape.php for escape sequences.

### Parameters

`embedText`  
A string containing formatting sequences e.g. "Trim box: %@ number of
unique colors: %k".

### Return Values

Returns format or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Imagick::identifyFormat</span>**

``` php
<?php
        $output = "Output of 'Trim box: %@ number of unique colors: %k' is: <br/>";
        $imagick = new \Imagick(realpath("./images/artifact/mask.png"));
        $output .= $imagick->identifyFormat("Trim box: %@ number of unique colors: %k");

?>
```

Imagick::identifyImage
======================

Identifies an image and fetches attributes

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::identifyImage</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$appendRawOutput`<span class="initializer"> = **`false`**</span></span>
\] )

Identifies an image and returns the attributes. Attributes include the
image width, height, size, and others.

### Parameters

`appendRawOutput`  
If **`true`** then the raw output is appended to the array.

### Return Values

Identifies an image and returns the attributes. Attributes include the
image width, height, size, and others.

**Example \#1 Example Result Format**

``` examples
Array
(
    [imageName] => /some/path/image.jpg
    [format] => JPEG (Joint Photographic Experts Group JFIF format)
    [geometry] => Array
        (
            [width] => 90
            [height] => 90
        )

    [type] => TrueColor
    [colorSpace] => RGB
    [resolution] => Array
        (
            [x] => 300
            [y] => 300
        )

    [units] => PixelsPerInch
    [fileSize] => 1.88672kb
    [compression] => JPEG
    [signature] => 9a6dc8f604f97d0d691c0286176ddf992e188f0bebba98494b2146ee2d7118da
)
```

### Errors/Exceptions

Throws ImagickException on error.

Imagick::implodeImage
=====================

Creates a new image as a copy

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::implodeImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Creates a new image that is a copy of an existing one with the image
pixels "imploded" by the specified percentage.

### Parameters

`radius`  
The radius of the implode

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::implodeImage</span>**

``` php
<?php
function implodeImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->implodeImage(0.0001);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();

}

?>
```

Imagick::importImagePixels
==========================

Imports image pixels

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::importImagePixels</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">string</span>
`$map`</span> , <span class="methodparam"><span class="type">int</span>
`$storage`</span> , <span class="methodparam"><span
class="type">array</span> `$pixels`</span> )

Imports pixels from an array into an image. The `map` is usually 'RGB'.
This method imposes the following constraints for the parameters: amount
of pixels in the array must match `width` x `height` x length of the
map. This method is available if Imagick has been compiled against
ImageMagick version 6.4.5 or newer.

### Parameters

`x`  
The image x position

`y`  
The image y position

`width`  
The image width

`height`  
The image height

`map`  
Map of pixel ordering as a string. This can be for example *RGB*. The
value can be any combination or order of R = red, G = green, B = blue, A
= alpha (0 is transparent), O = opacity (0 is opaque), C = cyan, Y =
yellow, M = magenta, K = black, I = intensity (for grayscale), P = pad.

`storage`  
The pixel storage method. Refer to this list of
<a href="/imagick/constants.html#PIXEL%20constants" class="link">pixel constants</a>.

`pixels`  
The array of pixels

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="methodname">Imagick::importImagePixels</span>
example**

``` php
<?php

/* Generate array of pixels. 2000 pixels per color stripe */
$count = 2000 * 3;

$pixels = 
   array_merge(array_pad(array(), $count, 0),
               array_pad(array(), $count, 255), 
               array_pad(array(), $count, 0),
               array_pad(array(), $count, 255),
               array_pad(array(), $count, 0));

/* Width and height. The area is amount of pixels divided
   by three. Three comes from 'RGB', three values per pixel */
$width = $height = pow((count($pixels) / 3), 0.5);

/* Create empty image */
$im = new Imagick();
$im->newImage($width, $height, 'gray');

/* Import the pixels into image.
   width * height * strlen("RGB") must match count($pixels) */
$im->importImagePixels(0, 0, $width, $height, "RGB", Imagick::PIXEL_CHAR, $pixels);

/* output as jpeg image */
$im->setImageFormat('jpg');
header("Content-Type: image/jpg");
echo $im;

?>
```

The above example will output something similar to:

<img src="images/c0d23d2d6769e53e24a1b3136c064577-importimagepixels.jpg" width="100" height="100" alt="Output of example : Imagick::importImagePixels()" />

Imagick::inverseFourierTransformImage
=====================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::inverseFourierTransformImage</span> (
<span class="methodparam"><span class="type">Imagick</span>
`$complement`</span> , <span class="methodparam"><span
class="type">bool</span> `$magnitude`</span> )

Implements the inverse discrete Fourier transform (DFT) of the image
either as a magnitude / phase or real / imaginary image pair.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`complement`  
The second image to combine with this one to form either the magnitude /
phase or real / imaginary image pair.

`magnitude`  
If true, combine as magnitude / phase pair otherwise a real / imaginary
image pair.

### Return Values

Returns **`true`** on success.

Imagick::labelImage
===================

Adds a label to an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::labelImage</span> ( <span
class="methodparam"><span class="type">string</span> `$label`</span> )

Adds a label to an image.

### Parameters

`label`  
The label to add

### Return Values

Returns **`true`** on success.

Imagick::levelImage
===================

Adjusts the levels of an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::levelImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$gamma`</span> , <span class="methodparam"><span
class="type">float</span> `$whitePoint`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adjusts the levels of an image by scaling the colors falling between
specified white and black points to the full available quantum range.
The parameters provided represent the black, mid, and white points. The
black point specifies the darkest color in the image. Colors darker than
the black point are set to zero. Mid point specifies a gamma correction
to apply to the image. White point specifies the lightest color in the
image. Colors brighter than the white point are set to the maximum
quantum value.

### Parameters

`blackPoint`  
The image black point

`gamma`  
The gamma value

`whitePoint`  
The image white point

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::levelImage</span>**

``` php
<?php
function levelImage($blackPoint, $gamma, $whitePoint) {
    $imagick = new \Imagick();
    $imagick->newPseudoimage(500, 500, 'gradient:black-white');

    $imagick->setFormat('png');
    $quantum = $imagick->getQuantum();
    $imagick->levelImage($blackPoint / 100 , $gamma, $quantum * $whitePoint / 100);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::linearStretchImage
===========================

Stretches with saturation the image intensity

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::linearStretchImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$whitePoint`</span> )

Stretches with saturation the image intensity.

### Parameters

`blackPoint`  
The image black point

`whitePoint`  
The image white point

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::linearStretchImage</span>**

``` php
<?php
function linearStretchImage($imagePath, $blackThreshold, $whiteThreshold) {
    $imagick = new \Imagick(realpath($imagePath));
    $pixels = $imagick->getImageWidth() * $imagick->getImageHeight();
    $imagick->linearStretchImage($blackThreshold * $pixels, $whiteThreshold * $pixels);

    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::liquidRescaleImage
===========================

Animates an image or images

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::liquidRescaleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">float</span>
`$delta_x`</span> , <span class="methodparam"><span
class="type">float</span> `$rigidity`</span> )

This method scales the images using liquid rescaling method. This method
is an implementation of a technique called seam carving. In order for
this method to work as expected ImageMagick must be compiled with liblqr
support. This method is available if Imagick has been compiled against
ImageMagick version 6.3.9 or newer.

### Parameters

`width`  
The width of the target size

`height`  
The height of the target size

`delta_x`  
How much the seam can traverse on x-axis. Passing 0 causes the seams to
be straight.

`rigidity`  
Introduces a bias for non-straight seams. This parameter is typically 0.

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::resizeImage</span>

Imagick::listRegistry
=====================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::listRegistry</span> ( <span
class="methodparam">void</span> )

List all the registry settings. Returns an array of all the key/value
pairs in the registry

### Parameters

This function has no parameters.

### Return Values

An array containing the key/values from the registry.

Imagick::magnifyImage
=====================

Scales an image proportionally 2x

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::magnifyImage</span> ( <span
class="methodparam">void</span> )

Is a convenience method that scales an image proportionally to twice its
original size.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::magnifyImage</span>**

``` php
<?php
function magnifyImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->magnifyImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::mapImage
=================

Replaces the colors of an image with the closest color from a reference
image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::mapImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$map`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$dither`</span> )

### Parameters

`map`  

`dither`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::matteFloodfillImage
============================

Changes the transparency value of a color

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::matteFloodfillImage</span> ( <span
class="methodparam"><span class="type">float</span> `$alpha`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

Changes the transparency value of any pixel that matches target and is
an immediate neighbor. If the method **`FillToBorderMethod`** is
specified, the transparency value is changed for any neighbor pixel that
does not match the bordercolor member of image.

### Parameters

`alpha`  
The level of transparency: 1.0 is fully opaque and 0.0 is fully
transparent.

`fuzz`  
The fuzz member of image defines how much tolerance is acceptable to
consider two colors as the same.

`bordercolor`  
An <span class="classname">ImagickPixel</span> object or string
representing the border color.

`x`  
The starting x coordinate of the operation.

`y`  
The starting y coordinate of the operation.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the third parameter. Previous versions allow only an <span class="classname">ImagickPixel</span> object. |

Imagick::medianFilterImage
==========================

Applies a digital filter

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::medianFilterImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Applies a digital filter that improves the quality of a noisy image.
Each pixel is replaced by the median in a set of neighboring pixels as
defined by radius.

### Parameters

`radius`  
The radius of the pixel neighborhood.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::medianFilterImage</span>**

``` php
<?php
function medianFilterImage($radius, $imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    @$imagick->medianFilterImage($radius);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::mergeImageLayers
=========================

Merges image layers

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::mergeImageLayers</span> ( <span
class="methodparam"><span class="type">int</span> `$layer_method`</span>
)

Merges image layers into one. This method is useful when working with
image formats that use multiple layers such as PSD. The merging is
controlled using the `layer_method` which defines how the layers are
merged. This method is available if Imagick has been compiled against
ImageMagick version 6.3.7 or newer.

### Parameters

`layer_method`  
One of the **`Imagick::LAYERMETHOD_*`** constants

### Return Values

Returns an Imagick object containing the merged image.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::flattenImages</span>

### Examples

**Example \#1 <span class="function">Imagick::mergeImageLayers</span>**

``` php
<?php
function mergeImageLayers($layerMethodType, $imagePath1, $imagePath2) {

    $imagick = new \Imagick(realpath($imagePath));

    $imagick2 = new \Imagick(realpath($imagePath2));
    $imagick->addImage($imagick2);
    $imagick->setImageFormat('png');

    $result = $imagick->mergeImageLayers($layerMethodType);
    header("Content-Type: image/png");
    echo $result->getImageBlob();
}

?>
```

Imagick::minifyImage
====================

Scales an image proportionally to half its size

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::minifyImage</span> ( <span
class="methodparam">void</span> )

Is a convenience method that scales an image proportionally to one-half
its original size

### Return Values

Returns **`true`** on success.

Imagick::modulateImage
======================

Control the brightness, saturation, and hue

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::modulateImage</span> ( <span
class="methodparam"><span class="type">float</span> `$brightness`</span>
, <span class="methodparam"><span class="type">float</span>
`$saturation`</span> , <span class="methodparam"><span
class="type">float</span> `$hue`</span> )

Lets you control the brightness, saturation, and hue of an image. Hue is
the percentage of absolute rotation from the current position. For
example 50 results in a counter-clockwise rotation of 90 degrees, 150
results in a clockwise rotation of 90 degrees, with 0 and 200 both
resulting in a rotation of 180 degrees.

### Parameters

`brightness`  

`saturation`  

`hue`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::modulateImage</span>**

``` php
<?php
function modulateImage($imagePath, $hue, $brightness, $saturation) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->modulateImage($brightness, $saturation, $hue);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::montageImage
=====================

Creates a composite image

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::montageImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span> `$draw`</span>
, <span class="methodparam"><span class="type">string</span>
`$tile_geometry`</span> , <span class="methodparam"><span
class="type">string</span> `$thumbnail_geometry`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> , <span
class="methodparam"><span class="type">string</span> `$frame`</span> )

Creates a composite image by combining several separate images. The
images are tiled on the composite image with the name of the image
optionally appearing just below the individual tile.

### Parameters

`draw`  
The font name, size, and color are obtained from this object.

`tile_geometry`  
The number of tiles per row and page (e.g. 6x4+0+0).

`thumbnail_geometry`  
Preferred image size and border size of each thumbnail (e.g.
120x120+4+3\>).

`mode`  
Thumbnail framing mode, see
<a href="/imagick/constants.html#MONTAGEMODE%20constants" class="link">Montage Mode constants</a>.

`frame`  
Surround the image with an ornamental border (e.g. 15x15+3+3). The frame
color is that of the thumbnail's matte color.

### Return Values

Returns **`true`** on success.

Imagick::morphImages
====================

Method morphs a set of images

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::morphImages</span> ( <span
class="methodparam"><span class="type">int</span>
`$number_frames`</span> )

Method morphs a set of images. Both the image pixels and size are
linearly interpolated to give the appearance of a meta-morphosis from
one image to the next.

### Parameters

`number_frames`  
The number of in-between images to generate.

### Return Values

This method returns a new Imagick object on success. Throw an <span
class="classname">ImagickException</span> on error.

Imagick::morphology
===================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::morphology</span> ( <span
class="methodparam"><span class="type">int</span>
`$morphologyMethod`</span> , <span class="methodparam"><span
class="type">int</span> `$iterations`</span> , <span
class="methodparam"><span class="type">ImagickKernel</span>
`$ImagickKernel`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Applies a user supplied kernel to the image according to the given
morphology method.

### Parameters

`morphologyMethod`  
Which morphology method to use one of the \\Imagick::MORPHOLOGY\_\*
constants.

`iterations`  
The number of iteration to apply the morphology function. A value of -1
means loop until no change found. How this is applied may depend on the
morphology method. Typically this is a value of 1.

`ImagickKernel`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Convolve <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $imagick = $this->getCharacter();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_GAUSSIAN, "5,1");
        $imagick->morphology(\Imagick::MORPHOLOGY_CONVOLVE, 2, $kernel);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();

?>
```

**Example \#2 Correlate <span
class="function">Imagick::morphology</span>**

``` php
<?php

        // Top-left pixel must be black
        // Bottom right pixel must be white
        // We don't care about the rest.
        

        $imagick = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromMatrix(self::$correlateMatrix, [2, 2]);
        $imagick->morphology(\Imagick::MORPHOLOGY_CORRELATE, 1, $kernel);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();

?>
```

**Example \#3 Erode <span class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_ERODE, 2, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#4 Erode Intensity <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacter();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "1");
        $canvas->morphology(\Imagick::MORPHOLOGY_ERODE_INTENSITY, 2, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#5 Dilate <span class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_DILATE, 4, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#6 Dilate intensity <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacter();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "1");
        $canvas->morphology(\Imagick::MORPHOLOGY_DILATE_INTENSITY, 4, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#7 Distance with Chebyshev kernel <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_CHEBYSHEV, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_DISTANCE, 3, $kernel);
        $canvas->autoLevelImage();
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#8 Distance with Manhattan kernel <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_MANHATTAN, "5");
        $canvas->morphology(\Imagick::MORPHOLOGY_DISTANCE, 3, $kernel);
        $canvas->autoLevelImage();
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#9 Distance with ocatagonal kernel <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGONAL, "5");
        $canvas->morphology(\Imagick::MORPHOLOGY_DISTANCE, 3, $kernel);
        $canvas->autoLevelImage();
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#10 Distance with Euclidean kernel <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_EUCLIDEAN, "4");
        $canvas->morphology(\Imagick::MORPHOLOGY_DISTANCE, 3, $kernel);
        $canvas->autoLevelImage();
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#11 Edge <span class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_EDGE, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#12 Open <span class="function">Imagick::morphology</span>**

``` php
<?php
        // As a result you will see that 'Open' smoothed the outline, by rounding off any sharp points, and remove any parts that is smaller than the shape used. It will also disconnect or 'open' any thin bridges.
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "6");
        $canvas->morphology(\Imagick::MORPHOLOGY_OPEN, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#13 Open intensity <span
class="function">Imagick::morphology</span>**

``` php
<?php
        // As a result you will see that 'Open' smoothed the outline, by rounding off any sharp points, and remove any parts that is smaller than the shape used. It will also disconnect or 'open' any thin bridges.

        $canvas = $this->getCharacter();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "6");
        $canvas->morphology(\Imagick::MORPHOLOGY_OPEN_INTENSITY, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#14 Close <span class="function">Imagick::morphology</span>**

``` php
<?php
        //The basic use of the 'Close' method is to reduce or remove any 'holes' or 'gaps' about the size of the kernel 'Structure Element'. That is 'close' parts of the background that are about that size.
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "6");
        $canvas->morphology(\Imagick::MORPHOLOGY_CLOSE, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#15 Close Intensity <span
class="function">Imagick::morphology</span>**

``` php
<?php
        //The basic use of the 'Close' method is to reduce or remove any 'holes' or 'gaps' about the size of the kernel 'Structure Element'. That is 'close' parts of the background that are about that size.
        $canvas = $this->getCharacter();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "6");
        $canvas->morphology(\Imagick::MORPHOLOGY_CLOSE_INTENSITY, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#16 Smooth <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_SMOOTH, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#17 Edge in <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_EDGE_IN, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#18 Edge out <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_OCTAGON, "3");
        $canvas->morphology(\Imagick::MORPHOLOGY_EDGE_OUT, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#19 The 'TopHat' method, or more specifically 'White Top
Hat', returns the pixels that were removed by a Opening of the shape,
that is the pixels that were removed to round off the points, and the
connecting bridged between shapes. <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "5");
        $canvas->morphology(\Imagick::MORPHOLOGY_TOP_HAT, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#20 The 'BottomHat' method, also known as 'Black TopHat' is
the pixels that a Closing of the shape adds to the image. That is the
pixels that were used to fill in the 'holes', 'gaps', and 'bridges'.
<span class="function">Imagick::morphology</span>**

``` php
<?php

        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "5");
        $canvas->morphology(\Imagick::MORPHOLOGY_BOTTOM_HAT, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#21 Hit and Miss <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        //This finds all the pixels with 3 pixels of the right edge
        $matrix = [[1, false, false, 0]];
        $kernel = \ImagickKernel::fromMatrix(
            $matrix,
            [0, 0]
        );
        $canvas->morphology(\Imagick::MORPHOLOGY_HIT_AND_MISS, 1, $kernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#22 Thinning <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $leftEdgeKernel = \ImagickKernel::fromMatrix([[0, 1]], [1, 0]);
        $rightEdgeKernel = \ImagickKernel::fromMatrix([[1, 0]], [0, 0]);
        $leftEdgeKernel->addKernel($rightEdgeKernel);
        
        $canvas->morphology(\Imagick::MORPHOLOGY_THINNING, 3, $leftEdgeKernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#23 Thicken <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $leftEdgeKernel = \ImagickKernel::fromMatrix([[0, 1]], [1, 0]);
        $rightEdgeKernel = \ImagickKernel::fromMatrix([[1, 0]], [0, 0]);
        $leftEdgeKernel->addKernel($rightEdgeKernel);

        $canvas->morphology(\Imagick::MORPHOLOGY_THICKEN, 3, $leftEdgeKernel);
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#24 Thick to generate a convex hull <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $diamondKernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DIAMOND, "1");
        $convexKernel =  \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_CONVEX_HULL, "");

        // The thicken morphology doesn't handle small gaps. We close them
        // with the close morphology.
        $canvas->morphology(\Imagick::MORPHOLOGY_CLOSE, 1, $diamondKernel);
        $canvas->morphology(\Imagick::MORPHOLOGY_THICKEN, -1, $convexKernel);
        $canvas->morphology(\Imagick::MORPHOLOGY_CLOSE, 1, $diamondKernel);

        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#25 Iterative morphology <span
class="function">Imagick::morphology</span>**

``` php
<?php
        $canvas = $this->getCharacterOutline();
        $kernel = \ImagickKernel::fromBuiltIn(\Imagick::KERNEL_DISK, "2");        
        $canvas->morphology(\Imagick::MORPHOLOGY_ITERATIVE, 3, $kernel);
        $canvas->autoLevelImage();
        header("Content-Type: image/png");
        echo $canvas->getImageBlob();

?>
```

**Example \#26 Helper functon to get an image silhouette <span
class="function">Imagick::morphology</span>**

``` php
<?php
    private function getCharacterOutline() {

        $imagick = new \Imagick(realpath("./images/character.png"));
        $character = new \Imagick();
        $character->newPseudoImage(
            $imagick->getImageWidth(),
            $imagick->getImageHeight(),
            "canvas:white"
        );
        $canvas = new \Imagick();
        $canvas->newPseudoImage(
            $imagick->getImageWidth(),
            $imagick->getImageHeight(),
            "canvas:black"
        );

        $character->compositeimage(
            $imagick,
            \Imagick::COMPOSITE_COPYOPACITY,
            0, 0
        );
        $canvas->compositeimage(
            $character,
            \Imagick::COMPOSITE_ATOP,
            0, 0
        );
        $canvas->setFormat('png');

        return $canvas;
    }

?>
```

Imagick::mosaicImages
=====================

Forms a mosaic from images

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::mosaicImages</span> ( <span
class="methodparam">void</span> )

Inlays an image sequence to form a single coherent picture. It returns a
wand with each image in the sequence composited at the location defined
by the page offset of the image.

### Return Values

Returns **`true`** on success.

Imagick::motionBlurImage
========================

Simulates motion blur

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::motionBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Simulates motion blur. We convolve the image with a Gaussian operator of
the given radius and standard deviation (sigma). For reasonable results,
radius should be larger than sigma. Use a radius of 0 and
MotionBlurImage() selects a suitable radius for you. Angle gives the
angle of the blurring motion.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel.

`sigma`  
The standard deviation of the Gaussian, in pixels.

`angle`  
Apply the effect along this angle.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.
The channel argument affects only if Imagick is compiled against
ImageMagick version 6.4.4 or greater.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::motionBlurImage</span>**

``` php
<?php
function motionBlurImage($imagePath, $radius, $sigma, $angle, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->motionBlurImage($radius, $sigma, $angle, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::negateImage
====================

Negates the colors in the reference image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::negateImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$gray`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Negates the colors in the reference image. The Grayscale option means
that only grayscale values within the image are negated.

### Parameters

`gray`  
Whether to only negate grayscale pixels within the image.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::negateImage</span>**

``` php
<?php
function negateImage($imagePath, $grayOnly, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->negateImage($grayOnly, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::newImage
=================

Creates a new image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::newImage</span> ( <span
class="methodparam"><span class="type">int</span> `$cols`</span> , <span
class="methodparam"><span class="type">int</span> `$rows`</span> , <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$format`</span> \] )

Creates a new image and associates ImagickPixel value as background
color

### Parameters

`cols`  
Columns in the new image

`rows`  
Rows in the new image

`background`  
The background color used for this image

`format`  
Image format. This parameter was added in Imagick version 2.0.1.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the third parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 Using <span class="function">Imagick::newImage</span>:**

Create a new image and display it.

``` php
<?php

$image = new Imagick();
$image->newImage(100, 100, new ImagickPixel('red'));
$image->setImageFormat('png');

header('Content-type: image/png');
echo $image;

?>
```

Imagick::newPseudoImage
=======================

Creates a new image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::newPseudoImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">string</span>
`$pseudoString`</span> )

Creates a new image using ImageMagick pseudo-formats.

### Parameters

`columns`  
columns in the new image

`rows`  
rows in the new image

`pseudoString`  
string containing pseudo image definition.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::newPseudoImage</span>**

``` php
<?php
function newPseudoImage($canvasType) {
    $imagick = new \Imagick();
    $imagick->newPseudoImage(300, 300, $canvasType);
    $imagick->setImageFormat("png");
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

//newPseudoImage('gradient:red-rgba(64, 255, 255, 0.5)');
//newPseudoImage("radial-gradient:red-blue");
newPseudoImage("plasma:fractal");

?>
```

Imagick::nextImage
==================

Moves to the next image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::nextImage</span> ( <span
class="methodparam">void</span> )

Associates the next image in the image list with an Imagick object.

### Return Values

Returns **`true`** on success.

Imagick::normalizeImage
=======================

Enhances the contrast of a color image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::normalizeImage</span> (\[ <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Enhances the contrast of a color image by adjusting the pixels color to
span the entire range of colors available.

### Parameters

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::normalizeImage</span>**

``` php
<?php
function normalizeImage($imagePath, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $original = clone $imagick;
    $original->cropimage($original->getImageWidth() / 2, $original->getImageHeight(), 0, 0);
    $imagick->normalizeImage($channel);
    $imagick->compositeimage($original, \Imagick::COMPOSITE_ATOP, 0, 0);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::oilPaintImage
======================

Simulates an oil painting

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::oilPaintImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Applies a special effect filter that simulates an oil painting. Each
pixel is replaced by the most frequent color occurring in a circular
region defined by radius.

### Parameters

`radius`  
The radius of the circular neighborhood.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::oilPaintImage</span>**

``` php
<?php
function oilPaintImage($imagePath, $radius) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->oilPaintImage($radius);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::opaquePaintImage
=========================

Changes the color value of any pixel that matches target

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::opaquePaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$fill`</span>
, <span class="methodparam"><span class="type">float</span>
`$fuzz`</span> , <span class="methodparam"><span
class="type">bool</span> `$invert`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes any pixel that matches color with the color defined by fill.
This method is available if Imagick has been compiled against
ImageMagick version 6.3.8 or newer.

### Parameters

`target`  
ImagickPixel object or a string containing the color to change

`fill`  
The replacement color

`fuzz`  
The amount of fuzz. For example, set fuzz to 10 and the color red at
intensities of 100 and 102 respectively are now interpreted as the same
color.

`invert`  
If **`true`** paints any pixel that does not match the target color.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

Imagick::optimizeImageLayers
============================

Removes repeated portions of images to optimize

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::optimizeImageLayers</span> ( <span
class="methodparam">void</span> )

Compares each image the GIF disposed forms of the previous image in the
sequence. From this it attempts to select the smallest cropped image to
replace each frame, while preserving the results of the animation. This
method is available if Imagick has been compiled against ImageMagick
version 6.2.9 or newer.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::optimizeImageLayers</span>**

Reading, optimizing and writing a GIF image

``` php
<?php
/* create new imagick object */
$im = new Imagick("test.gif");

/* optimize the image layers */
$im->optimizeImageLayers();

/* write the image back */
$im->writeImages("test_optimized.gif", true);
?>
```

### See Also

-   <span class="function">Imagick::compareImageLayers</span>
-   <span class="function">Imagick::writeImages</span>
-   <span class="function">Imagick::writeImage</span>

Imagick::orderedPosterizeImage
==============================

Performs an ordered dither

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::orderedPosterizeImage</span> ( <span
class="methodparam"><span class="type">string</span>
`$threshold_map`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Performs an ordered dither based on a number of pre-defined dithering
threshold maps, but over multiple intensity levels, which can be
different for different channels, according to the input arguments. This
method is available if Imagick has been compiled against ImageMagick
version 6.3.1 or newer.

### Parameters

`threshold_map`  
A string containing the name of the threshold dither map to use

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span
class="function">Imagick::orderedPosterizeImage</span>**

``` php
<?php
function orderedPosterizeImage($imagePath, $orderedPosterizeType) {
    $imagick = new \Imagick(realpath($imagePath));
    
  
    $imagick->orderedPosterizeImage($orderedPosterizeType);
    $imagick->setImageFormat('png');
    
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

//orderedPosterizeImage($imagePath, 'o4x4,3,3');
//orderedPosterizeImage($imagePath, 'o8x8,6,6');
orderedPosterizeImage($imagePath, 'h8x8a');





?>
```

Imagick::paintFloodfillImage
============================

Changes the color value of any pixel that matches target

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::paintFloodfillImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$fill`</span> ,
<span class="methodparam"><span class="type">float</span> `$fuzz`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$bordercolor`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes the color value of any pixel that matches target and is an
immediate neighbor. As of ImageMagick 6.3.8 this method has been
deprecated and <span
class="function">Imagick::floodfillPaintImage</span> should be used
instead.

### Parameters

`fill`  
ImagickPixel object or a string containing the fill color

`fuzz`  
The amount of fuzz. For example, set fuzz to 10 and the color red at
intensities of 100 and 102 respectively are now interpreted as the same
color for the purposes of the floodfill.

`bordercolor`  
ImagickPixel object or a string containing the border color

`x`  
X start position of the floodfill

`y`  
Y start position of the floodfill

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

Imagick::paintOpaqueImage
=========================

Change any pixel that matches color

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::paintOpaqueImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$fill`</span>
, <span class="methodparam"><span class="type">float</span>
`$fuzz`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes any pixel that matches color with the color defined by fill.

### Parameters

`target`  
Change this target color to the fill color within the image. An
ImagickPixel object or a string representing the target color.

`fill`  
An ImagickPixel object or a string representing the fill color.

`fuzz`  
The fuzz member of image defines how much tolerance is acceptable to
consider two colors as the same.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                    |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as first and second parameter. Previous versions allow only an ImagickPixel object. |

Imagick::paintTransparentImage
==============================

Changes any pixel that matches color with the color defined by fill

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::paintTransparentImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

Changes any pixel that matches color with the color defined by fill.

### Parameters

`target`  
Change this target color to specified opacity value within the image.

`alpha`  
The level of transparency: 1.0 is fully opaque and 0.0 is fully
transparent.

`fuzz`  
The fuzz member of image defines how much tolerance is acceptable to
consider two colors as the same.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter. Previous versions allow only an ImagickPixel object. |

Imagick::pingImage
==================

Fetch basic attributes about the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::pingImage</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

This method can be used to query image width, height, size, and format
without reading the whole image in to memory.

### Parameters

`filename`  
The filename to read the information from.

### Return Values

Returns **`true`** on success.

Imagick::pingImageBlob
======================

Quickly fetch attributes

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::pingImageBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$image`</span> )

This method can be used to query image width, height, size, and format
without reading the whole image to memory. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`image`  
A string containing the image.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span
class="function">Imagick::pingImageBlob</span>**

Pinging an image from a string

``` php
<?php
/* read image contents */
$image = file_get_contents("test.jpg");

/* create new imagick object */
$im = new Imagick();

/* pass the string to the imagick object */
$im->pingImageBlob($image);

/* output image width and height */
echo $im->getImageWidth() . 'x' . $im->getImageHeight();
?>
```

### See Also

-   <span class="function">Imagick::pingImage</span>
-   <span class="function">Imagick::pingImageFile</span>
-   <span class="function">Imagick::readImage</span>
-   <span class="function">Imagick::readImageBlob</span>
-   <span class="function">Imagick::readImageFile</span>

Imagick::pingImageFile
======================

Get basic image attributes in a lightweight manner

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::pingImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$fileName`</span> \] )

This method can be used to query image width, height, size, and format
without reading the whole image to memory. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`filehandle`  
An open filehandle to the image.

`fileName`  
Optional filename for this image.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span
class="function">Imagick::pingImageFile</span>**

Opening a remote location

``` php
<?php
/* fopen a remote location */
$fp = fopen("http://example.com/test.jpg");

/* create new imagick object */
$im = new Imagick();

/* pass the handle to imagick */
$im->pingImageFile($fp);
?>
```

### See Also

-   <span class="function">Imagick::pingImage</span>
-   <span class="function">Imagick::pingImageBlob</span>
-   <span class="function">Imagick::readImage</span>
-   <span class="function">Imagick::readImageBlob</span>
-   <span class="function">Imagick::readImageFile</span>

Imagick::polaroidImage
======================

Simulates a Polaroid picture

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::polaroidImage</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$properties`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> )

Simulates a Polaroid picture. This method is available if Imagick has
been compiled against ImageMagick version 6.3.2 or newer.

### Parameters

`properties`  
The polaroid properties

`angle`  
The polaroid angle

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 A <span class="function">Imagick::polaroidImage</span>
example**

An example of using Imagick::polaroidImage()

``` php
<?php
/* Create the object */
$image = new Imagick('source.png');

/* Set the opacity */
$image->polaroidImage(new ImagickDraw(), 25);

/* output the image */
header('Content-type: image/png');
echo $image;

?>
```

Imagick::posterizeImage
=======================

Reduces the image to a limited number of color level

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::posterizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$levels`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$dither`</span> )

Reduces the image to a limited number of color level.

### Parameters

`levels`  

`dither`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::posterizeImage</span>**

``` php
<?php
function posterizeImage($imagePath, $posterizeType, $numberLevels) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->posterizeImage($numberLevels, $posterizeType);
    $imagick->setImageFormat('png');
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

posterizeImage($imagePath, \Imagick::DITHERMETHOD_RIEMERSMA, 8);

?>
```

Imagick::previewImages
======================

Quickly pin-point appropriate parameters for image processing

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::previewImages</span> ( <span
class="methodparam"><span class="type">int</span> `$preview`</span> )

Tiles 9 thumbnails of the specified image with an image processing
operation applied at varying strengths. This is helpful to quickly
pin-point an appropriate parameter for an image processing operation.

### Parameters

`preview`  
Preview type. See
<a href="/imagick/constants.html#PREVIEW%20constants" class="link">Preview type constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::previousImage
======================

Move to the previous image in the object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::previousImage</span> ( <span
class="methodparam">void</span> )

Assocates the previous image in an image list with the Imagick object.

### Return Values

Returns **`true`** on success.

Imagick::profileImage
=====================

Adds or removes a profile from an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::profileImage</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$profile`</span> )

Adds or removes a ICC, IPTC, or generic profile from an image. If the
profile is NULL, it is removed from the image otherwise added. Use a
name of '\*' and a profile of NULL to remove all profiles from the
image.

### Parameters

`name`  

`profile`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::quantizeImage
======================

Analyzes the colors within a reference image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::quantizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$numberColors`</span>
, <span class="methodparam"><span class="type">int</span>
`$colorspace`</span> , <span class="methodparam"><span
class="type">int</span> `$treedepth`</span> , <span
class="methodparam"><span class="type">bool</span> `$dither`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$measureError`</span> )

### Parameters

`numberColors`  

`colorspace`  

`treedepth`  

`dither`  

`measureError`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::quantizeImage</span>**

``` php
<?php
function quantizeImage($imagePath, $numberColors, $colorSpace, $treeDepth, $dither) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->quantizeImage($numberColors, $colorSpace, $treeDepth, $dither, false);
    $imagick->setImageFormat('png');
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::quantizeImages
=======================

Analyzes the colors within a sequence of images

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::quantizeImages</span> ( <span
class="methodparam"><span class="type">int</span> `$numberColors`</span>
, <span class="methodparam"><span class="type">int</span>
`$colorspace`</span> , <span class="methodparam"><span
class="type">int</span> `$treedepth`</span> , <span
class="methodparam"><span class="type">bool</span> `$dither`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$measureError`</span> )

### Parameters

`numberColors`  

`colorspace`  

`treedepth`  

`dither`  

`measureError`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::queryFontMetrics
=========================

Returns an array representing the font metrics

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Imagick::queryFontMetrics</span> ( <span
class="methodparam"><span class="type">ImagickDraw</span>
`$properties`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$multiline`</span>
\] )

Returns a multi-dimensional array representing the font metrics.

### Parameters

`properties`  
ImagickDraw object containing font properties

`text`  
The text

`multiline`  
Multiline parameter. If left empty it is autodetected

### Return Values

Returns a multi-dimensional array representing the font metrics.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span
class="function">Imagick::queryFontMetrics</span>:**

Query the metrics for the text and dump the results on the screen.

``` php
<?php
/* Create a new Imagick object */
$im = new Imagick();

/* Create an ImagickDraw object */
$draw = new ImagickDraw();

/* Set the font */
$draw->setFont('/path/to/font.ttf');

/* Dump the font metrics, autodetect multiline */
var_dump($im->queryFontMetrics($draw, "Hello World!"));
?>
```

Imagick::queryFonts
===================

Returns the configured fonts

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::queryFonts</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \] )

Returns the configured fonts.

### Parameters

`pattern`  
The query pattern

### Return Values

Returns an array containing the configured fonts.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::queryFonts</span>**

``` php
<?php
        $output = '';
        $output .= "Fonts that match 'Helvetica*' are:<br/>";

        $fontList = \Imagick::queryFonts("Helvetica*");
 
        foreach ($fontList as $fontName) {
            $output .= '<li>'. $fontName."</li>";
        }

        return $output;

?>
```

Imagick::queryFormats
=====================

Returns formats supported by Imagick

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">Imagick::queryFormats</span> (\[ <span
class="methodparam"><span class="type">string</span> `$pattern`<span
class="initializer"> = "\*"</span></span> \] )

Returns formats supported by Imagick.

### Parameters

`pattern`  

### Return Values

Returns an array containing the formats supported by Imagick.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::queryFormats</span>**

``` php
<?php
    function render() {
        $output = "";
        $input = \Imagick::queryformats();
        $columns = 6;

        $output .= "<table border='2'>";

        for ($i=0; $i < count($input); $i += $columns) {
            $output .= "<tr>";
            for ($c=0; $c<$columns; $c++) {
                $output .= "<td>";
                if (($i + $c) <  count($input)) {
                    $output .= $input[$i + $c];
                }
                $output .= "</td>";
            }
            $output .= "</tr>";
        }

        $output .= "</table>";

        return $output;
    }

?>
```

Imagick::radialBlurImage
========================

Radial blurs an image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::radialBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$angle`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Radial blurs an image.

### Parameters

`angle`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::radialBlurImage</span>**

``` php
<?php
function radialBlurImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    //Blur 3 times with different radii
    $imagick->radialBlurImage(3);
    $imagick->radialBlurImage(5);
    $imagick->radialBlurImage(7);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::raiseImage
===================

Creates a simulated 3d button-like effect

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::raiseImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">bool</span> `$raise`</span>
)

Creates a simulated three-dimensional button-like effect by lightening
and darkening the edges of the image. Members width and height of
raise\_info define the width of the vertical and horizontal edge of the
effect.

### Parameters

`width`  

`height`  

`x`  

`y`  

`raise`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::raiseImage</span>**

``` php
<?php
function raiseImage($imagePath, $width, $height, $x, $y, $raise) {
    $imagick = new \Imagick(realpath($imagePath));

    //x and y do nothing?
    $imagick->raiseImage($width, $height, $x, $y, $raise);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::randomThresholdImage
=============================

Creates a high-contrast, two-color image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::randomThresholdImage</span> ( <span
class="methodparam"><span class="type">float</span> `$low`</span> ,
<span class="methodparam"><span class="type">float</span> `$high`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes the value of individual pixels based on the intensity of each
pixel compared to threshold. The result is a high-contrast, two color
image. This method is available if Imagick has been compiled against
ImageMagick version 6.2.9 or newer.

### Parameters

`low`  
The low point

`high`  
The high point

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine channeltype constants using
bitwise operators. Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::randomThresholdImage</span>**

``` php
<?php
function randomThresholdimage($imagePath, $lowThreshold, $highThreshold, $channel) {
    $imagick = new \Imagick(realpath($imagePath));

    $imagick->randomThresholdimage(
        $lowThreshold * \Imagick::getQuantum(),
        $highThreshold * \Imagick::getQuantum(),
        $channel
    );
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::readImage
==================

Reads image from filename

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::readImage</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Reads image from filename

### Parameters

`filename`  

### Return Values

Returns **`true`** on success.

Imagick::readImageBlob
======================

Reads image from a binary string

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::readImageBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$image`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \] )

Reads image from a binary string

### Parameters

`image`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::readImageBlob</span>**

``` php
<?php
function readImageBlob() {
    $base64 = "iVBORw0KGgoAAAANSUhEUgAAAM0AAAD
 NCAMAAAAsYgRbAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5c
 cllPAAAABJQTFRF3NSmzMewPxIG//ncJEJsldTou1jHgAAAARBJREFUeNrs2EEK
 gCAQBVDLuv+V20dENbMY831wKz4Y/VHb/5RGQ0NDQ0NDQ0NDQ0NDQ0NDQ
 0NDQ0NDQ0NDQ0NDQ0NDQ0NDQ0PzMWtyaGhoaGhoaGhoaGhoaGhoxtb0QGho
 aGhoaGhoaGhoaGhoaMbRLEvv50VTQ9OTQ5OpyZ01GpM2g0bfmDQaL7S+ofFC6x
 v3ZpxJiywakzbvd9r3RWPS9I2+MWk0+kbf0Hih9Y17U0nTHibrDDQ0NDQ0NDQ0
 NDQ0NDQ0NTXbRSL/AK72o6GhoaGhoRlL8951vwsNDQ0NDQ1NDc0WyHtDTEhD
 Q0NDQ0NTS5MdGhoaGhoaGhoaGhoaGhoaGhoaGhoaGposzSHAAErMwwQ2HwRQ
 AAAAAElFTkSuQmCC";

    $imageBlob = base64_decode($base64);

    $imagick = new Imagick();
    $imagick->readImageBlob($imageBlob);

    header("Content-Type: image/png");
    echo $imagick;
}

?>
```

Imagick::readImageFile
======================

Reads image from open filehandle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::readImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$fileName`<span class="initializer"> =
**`null`**</span></span> \] )

Reads image from open filehandle

### Parameters

`filehandle`  

`fileName`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::readimages
===================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::readImages</span> ( <span
class="methodparam"><span class="type">array</span> `$filenames`</span>
)

Reads image from an array of filenames. All the images are held in a
single Imagick object.

### Parameters

`filenames`  

### Return Values

Returns **`true`** on success.

Imagick::recolorImage
=====================

Recolors image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::recolorImage</span> ( <span
class="methodparam"><span class="type">array</span> `$matrix`</span> )

Translate, scale, shear, or rotate image colors. This method supports
variable sized matrices but normally 5x5 matrix is used for RGBA and 6x6
is used for CMYK. The last row should contain the normalized values.
This method is available if Imagick has been compiled against
ImageMagick version 6.3.6 or newer.

### Parameters

`matrix`  
The matrix containing the color values

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::displayImage</span>

### Examples

**Example \#1 <span class="function">Imagick::recolorImage</span>**

``` php
<?php
function recolorImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $remapColor = [ 1, 0, 0,
        0, 0, 1,
        0, 1, 0,];

//$remapColor = [
//    1.438, -0.122, -0.016,  0, 0, -0.03,
//    -0.062,  1.378, -0.016,  0, 0,  0.05,
//    -0.062, -0.122, 1.483,   0, 0, -0.02,
//];

    @$imagick->recolorImage($remapColor);

    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::reduceNoiseImage
=========================

Smooths the contours of an image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::reduceNoiseImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Smooths the contours of an image while still preserving edge
information. The algorithm works by replacing each pixel with its
neighbor closest in value. A neighbor is defined by radius. Use a radius
of 0 and Imagick::reduceNoiseImage() selects a suitable radius for you.

### Parameters

`radius`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::reduceNoiseImage</span>**

``` php
<?php
function reduceNoiseImage($imagePath, $reduceNoise) {
    $imagick = new \Imagick(realpath($imagePath));
    @$imagick->reduceNoiseImage($reduceNoise);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::remapImage
===================

Remaps image colors

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::remapImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">int</span> `$DITHER`</span> )

Replaces colors an image with those defined by `replacement`. The colors
are replaced with the closest possible color. This method is available
if Imagick has been compiled against ImageMagick version 6.4.5 or newer.

### Parameters

`replacement`  
An Imagick object containing the replacement colors

`DITHER`  
Refer to this list of
<a href="/imagick/constants.html#DITHERMETHOD%20constants" class="link">dither method constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::removeImage
====================

Removes an image from the image list

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::removeImage</span> ( <span
class="methodparam">void</span> )

Removes an image from the image list.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::removeImageProfile
===========================

Removes the named image profile and returns it

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::removeImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Removes the named image profile and returns it.

### Parameters

`name`  

### Return Values

Returns a string containing the profile of the image.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::render
===============

Renders all preceding drawing commands

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::render</span> ( <span
class="methodparam">void</span> )

Renders all preceding drawing commands.

### Return Values

Returns **`true`** on success.

Imagick::resampleImage
======================

Resample image to desired resolution

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::resampleImage</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> , <span
class="methodparam"><span class="type">int</span> `$filter`</span> ,
<span class="methodparam"><span class="type">float</span> `$blur`</span>
)

Resample image to desired resolution.

### Parameters

`x_resolution`  

`y_resolution`  

`filter`  

`blur`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::resampleImage</span>**

``` php
<?php
function resampleImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));

    $imagick->resampleImage(200, 200, \Imagick::FILTER_LANCZOS, 1);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::resetImagePage
=======================

Reset image page

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::resetImagePage</span> ( <span
class="methodparam"><span class="type">string</span> `$page`</span> )

The page definition as a string. The string is in format WxH+x+y. This
method is available if Imagick has been compiled against ImageMagick
version 6.3.6 or newer.

### Parameters

`page`  
The page definition. For example *7168x5147+0+0*

### Return Values

Returns **`true`** on success.

Imagick::resizeImage
====================

Scales an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::resizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">int</span> `$filter`</span>
, <span class="methodparam"><span class="type">float</span>
`$blur`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$bestfit`<span class="initializer"> =
**`false`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \]\] )

Scales an image to the desired dimensions with a
<a href="/imagick/constants.html#FILTER%20constants" class="link">filter</a>.

> **Note**: <span class="simpara"> The behavior of the parameter
> `bestfit` changed in Imagick 3.0.0. Before this version given
> dimensions 400x400 an image of dimensions 200x150 would be left
> untouched. In Imagick 3.0.0 and later the image would be scaled up to
> size 400x300 as this is the "best fit" for the given dimensions. If
> `bestfit` parameter is used both width and height must be given.
> </span>

### Parameters

`columns`  
Width of the image

`rows`  
Height of the image

`filter`  
Refer to the list of
<a href="/imagick/constants.html#FILTER%20constants" class="link">filter constants</a>.

`blur`  
The blur factor where \> 1 is blurry, \< 1 is sharp.

`bestfit`  
Optional fit parameter.

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                                          |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Added optional fit parameter. This method now supports proportional scaling. Pass zero as either parameter for proportional scaling. |

### Examples

**Example \#1 <span class="function">Imagick::resizeImage</span>**

``` php
<?php
function resizeImage($imagePath, $width, $height, $filterType, $blur, $bestFit, $cropZoom) {
    //The blur factor where > 1 is blurry, < 1 is sharp.
    $imagick = new \Imagick(realpath($imagePath));

    $imagick->resizeImage($width, $height, $filterType, $blur, $bestFit);

    $cropWidth = $imagick->getImageWidth();
    $cropHeight = $imagick->getImageHeight();

    if ($cropZoom) {
        $newWidth = $cropWidth / 2;
        $newHeight = $cropHeight / 2;

        $imagick->cropimage(
            $newWidth,
            $newHeight,
            ($cropWidth - $newWidth) / 2,
            ($cropHeight - $newHeight) / 2
        );

        $imagick->scaleimage(
            $imagick->getImageWidth() * 4,
            $imagick->getImageHeight() * 4
        );
    }


    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::rollImage
==================

Offsets an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::rollImage</span> ( <span
class="methodparam"><span class="type">int</span> `$x`</span> , <span
class="methodparam"><span class="type">int</span> `$y`</span> )

Offsets an image as defined by x and y.

### Parameters

`x`  
The X offset.

`y`  
The Y offset.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::rollImage</span>**

``` php
<?php
function rollImage($imagePath, $rollX, $rollY) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->rollimage($rollX, $rollY);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::rotateImage
====================

Rotates an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::rotateImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
, <span class="methodparam"><span class="type">float</span>
`$degrees`</span> )

Rotates an image the specified number of degrees. Empty triangles left
over from rotating the image are filled with the background color.

### Parameters

`background`  
The background color

`degrees`  
Rotation angle, in degrees. The rotation angle is interpreted as the
number of degrees to rotate the image clockwise.

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span class="function">Imagick::rotateImage</span>**

``` php
<?php
function rotateImage($imagePath, $angle, $color) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->rotateimage($color, $angle);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::rotationalBlurImage
============================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::rotationalBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$angle`</span> \[,
<span class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Rotational blurs an image.

### Parameters

`angle`  
The angle to apply the blur over.

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::rotationalBlurImage</span>**

``` php
<?php
function rotationalBlurImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->rotationalBlurImage(3);
    $imagick->rotationalBlurImage(5);
    $imagick->rotationalBlurImage(7);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::roundCorners
=====================

Rounds image corners

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::roundCorners</span> ( <span
class="methodparam"><span class="type">float</span> `$x_rounding`</span>
, <span class="methodparam"><span class="type">float</span>
`$y_rounding`</span> \[, <span class="methodparam"><span
class="type">float</span> `$stroke_width`<span class="initializer"> =
10</span></span> \[, <span class="methodparam"><span
class="type">float</span> `$displace`<span class="initializer"> =
5</span></span> \[, <span class="methodparam"><span
class="type">float</span> `$size_correction`<span class="initializer"> =
-6</span></span> \]\]\] )

Rounds image corners. The first two parameters control the amount of
rounding and the three last parameters can be used to fine-tune the
rounding process. This method is available if Imagick has been compiled
against ImageMagick version 6.2.9 or newer.

### Parameters

`x_rounding`  
x rounding

`y_rounding`  
y rounding

`stroke_width`  
stroke width

`displace`  
image displace

`size_correction`  
size correction

### Examples

**Example \#1 Using <span
class="function">Imagick::roundCorners</span>:**

Rounds the image corners

``` php
<?php

$image = new Imagick();
$image->newPseudoImage(100, 100, "magick:rose");
$image->setImageFormat("png");

$image->roundCorners(5,3);
$image->writeImage("rounded.png");
?>
```

### Return Values

Returns **`true`** on success.

Imagick::sampleImage
====================

Scales an image with pixel sampling

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sampleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

Scales an image to the desired dimensions with pixel sampling. Unlike
other scaling methods, this method does not introduce any additional
color into the scaled image.

### Parameters

`columns`  

`rows`  

### Return Values

Returns **`true`** on success.

Imagick::scaleImage
===================

Scales the size of an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::scaleImage</span> ( <span
class="methodparam"><span class="type">int</span> `$cols`</span> , <span
class="methodparam"><span class="type">int</span> `$rows`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$bestfit`<span
class="initializer"> = **`false`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\] )

Scales the size of an image to the given dimensions. The other parameter
will be calculated if 0 is passed as either param.

> **Note**: <span class="simpara"> The behavior of the parameter
> `bestfit` changed in Imagick 3.0.0. Before this version given
> dimensions 400x400 an image of dimensions 200x150 would be left
> untouched. In Imagick 3.0.0 and later the image would be scaled up to
> size 400x300 as this is the "best fit" for the given dimensions. If
> `bestfit` parameter is used both width and height must be given.
> </span>

### Parameters

`cols`  

`rows`  

`bestfit`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                          |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Added optional fit parameter. This method now supports proportional scaling. Pass zero as either parameter for proportional scaling. |

### Examples

**Example \#1 <span class="function">Imagick::scaleImage</span>**

``` php
<?php
function scaleImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->scaleImage(150, 150, true);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::segmentImage
=====================

Segments an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::segmentImage</span> ( <span
class="methodparam"><span class="type">int</span> `$COLORSPACE`</span> ,
<span class="methodparam"><span class="type">float</span>
`$cluster_threshold`</span> , <span class="methodparam"><span
class="type">float</span> `$smooth_threshold`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$verbose`<span
class="initializer"> = **`false`**</span></span> \] )

Analyses the image and identifies units that are similar. This method is
available if Imagick has been compiled against ImageMagick version 6.4.5
or newer.

### Parameters

`COLORSPACE`  
One of the
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>.

`cluster_threshold`  
A percentage describing minimum number of pixels contained in hexedra
before it is considered valid.

`smooth_threshold`  
Eliminates noise from the histogram.

`verbose`  
Whether to output detailed information about recognised classes.

### Return Values

### Examples

**Example \#1 <span class="function">Imagick::segmentImage</span>**

``` php
<?php
function segmentImage($imagePath, $colorSpace, $clusterThreshold, $smoothThreshold) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->segmentImage($colorSpace, $clusterThreshold, $smoothThreshold);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

segmentImage($imagePath, \Imagick::COLORSPACE_RGB, 5, 5);

?>
```

Imagick::selectiveBlurImage
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::selectiveBlurImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$threshold`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Selectively blur an image within a contrast threshold. It is similar to
the unsharpen mask that sharpens everything with contrast above a
certain threshold.

### Parameters

`radius`  

`sigma`  

`threshold`  

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::selectiveBlurImage</span>**

``` php
<?php
function selectiveBlurImage($imagePath, $radius, $sigma, $threshold, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->selectiveBlurImage($radius, $sigma, $threshold, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::separateImageChannel
=============================

Separates a channel from the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::separateImageChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Separates a channel from the image and returns a grayscale image. A
channel is a particular color component of each pixel in the image.

### Parameters

`channel`  
Which 'channel' to return. For colorspaces other than RGB, you can still
use the CHANNEL\_RED, CHANNEL\_GREEN, CHANNEL\_BLUE constants to
indicate the 1st, 2nd and 3rd channels.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span
class="function">Imagick::separateImageChannel</span>**

``` php
<?php
function separateImageChannel($imagePath, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->separateimagechannel($channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

separateImageChannel($imagePath, \Imagick::CHANNEL_GREEN);

?>
```

Imagick::sepiaToneImage
=======================

Sepia tones an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sepiaToneImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
)

Applies a special effect to the image, similar to the effect achieved in
a photo darkroom by sepia toning. Threshold ranges from 0 to
QuantumRange and is a measure of the extent of the sepia toning. A
threshold of 80 is a good starting point for a reasonable tone.

### Parameters

`threshold`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::sepiaToneImage</span>**

``` php
<?php
function sepiaToneImage($imagePath, $sepia) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->sepiaToneImage($sepia);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setBackgroundColor
===========================

Sets the object's default background color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setBackgroundColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
)

Sets the object's default background color.

### Parameters

`background`  

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                     |
|--------------------|-----------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as a parameter. Previous versions allow only an ImagickPixel object. |

Imagick::setColorspace
======================

Set colorspace

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setColorspace</span> ( <span
class="methodparam"><span class="type">int</span> `$COLORSPACE`</span> )

Sets the global colorspace value for the object. This method is
available if Imagick has been compiled against ImageMagick version 6.5.7
or newer.

### Parameters

`COLORSPACE`  
One of the
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setCompression
=======================

Sets the object's default compression type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setCompression</span> ( <span
class="methodparam"><span class="type">int</span> `$compression`</span>
)

Sets the object's default compression type

### Parameters

`compression`  
The compression type. See the
<a href="/imagick/constants.html" class="link">Imagick::COMPRESSION_*</a>
constants.

### Return Values

Returns **`true`** on success.

Imagick::setCompressionQuality
==============================

Sets the object's default compression quality

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setCompressionQuality</span> ( <span
class="methodparam"><span class="type">int</span> `$quality`</span> )

Sets the object's default compression quality.

**Caution**

This method only works for new images e.g. those created through
Imagick::newPseudoImage. For existing images you should use <span
class="methodname">Imagick::setImageCompressionQuality</span>.

### Parameters

`quality`  
An <span class="type">int</span> between 1 and 100, 1 = high
compression, 100 low compression.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::setCompressionQuality</span>**

``` php
<?php
function setCompressionQuality($imagePath, $quality) {

    $backgroundImagick = new \Imagick(realpath($imagePath));
    $imagick = new \Imagick();
    $imagick->setCompressionQuality($quality);
    $imagick->newPseudoImage(
        $backgroundImagick->getImageWidth(),
        $backgroundImagick->getImageHeight(),
        'canvas:white'
    );

    $imagick->compositeImage(
        $backgroundImagick,
        \Imagick::COMPOSITE_ATOP,
        0,
        0
    );
    
    $imagick->setFormat("jpg");    
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setFilename
====================

Sets the filename before you read or write the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setFilename</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Sets the filename before you read or write an image file.

### Parameters

`filename`  

### Return Values

Returns **`true`** on success.

Imagick::setFirstIterator
=========================

Sets the Imagick iterator to the first image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setFirstIterator</span> ( <span
class="methodparam">void</span> )

Sets the Imagick iterator to the first image.

### Return Values

Returns **`true`** on success.

Imagick::setFont
================

Sets font

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setFont</span> ( <span
class="methodparam"><span class="type">string</span> `$font`</span> )

Sets object's font property. This method can be used for example to set
font for caption: pseudo-format. The font needs to be configured in
ImageMagick configuration or a file by the name of `font` must exist.
This method should not be confused with <span
class="function">ImagickDraw::setFont</span> which sets the font for a
specific ImagickDraw object. This method is available if Imagick has
been compiled against ImageMagick version 6.3.7 or newer.

### Parameters

`font`  
Font name or a filename

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::getFont</span>
-   <span class="function">ImagickDraw::setFont</span>
-   <span class="function">ImagickDraw::getFont</span>

### Examples

**Example \#1 A <span class="function">Imagick::setFont</span> example**

Example of using Imagick::setFont

``` php
<?php
/* Create new imagick object */
$im = new Imagick();

/* Set the font for the object */
$im->setFont("example.ttf");

/* Create new caption */
$im->newPseudoImage(100, 100, "caption:Hello");

/* Do something with the image */
?>
```

Imagick::setFormat
==================

Sets the format of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Sets the format of the Imagick object.

### Parameters

`format`  

### Return Values

Returns **`true`** on success.

Imagick::setGravity
===================

Sets the gravity

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

Sets the global gravity property for the Imagick object. This method is
available if Imagick has been compiled against ImageMagick version 6.4.0
or newer.

### Parameters

`gravity`  
The gravity property. Refer to the list of
<a href="/imagick/constants.html#GRAVITY%20constants" class="link">gravity constants</a>.

### Return Values

No value is returned.

Imagick::setImage
=================

Replaces image in the object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImage</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$replace`</span>
)

Replaces the current image sequence with the image from replace object.

### Parameters

`replace`  
The replace Imagick object

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 A <span class="function">Imagick::setImage</span>
example**

An example of using Imagick::setImage()

``` php
<?php
/* Create the objects */
$image = new Imagick('source.jpg');
$replace = new Imagick('replace.jpg');

/* source.jpg is replaced with replace.jpg */
$image->setImage($replace);

/* output the image */
header('Content-type: image/jpeg');
echo $image;

?>
```

Imagick::setImageAlphaChannel
=============================

Sets image alpha channel

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageAlphaChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Activate or deactivate image alpha channel. The `mode` is one of the
**`Imagick::ALPHACHANNEL_*`** constants. This method is available if
Imagick has been compiled against ImageMagick version 6.3.8 or newer.

### Parameters

`mode`  
One of the **`Imagick::ALPHACHANNEL_*`** constants

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::setImageMatte</span>
-   <a href="/imagick/constants.html#ALPHACHANNEL%20constants" class="link">Imagick Alpha Channel Constants</a>

Imagick::setImageArtifact
=========================

Set image artifact

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageArtifact</span> ( <span
class="methodparam"><span class="type">string</span> `$artifact`</span>
, <span class="methodparam"><span class="type">string</span>
`$value`</span> )

Associates an artifact with the image. The difference between image
properties and image artifacts is that properties are public and
artifacts are private. This method is available if Imagick has been
compiled against ImageMagick version 6.5.7 or newer.

### Parameters

`artifact`  
The name of the artifact

`value`  
The value of the artifact

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::getImageArtifact</span>
-   <span class="function">Imagick::deleteImageArtifact</span>

### Examples

**Example \#1 <span class="function">Imagick::setImageArtifact</span>**

``` php
<?php
function setImageArtifact() {

    $src1 = new \Imagick(realpath("./images/artifact/source1.png"));
    $src2 = new \Imagick(realpath("./images/artifact/source2.png"));

    $src2->setImageVirtualPixelMethod(\Imagick::VIRTUALPIXELMETHOD_TRANSPARENT);
    $src2->setImageArtifact('compose:args', "1,0,-0.5,0.5");
    $src1->compositeImage($src2, Imagick::COMPOSITE_MATHEMATICS, 0, 0);
    
    $src1->setImageFormat('png');
    header("Content-Type: image/png");
    echo $src1->getImagesBlob();
}

?>
```

Imagick::setImageAttribute
==========================

Description

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageAttribute</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`key`  

`value`  

### Return Values

Returns **`true`** on success.

Imagick::setImageBackgroundColor
================================

Sets the image background color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageBackgroundColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
)

Sets the image background color.

### Parameters

`background`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                       |
|--------------------|-------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the parameter. Previous versions allow only an ImagickPixel object. |

Imagick::setImageBias
=====================

Sets the image bias for any method that convolves an image

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageBias</span> ( <span
class="methodparam"><span class="type">float</span> `$bias`</span> )

Sets the image bias for any method that convolves an image (e.g.
Imagick::ConvolveImage()).

### Parameters

`bias`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::setImageBias</span>**

``` php
<?php
//requires ImageMagick version 6.9.0-1 to have an effect on convolveImage
function setImageBias($bias) {
    $imagick = new \Imagick(realpath("images/stack.jpg"));

    $xKernel = array(
        -0.70, 0, 0.70,
        -0.70, 0, 0.70,
        -0.70, 0, 0.70
    );

    $imagick->setImageBias($bias * \Imagick::getQuantum());
    $imagick->convolveImage($xKernel, \Imagick::CHANNEL_ALL);

    $imagick->setImageFormat('png');
    
    header('Content-type: image/png');
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setImageBiasQuantum
============================

Description

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Imagick::setImageBiasQuantum</span> ( <span
class="methodparam"><span class="type">string</span> `$bias`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`bias`  

### Return Values

Imagick::setImageBluePrimary
============================

Sets the image chromaticity blue primary point

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageBluePrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

Sets the image chromaticity blue primary point.

### Parameters

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageBorderColor
============================

Sets the image border color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageBorderColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$border`</span> )

Sets the image border color.

### Parameters

`border`  
The border color

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                     |
|--------------------|-----------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as a parameter. Previous versions allow only an ImagickPixel object. |

Imagick::setImageChannelDepth
=============================

Sets the depth of a particular image channel

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageChannelDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> ,
<span class="methodparam"><span class="type">int</span> `$depth`</span>
)

Sets the depth of a particular image channel.

### Parameters

`channel`  

`depth`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageClipMask
=========================

Sets image clip mask

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageClipMask</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$clip_mask`</span> )

Sets image clip mask from another Imagick object. This method is
available if Imagick has been compiled against ImageMagick version 6.3.6
or newer.

### Parameters

`clip_mask`  
The Imagick object containing the clip mask

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::setImageClipMask</span>**

``` php
<?php
function setImageClipMask($imagePath) {
    $imagick = new \Imagick();
    $imagick->readImage(realpath($imagePath));

    $width = $imagick->getImageWidth();
    $height = $imagick->getImageHeight();

    $clipMask = new \Imagick();
    $clipMask->newPseudoImage(
        $width,
        $height,
        "canvas:transparent"
    );

    $draw = new \ImagickDraw();
    $draw->setFillColor('white');
    $draw->circle(
        $width / 2,
        $height / 2,
        ($width / 2) + ($width / 4),
        $height / 2
    );
    $clipMask->drawImage($draw);
    $imagick->setImageClipMask($clipMask);

    $imagick->negateImage(false);
    $imagick->setFormat("png");

    header("Content-Type: image/png");
    echo $imagick->getImagesBlob();
    
}

?>
```

Imagick::setImageColormapColor
==============================

Sets the color of the specified colormap index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageColormapColor</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> )

Sets the color of the specified colormap index.

### Parameters

`index`  

`color`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageColorspace
===========================

Sets the image colorspace

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageColorspace</span> ( <span
class="methodparam"><span class="type">int</span> `$colorspace`</span> )

Sets the image colorspace. This method should be used when creating new
images. To change the colorspace of an existing image, you should use
<span class="methodname">Imagick::transformImageColorspace</span>.

### Parameters

`colorspace`  
One of the
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageCompose
========================

Sets the image composite operator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageCompose</span> ( <span
class="methodparam"><span class="type">int</span> `$compose`</span> )

Sets the image composite operator, useful for specifying how to
composite the image thumbnail when using the Imagick::montageImage()
method.

### Parameters

`compose`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageCompression
============================

Sets the image compression

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageCompression</span> ( <span
class="methodparam"><span class="type">int</span> `$compression`</span>
)

### Parameters

`compression`  
One of the **`COMPRESSION`** constants

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageCompressionQuality
===================================

Sets the image compression quality

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageCompressionQuality</span> (
<span class="methodparam"><span class="type">int</span>
`$quality`</span> )

Sets the image compression quality.

### Parameters

`quality`  
The image compression quality as an integer

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span
class="function">Imagick::setImageCompressionQuality</span>**

``` php
<?php
function setImageCompressionQuality($imagePath, $quality) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setImageCompressionQuality($quality);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setImageDelay
======================

Sets the image delay

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageDelay</span> ( <span
class="methodparam"><span class="type">int</span> `$delay`</span> )

Sets the image delay. For an animated image this is the amount of time
that this frame of the image should be displayed for, before displaying
the next frame.

The delay can be set individually for each frame in an image.

### Parameters

`delay`  
The amount of time expressed in 'ticks' that the image should be
displayed for. For animated GIFs there are 100 ticks per second, so a
value of 20 would be 20/100 of a second aka 1/5th of a second.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Modify animated Gif with <span
class="function">Imagick::setImageDelay</span>**

``` php
<?php

// Modify an animated Gif so that it's frames are played at a variable speed,
// varying between being shown for 50ms down to 0ms, which will cause the frame
// to be skipped in most browsers.
$imagick = new Imagick(realpath("Test.gif"));
$imagick = $imagick->coalesceImages();

$frameCount = 0;

foreach ($imagick as $frame) {
    $imagick->setImageDelay((($frameCount % 11) * 5));
    $frameCount++;
}

$imagick = $imagick->deconstructImages();

$imagick->writeImages("/path/to/save/output.gif", true);

?>
```

Imagick::setImageDepth
======================

Sets the image depth

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageDepth</span> ( <span
class="methodparam"><span class="type">int</span> `$depth`</span> )

Sets the image depth.

### Parameters

`depth`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageDispose
========================

Sets the image disposal method

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageDispose</span> ( <span
class="methodparam"><span class="type">int</span> `$dispose`</span> )

Sets the image disposal method.

### Parameters

`dispose`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageExtent
=======================

Sets the image size

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageExtent</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

Sets the image size (i.e. columns & rows).

### Parameters

`columns`  

`rows`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageFilename
=========================

Sets the filename of a particular image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageFilename</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Sets the filename of a particular image in a sequence.

### Parameters

`filename`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageFormat
=======================

Sets the format of a particular image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Sets the format of a particular image in a sequence.

### Parameters

`format`  
String presentation of the image format. Format support depends on the
ImageMagick installation.

### Return Values

Returns **`true`** on success.

Imagick::setImageGamma
======================

Sets the image gamma

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageGamma</span> ( <span
class="methodparam"><span class="type">float</span> `$gamma`</span> )

Sets the image gamma.

### Parameters

`gamma`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageGravity
========================

Sets the image gravity

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

Sets the gravity property for the current image. This method can be used
to set the gravity property for a single image sequence. This method is
available if Imagick has been compiled against ImageMagick version 6.4.4
or newer.

### Parameters

`gravity`  
The gravity property. Refer to the list of
<a href="/imagick/constants.html#GRAVITY%20constants" class="link">gravity constants</a>.

### Return Values

No value is returned.

Imagick::setImageGreenPrimary
=============================

Sets the image chromaticity green primary point

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageGreenPrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

Sets the image chromaticity green primary point.

### Parameters

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageIndex
======================

Set the iterator position

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Set the iterator to the position in the image list specified with the
index parameter.

This method has been deprecated. See <span
class="function">Imagick::setIteratorIndex</span>.

### Parameters

`index`  
The position to set the iterator to

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageInterlaceScheme
================================

Sets the image compression

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageInterlaceScheme</span> ( <span
class="methodparam"><span class="type">int</span>
`$interlace_scheme`</span> )

Sets the image compression.

### Parameters

`interlace_scheme`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageInterpolateMethod
==================================

Sets the image interpolate pixel method

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageInterpolateMethod</span> (
<span class="methodparam"><span class="type">int</span> `$method`</span>
)

Sets the image interpolate pixel method.

### Parameters

`method`  
The method is one of the **`Imagick::INTERPOLATE_*`** constants

### Return Values

Returns **`true`** on success.

Imagick::setImageIterations
===========================

Sets the image iterations

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageIterations</span> ( <span
class="methodparam"><span class="type">int</span> `$iterations`</span> )

Sets the number of iterations an animated image is repeated.

### Parameters

`iterations`  
The number of iterations the image should loop over. Set to '0' to loop
continuously.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Basic <span
class="function">Imagick::setImageIterations</span> usage**

``` php
<?php

$imagick = new Imagick(realpath("Test.gif"));

$imagick = $imagick->coalesceImages();
$imagick->setImageIterations(1);
$imagick = $imagick->deconstructImages();

$imagick->writeImages('/path/to/save/OnceOnly.gif', true);

?>
```

Imagick::setImageMatte
======================

Sets the image matte channel

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageMatte</span> ( <span
class="methodparam"><span class="type">bool</span> `$matte`</span> )

Sets the image matte channel. This method is available if Imagick has
been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`matte`  
True activates the matte channel and false disables it.

### Return Values

Returns **`true`** on success.

Imagick::setImageMatteColor
===========================

Sets the image matte color

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageMatteColor</span> ( <span
class="methodparam"><span class="type">mixed</span> `$matte`</span> )

Sets the image matte color.

### Parameters

`matte`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                       |
|--------------------|-------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the parameter. Previous versions allow only an ImagickPixel object. |

Imagick::setImageOpacity
========================

Sets the image opacity level

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageOpacity</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

Sets the image to the specified opacity level. This method is available
if Imagick has been compiled against ImageMagick version 6.3.1 or newer.
This method operates on all channels, which means that for example
opacity value of 0.5 will set all transparent areas to partially opaque.
To add transparency to areas that are not already transparent use
<a href="/class/imagick.html#Imagick::evaluateImage" class="link">Imagick::evaluateImage()</a>

### Parameters

`opacity`  
The level of transparency: 1.0 is fully opaque and 0.0 is fully
transparent.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 A <span class="function">Imagick::setImageOpacity</span>
example**

An example of using Imagick::setImageOpacity()

``` php
<?php
/* Create the object */
$image = new Imagick('source.png');

/* Set the opacity */
$image->setImageOpacity(0.7);

/* output the image */
header('Content-type: image/png');
echo $image;

?>
```

Imagick::setImageOrientation
============================

Sets the image orientation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageOrientation</span> ( <span
class="methodparam"><span class="type">int</span> `$orientation`</span>
)

Sets the image orientation.

### Parameters

`orientation`  
One of the
<a href="/imagick/constants.html#ORIENTATION%20constants" class="link">orientation constants</a>

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::setImageOrientation</span>**

``` php
<?php
//Doesn't appear to do anything
function setImageOrientation($imagePath, $orientationType) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setImageOrientation($orientationType);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setImagePage
=====================

Sets the page geometry of the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImagePage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Sets the page geometry of the image.

### Parameters

`width`  

`height`  

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageProfile
========================

Adds a named profile to the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageProfile</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$profile`</span> )

Adds a named profile to the Imagick object. If a profile with the same
name already exists, it is replaced. This method differs from the
Imagick::ProfileImage() method in that it does not apply any CMS color
profiles.

### Parameters

`name`  

`profile`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageProperty
=========================

Sets an image property

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageProperty</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Sets a named property to the image. This method is available if Imagick
has been compiled against ImageMagick version 6.3.2 or newer.

### Parameters

`name`  

`value`  

### Examples

**Example \#1 Using <span
class="function">Imagick::setImageProperty</span>:**

Setting and getting image properties

``` php
<?php
$image = new Imagick();
$image->newImage(300, 200, "black");

$image->setImageProperty('Exif:Make', 'Imagick');
echo $image->getImageProperty('Exif:Make');
?>
```

### See Also

-   <span class="function">Imagick::getImageProperty</span>

### Return Values

Returns **`true`** on success.

Imagick::setImageRedPrimary
===========================

Sets the image chromaticity red primary point

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageRedPrimary</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

Sets the image chromaticity red primary point.

### Parameters

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageRenderingIntent
================================

Sets the image rendering intent

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageRenderingIntent</span> ( <span
class="methodparam"><span class="type">int</span>
`$rendering_intent`</span> )

Sets the image rendering intent.

### Parameters

`rendering_intent`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageResolution
===========================

Sets the image resolution

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

Sets the image resolution.

### Parameters

`x_resolution`  

`y_resolution`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span
class="function">Imagick::setImageResolution</span>**

``` php
<?php
function setImageResolution($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setImageResolution(50, 50);
    
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::setImageScene
======================

Sets the image scene

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageScene</span> ( <span
class="methodparam"><span class="type">int</span> `$scene`</span> )

Sets the image scene.

### Parameters

`scene`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setImageTicksPerSecond
===============================

Sets the image ticks-per-second

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageTicksPerSecond</span> ( <span
class="methodparam"><span class="type">int</span>
`$ticks_per_second`</span> )

Adjust the amount of time that a frame of an animated image is displayed
for.

> **Note**:
>
> For animated GIFs, this function does not change the number of 'image
> ticks' per second, which is always defined as 100. Instead it adjusts
> the amount of time that the frame is displayed for to simulate the
> change in 'ticks per second'.
>
> For example, for an animated GIF where each frame is displayed for 20
> ticks (1/5 of a second) when this method is called on each frame of
> that image with an argument of *50* the frames are adjusted to be
> displayed for 40 ticks (2/5 of a second) and the animation will play
> at half the original speed.

### Parameters

`ticks_per_second`  
The duration for which an image should be displayed expressed in ticks
per second.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Modify animated Gif with <span
class="function">Imagick::setImageTicksPerSecond</span>**

``` php
<?php

// Modify an animated gif so the first half of the gif is played at half the
// speed it currently is, and the second half to be played at double the speed
// it currently is

$imagick = new Imagick(realpath("Test.gif"));
$imagick = $imagick->coalesceImages();

$totalFrames = $imagick->getNumberImages();

$frameCount = 0;

foreach ($imagick as $frame) {
    $imagick->setImageTicksPerSecond(50);
    
    if ($frameCount < ($totalFrames / 2)) {
        // Modify the frame to be displayed for twice as long as it currently is
        $imagick->setImageTicksPerSecond(50);
    } else {
        // Modify the frame to be displayed for half as long as it currently is
        $imagick->setImageTicksPerSecond(200);
    }

    $frameCount++;
}

$imagick = $imagick->deconstructImages();

$imagick->writeImages("/path/to/save/output.gif", true);

?>
```

Imagick::setImageType
=====================

Sets the image type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageType</span> ( <span
class="methodparam"><span class="type">int</span> `$image_type`</span> )

Sets the image type.

### Parameters

`image_type`  

### Return Values

Returns **`true`** on success.

Imagick::setImageUnits
======================

Sets the image units of resolution

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageUnits</span> ( <span
class="methodparam"><span class="type">int</span> `$units`</span> )

Sets the image units of resolution.

### Parameters

`units`  

### Return Values

Returns **`true`** on success.

Imagick::setImageVirtualPixelMethod
===================================

Sets the image virtual pixel method

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageVirtualPixelMethod</span> (
<span class="methodparam"><span class="type">int</span> `$method`</span>
)

Sets the image virtual pixel method.

### Parameters

`method`  

### Return Values

Returns **`true`** on success.

Imagick::setImageWhitePoint
===========================

Sets the image chromaticity white point

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setImageWhitePoint</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

Sets the image chromaticity white point.

### Parameters

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::setInterlaceScheme
===========================

Sets the image compression

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setInterlaceScheme</span> ( <span
class="methodparam"><span class="type">int</span>
`$interlace_scheme`</span> )

Sets the image compression.

### Parameters

`interlace_scheme`  

### Return Values

Returns **`true`** on success.

Imagick::setIteratorIndex
=========================

Set the iterator position

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setIteratorIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Set the iterator to the position in the image list specified with the
index parameter. This method is available if Imagick has been compiled
against ImageMagick version 6.2.9 or newer.

### Parameters

`index`  
The position to set the iterator to

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Using <span
class="function">Imagick::setIteratorIndex</span>:**

Create images, set and get the iterator index

``` php
<?php
$im = new Imagick();
$im->newImage(100, 100, new ImagickPixel("red"));
$im->newImage(100, 100, new ImagickPixel("green"));
$im->newImage(100, 100, new ImagickPixel("blue"));

$im->setIteratorIndex(1);
echo $im->getIteratorIndex();
?>
```

### See Also

-   <span class="function">Imagick::getIteratorIndex</span>
-   <span class="function">Imagick::getImageIndex</span>
-   <span class="function">Imagick::setImageIndex</span>

Imagick::setLastIterator
========================

Sets the Imagick iterator to the last image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setLastIterator</span> ( <span
class="methodparam">void</span> )

Sets the Imagick iterator to the last image.

### Return Values

Returns **`true`** on success.

Imagick::setOption
==================

Set an option

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setOption</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Associates one or more options with the wand.

### Parameters

`key`  

`value`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Attempt to reach '$extent' size<span
class="function">Imagick::setOption</span>**

``` php
<?php
    function renderJPG($extent) {
        $imagePath = $this->control->getImagePath();
        $imagick = new \Imagick(realpath($imagePath));
        $imagick->setImageFormat('jpg');
        $imagick->setOption('jpeg:extent', $extent);
        header("Content-Type: image/jpg");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#2 <span class="function">Imagick::setOption</span>**

``` php
<?php
    function renderPNG($imagePath, $format) {

        $imagick = new \Imagick(realpath($imagePath));
        $imagick->setImageFormat('png');
        $imagick->setOption('png:format', $format);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }
    
    //Save as 64bit PNG.
    renderPNG($imagePath, 'png64');

?>
```

**Example \#3 <span class="function">Imagick::setOption</span>**

``` php
<?php
    function renderCustomBitDepthPNG() {
        $imagePath = $this->control->getImagePath();
        $imagick = new \Imagick(realpath($imagePath));
        $imagick->setImageFormat('png');
        
        $imagick->setOption('png:bit-depth', '16');
        $imagick->setOption('png:color-type', 6);
        header("Content-Type: image/png");
        $crash = true;
        if ($crash) {
            echo $imagick->getImageBlob();
        }
        else {
            $tempFilename = tempnam('./', 'imagick');
            $imagick->writeimage(realpath($tempFilename));
            echo file_get_contents($tempFilename);
        }
    }

?>
```

Imagick::setPage
================

Sets the page geometry of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setPage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Sets the page geometry of the Imagick object.

### Parameters

`width`  

`height`  

`x`  

`y`  

### Return Values

Returns **`true`** on success.

Imagick::setPointSize
=====================

Sets point size

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setPointSize</span> ( <span
class="methodparam"><span class="type">float</span> `$point_size`</span>
)

Sets object's point size property. This method can be used for example
to set font size for caption: pseudo-format. This method is available if
Imagick has been compiled against ImageMagick version 6.3.7 or newer.

### Parameters

`point_size`  
Point size

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::getPointSize</span>

### Examples

**Example \#1 A <span class="function">Imagick::setPointSize</span>
example**

Example of using Imagick::setPointSize

``` php
<?php
/* Create new imagick object */
$im = new Imagick();

/* Set the font for the object */
$im->setFont("example.ttf");

/* Set the point size */
$im->setPointSize(12);

/* Create new caption */
$im->newPseudoImage(100, 100, "caption:Hello");

/* Do something with the image */
?>
```

Imagick::setProgressMonitor
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setProgressMonitor</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Set a callback that will be called during the processing of the Imagick
image.

### Parameters

`callback`  
The progress function to call. It should return true if image processing
should continue, or false if it should be cancelled. The offset
parameter indicates the progress and the span parameter indicates the
total amount of work needed to be done.

<span class="type">bool</span> <span class="methodname"> <span
class="replaceable">callback</span> </span> ( <span class="methodparam">
<span class="type">mixed</span> `$offset` </span> , <span
class="methodparam"> <span class="type">mixed</span> `$span` </span> )

**Caution**
The values passed to the callback function are not consistent. In
particular the span parameter can increase during image processing.
Because of this calculating the percentage complete of an image
operation is not trivial.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::setProgressMonitor</span>**

``` php
<?php
        $abortReason = null;
        
        try {
            $imagick = new \Imagick(realpath($this->control->getImagePath()));
            $startTime = time();

            $callback = function ($offset, $span)  use ($startTime, &$abortReason) {
                if (((100 * $offset) / $span)  > 20) {
                    $abortReason = "Processing reached 20%";
                    return false;
                }

                $nowTime = time();

                if ($nowTime - $startTime > 5) {
                    $abortReason = "Image processing took more than 5 seconds";
                    return false;
                }
                if (($offset % 5) == 0) {
                    echo "Progress: $offset / $span <br/>";
                }
                return true;
            };

            $imagick->setProgressMonitor($callback);

            $imagick->waveImage(2, 15);

            echo "Data len is: ".strlen($imagick->getImageBlob());
        }
        catch(\ImagickException $e) {
            if ($abortReason != null) {
                echo "Image processing was aborted: ".$abortReason."<br/>";
            }
            else {
                echo "ImagickException caught: ".$e->getMessage()." Exception type is ".get_class($e);
            }
        }

?>
```

Imagick::setRegistry
====================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Imagick::setRegistry</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

Sets the ImageMagick registry entry named key to value. This is most
useful for setting "temporary-path" which controls where ImageMagick
creates temporary images e.g. while processing PDFs.

### Parameters

`key`  

`value`  

### Return Values

Returns **`true`** on success.

Imagick::setResolution
======================

Sets the image resolution

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

Sets the image resolution.

### Parameters

`x_resolution`  
The horizontal resolution.

`y_resolution`  
The vertical resolution.

### Return Values

Returns **`true`** on success.

### Notes

<span class="methodname">Imagick::setResolution</span> must be called
before loading or creating an image.

### See Also

-   <span class="methodname">Imagick::setImageResolution</span>
-   <span class="methodname">Imagick::getImageResolution</span>

Imagick::setResourceLimit
=========================

Sets the limit for a particular resource

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Imagick::setResourceLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">int</span> `$limit`</span> )

This method is used to modify the resource limits of the underlying
ImageMagick library.

### Parameters

`type`  
Refer to the list of
<a href="/imagick/constants.html#RESOURCETYPE%20constants" class="link">resourcetype constants</a>.

`limit`  
One of the
<a href="/imagick/constants.html#RESOURCETYPE%20constants" class="link">resourcetype constants</a>.
The unit depends on the type of the resource being limited.

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="methodname">Imagick::getResourceLimit</span>

Imagick::setSamplingFactors
===========================

Sets the image sampling factors

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setSamplingFactors</span> ( <span
class="methodparam"><span class="type">array</span> `$factors`</span> )

Sets the image sampling factors.

### Parameters

`factors`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::setSamplingFactors</span>**

``` php
<?php
function setSamplingFactors($imagePath) {

    $imagePath = "../imagick/images/FineDetail.png";
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setImageFormat('jpg');
    $imagick->setSamplingFactors(array('2x2', '1x1', '1x1'));

    $compressed = $imagick->getImageBlob();

    
    $reopen = new \Imagick();
    $reopen->readImageBlob($compressed);

    $reopen->resizeImage(
        $reopen->getImageWidth() * 4,
        $reopen->getImageHeight() * 4,
        \Imagick::FILTER_POINT,
        1
    );
    
    header("Content-Type: image/jpg");
    echo $reopen->getImageBlob();
}

?>
```

Imagick::setSize
================

Sets the size of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

Sets the size of the Imagick object. Set it before you read a raw image
format such as RGB, GRAY, or CMYK.

### Parameters

`columns`  

`rows`  

### Return Values

Returns **`true`** on success.

Imagick::setSizeOffset
======================

Sets the size and offset of the Imagick object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setSizeOffset</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
)

Sets the size and offset of the Imagick object. Set it before you read a
raw image format such as RGB, GRAY, or CMYK. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`columns`  
The width in pixels.

`rows`  
The height in pixels.

`offset`  
The image offset.

### Return Values

Returns **`true`** on success.

Imagick::setType
================

Sets the image type attribute

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::setType</span> ( <span
class="methodparam"><span class="type">int</span> `$image_type`</span> )

Sets the image type attribute.

### Parameters

`image_type`  

### Return Values

Returns **`true`** on success.

Imagick::shadeImage
===================

Creates a 3D effect

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::shadeImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$gray`</span> ,
<span class="methodparam"><span class="type">float</span>
`$azimuth`</span> , <span class="methodparam"><span
class="type">float</span> `$elevation`</span> )

Shines a distant light on an image to create a three-dimensional effect.
You control the positioning of the light with azimuth and elevation;
azimuth is measured in degrees off the x axis and elevation is measured
in pixels above the Z axis. This method is available if Imagick has been
compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`gray`  
A value other than zero shades the intensity of each pixel.

`azimuth`  
Defines the light source direction.

`elevation`  
Defines the light source direction.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on failure.

### Examples

**Example \#1 <span class="function">Imagick::shadeImage</span>**

``` php
<?php
function shadeImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->shadeImage(true, 45, 20);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::shadowImage
====================

Simulates an image shadow

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::shadowImage</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

Simulates an image shadow.

### Parameters

`opacity`  

`sigma`  

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::shadowImage</span>**

``` php
<?php
function shadowImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->shadowImage(0.4, 10, 50, 5);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::sharpenImage
=====================

Sharpens an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sharpenImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> \[, <span class="methodparam"><span
class="type">int</span> `$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Sharpens an image. We convolve the image with a Gaussian operator of the
given radius and standard deviation (sigma). For reasonable results, the
radius should be larger than sigma. Use a radius of 0 and <span
class="function">Imagick::sharpenImage</span> selects a suitable radius
for you.

### Parameters

`radius`  

`sigma`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::sharpenImage</span>**

``` php
<?php
function sharpenImage($imagePath, $radius, $sigma, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->sharpenimage($radius, $sigma, $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::shaveImage
===================

Shaves pixels from the image edges

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::shaveImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span> )

Shaves pixels from the image edges. It allocates the memory necessary
for the new Image structure and returns a pointer to the new image.

### Parameters

`columns`  

`rows`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::shaveImage</span>**

``` php
<?php
function shaveImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->shaveImage(100, 50);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::shearImage
===================

Creating a parallelogram

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::shearImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$background`</span>
, <span class="methodparam"><span class="type">float</span>
`$x_shear`</span> , <span class="methodparam"><span
class="type">float</span> `$y_shear`</span> )

Slides one edge of an image along the X or Y axis, creating a
parallelogram. An X direction shear slides an edge along the X axis,
while a Y direction shear slides an edge along the Y axis. The amount of
the shear is controlled by a shear angle. For X direction shears,
x\_shear is measured relative to the Y axis, and similarly, for Y
direction shears y\_shear is measured relative to the X axis. Empty
triangles left over from shearing the image are filled with the
background color.

### Parameters

`background`  
The background color

`x_shear`  
The number of degrees to shear on the x axis

`y_shear`  
The number of degrees to shear on the y axis

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                             |
|--------------------|-------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span class="function">Imagick::shearImage</span>**

``` php
<?php
function shearImage($imagePath, $color, $shearX, $shearY) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->shearimage($color, $shearX, $shearY);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::sigmoidalContrastImage
===============================

Adjusts the contrast of an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sigmoidalContrastImage</span> ( <span
class="methodparam"><span class="type">bool</span> `$sharpen`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$beta`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Adjusts the contrast of an image with a non-linear sigmoidal contrast
algorithm. Increase the contrast of the image using a sigmoidal transfer
function without saturating highlights or shadows. Contrast indicates
how much to increase the contrast (0 is none; 3 is typical; 20 is
pushing it); mid-point indicates where midtones fall in the resultant
image (0 is white; 50 is middle-gray; 100 is black). Set sharpen to
**`true`** to increase the image contrast otherwise the contrast is
reduced.

See also
<a href="url.imagemagick.usage.color_mods.sigmoidal" class="link external">» ImageMagick v6 Examples - Image Transformations — Sigmoidal Non-linearity Contrast</a>

### Parameters

`sharpen`  
If true increase the contrast, if false decrease the contrast.

`alpha`  
The amount of contrast to apply. 1 is very little, 5 is a significant
amount, 20 is extreme.

`beta`  
Where the midpoint of the gradient will be. This value should be in the
range 0 to 1 - mutliplied by the quantum value for ImageMagick.

`channel`  
Which color channels the contrast will be applied to.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Create a gradient image using <span
class="function">Imagick::sigmoidalContrastImage</span> suitable for
blending two images together smoothly, with the blending defined by
$contrast and $the midpoint**

``` php
<?php

function generateBlendImage($width, $height, $contrast = 10, $midpoint = 0.5) {
    $imagick = new Imagick();
    $imagick->newPseudoImage($width, $height, 'gradient:black-white');
    $quanta = $imagick->getQuantumRange();
    $imagick->sigmoidalContrastImage(true, $contrast, $midpoint * $quanta["quantumRangeLong"]);

    return $imagick; 
}

?>
```

### Errors/Exceptions

Throws ImagickException on error.

Imagick::sketchImage
====================

Simulates a pencil sketch

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sketchImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> )

Simulates a pencil sketch. We convolve the image with a Gaussian
operator of the given radius and standard deviation (sigma). For
reasonable results, radius should be larger than sigma. Use a radius of
0 and Imagick::sketchImage() selects a suitable radius for you. Angle
gives the angle of the blurring motion. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`radius`  
The radius of the Gaussian, in pixels, not counting the center pixel

`sigma`  
The standard deviation of the Gaussian, in pixels.

`angle`  
Apply the effect along this angle.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::sketchImage</span>**

``` php
<?php
function sketchImage($imagePath, $radius, $sigma, $angle) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->sketchimage($radius, $sigma, $angle);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::smushImages
====================

Description

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::smushImages</span> ( <span
class="methodparam"><span class="type">bool</span> `$stack`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
)

Takes all images from the current image pointer to the end of the image
list and smushs them to each other top-to-bottom if the stack parameter
is true, otherwise left-to-right.

### Parameters

`stack`  

`offset`  

### Return Values

The new smushed image.

### Examples

**Example \#1 <span class="function">Imagick::smushImages</span>**

``` php
<?php
function smushImages($imagePath, $imagePath2) {

    $imagick = new \Imagick(realpath($imagePath));
    $imagick2 = new \Imagick(realpath($imagePath2));

    $imagick->addimage($imagick2);
    $smushed = $imagick->smushImages(false, 50);
    $smushed->setImageFormat('jpg');
    header("Content-Type: image/jpg");
    echo $smushed->getImageBlob();
}

?>
```

Imagick::solarizeImage
======================

Applies a solarizing effect to the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::solarizeImage</span> ( <span
class="methodparam"><span class="type">int</span> `$threshold`</span> )

Applies a special effect to the image, similar to the effect achieved in
a photo darkroom by selectively exposing areas of photo sensitive paper
to light. Threshold ranges from 0 to QuantumRange and is a measure of
the extent of the solarization.

### Parameters

`threshold`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::solarizeImage</span>**

``` php
<?php
function solarizeImage($imagePath, $solarizeThreshold) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->solarizeImage($solarizeThreshold * \Imagick::getQuantum());
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::sparseColorImage
=========================

Interpolates colors

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::sparseColorImage</span> ( <span
class="methodparam"><span class="type">int</span>
`$SPARSE_METHOD`</span> , <span class="methodparam"><span
class="type">array</span> `$arguments`</span> \[, <span
class="methodparam"><span class="type">int</span> `$channel`<span
class="initializer"> = Imagick::CHANNEL\_DEFAULT</span></span> \] )

Given the arguments array containing numeric values this method
interpolates the colors found at those coordinates across the whole
image using `sparse_method`. This method is available if Imagick has
been compiled against ImageMagick version 6.4.5 or newer.

### Parameters

`SPARSE_METHOD`  
Refer to this list of
<a href="/imagick/constants.html#SPARSECOLORMETHOD%20constants" class="link">sparse method constants</a>

`arguments`  
An array containing the coordinates. The array is in format *array(1,1,
2,45)*

`channel`  
Provide any channel constant that is valid for your channel mode. To
apply to more than one channel, combine
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>
using bitwise operators. Defaults to **`Imagick::CHANNEL_DEFAULT`**.
Refer to this list of
<a href="/imagick/constants.html#CHANNEL%20constants" class="link">channel constants</a>

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 SPARSECOLORMETHOD\_BARYCENTRIC <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
    function renderImageBarycentric2() {
        $points = [
            [0.30, 0.10, 'red'],
            [0.10, 0.80, 'blue'],
            [0.70, 0.60, 'lime'],
            [0.80, 0.20, 'yellow'],
        ];
        $imagick = createGradientImage(
            400, 400,
            $points,
            \Imagick::SPARSECOLORMETHOD_BARYCENTRIC
        );
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#2 SPARSECOLORMETHOD\_BILINEAR <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
    function renderImageBilinear() {
        $points = [[0.30, 0.10, 'red'], [0.10, 0.80, 'blue'], [0.70, 0.60, 'lime'], [0.80, 0.20, 'yellow'],];
        $imagick = createGradientImage(500, 500, $points, \Imagick::SPARSECOLORMETHOD_BILINEAR);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#3 SPARSECOLORMETHOD\_SPEPARDS <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
    function renderImageShepards() {
        $points = [
            [0.30, 0.10, 'red'],
            [0.10, 0.80, 'blue'],
            [0.70, 0.60, 'lime'],
            [0.80, 0.20, 'yellow'],
        ];
        $imagick = createGradientImage(600, 600, $points, \Imagick::SPARSECOLORMETHOD_SPEPARDS);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#4 SPARSECOLORMETHOD\_VORONOI <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
    function renderImageVoronoi() {
        $points = [
            [0.30, 0.10, 'red'],
            [0.10, 0.80, 'blue'],
            [0.70, 0.60, 'lime'],
            [0.80, 0.20, 'yellow'],
        ];
        $imagick = createGradientImage(500, 500, $points, \Imagick::SPARSECOLORMETHOD_VORONOI);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#5 SPARSECOLORMETHOD\_BARYCENTRIC <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
    function renderImageBarycentric() {
        $points = [
            [0, 0, 'skyblue'],
            [-1, 1, 'skyblue'],
            [1, 1, 'black'],
        ];
        $imagick = createGradientImage(600, 200, $points, \Imagick::SPARSECOLORMETHOD_BARYCENTRIC);
        header("Content-Type: image/png");
        echo $imagick->getImageBlob();
    }

?>
```

**Example \#6 createGradientImage is used by other examples. <span
class="function">Imagick::sparseColorImage</span>**

``` php
<?php
function createGradientImage($width, $height, $colorPoints, $sparseMethod, $absolute = false) {

    $imagick = new \Imagick();
    $imagick->newImage($width, $height, "white");
    $imagick->setImageFormat("png");

    $barycentricPoints = array();

    foreach ($colorPoints as $colorPoint) {

        if ($absolute == true) {
            $barycentricPoints[] = $colorPoint[0];
            $barycentricPoints[] = $colorPoint[1];
        }
        else {
            $barycentricPoints[] = $colorPoint[0] * $width;
            $barycentricPoints[] = $colorPoint[1] * $height;
        }

        if (is_string($colorPoint[2])) {
            $imagickPixel = new \ImagickPixel($colorPoint[2]);
        }
        else if ($colorPoint[2] instanceof \ImagickPixel) {
            $imagickPixel = $colorPoint[2];
        }
        else{
            $errorMessage = sprintf(
                "Value %s is neither a string nor an ImagickPixel class. Cannot use as a color.",
                $colorPoint[2]
            );

            throw new \InvalidArgumentException(
                $errorMessage
            );
        }

        $red = $imagickPixel->getColorValue(\Imagick::COLOR_RED);
        $green = $imagickPixel->getColorValue(\Imagick::COLOR_GREEN);
        $blue = $imagickPixel->getColorValue(\Imagick::COLOR_BLUE);
        $alpha = $imagickPixel->getColorValue(\Imagick::COLOR_ALPHA);

        $barycentricPoints[] = $red;
        $barycentricPoints[] = $green;
        $barycentricPoints[] = $blue;
        $barycentricPoints[] = $alpha;
    }

    $imagick->sparseColorImage($sparseMethod, $barycentricPoints);

    return $imagick;
}

?>
```

Imagick::spliceImage
====================

Splices a solid color into the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::spliceImage</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
, <span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> )

Splices a solid color into the image.

### Parameters

`width`  

`height`  

`x`  

`y`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::spliceImage</span>**

``` php
<?php
function spliceImage($imagePath, $startX, $startY, $width, $height) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->spliceImage($width, $height, $startX, $startY);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::spreadImage
====================

Randomly displaces each pixel in a block

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::spreadImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Special effects method that randomly displaces each pixel in a block
defined by the radius parameter.

### Parameters

`radius`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::spreadImage</span>**

``` php
<?php
function spreadImage($imagePath, $radius) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->spreadImage($radius);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::statisticImage
=======================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::statisticImage</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Replace each pixel with corresponding statistic from the neighborhood of
the specified width and height.

### Parameters

`type`  

`width`  

`height`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::statisticImage</span>**

``` php
<?php
function statisticImage($imagePath, $statisticType, $width, $height, $channel) {
    $imagick = new \Imagick(realpath($imagePath));

    $imagick->statisticImage(
        $statisticType,
        $width,
        $height,
        $channel
    );

    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

statisticImage($imagePath, \Imagick::STATISTIC_MEDIAN, 5, 5, \Imagick::CHANNEL_DEFAULT);

?>
```

Imagick::steganoImage
=====================

Hides a digital watermark within the image

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::steganoImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$watermark_wand`</span> , <span class="methodparam"><span
class="type">int</span> `$offset`</span> )

Hides a digital watermark within the image. Recover the hidden watermark
later to prove that the authenticity of an image. Offset defines the
start position within the image to hide the watermark.

### Parameters

`watermark_wand`  

`offset`  

### Return Values

Returns **`true`** on success.

Imagick::stereoImage
====================

Composites two images

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::stereoImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$offset_wand`</span> )

Composites two images and produces a single image that is the composite
of a left and right image of a stereo pair.

### Parameters

`offset_wand`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::stripImage
===================

Strips an image of all profiles and comments

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::stripImage</span> ( <span
class="methodparam">void</span> )

Strips an image of all profiles and comments.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

Imagick::subImageMatch
======================

Description

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::subImageMatch</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$Imagick`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$offset`</span> \[, <span class="methodparam"><span
class="type">float</span> `&$similarity`</span> \]\] )

Searches for a subimage in the current image and returns a similarity
image such that an exact match location is completely white and if none
of the pixels match, black, otherwise some gray level in-between. You
can also pass in the optional parameters bestMatch and similarity. After
calling the function similarity will be set to the 'score' of the
similarity between the subimage and the matching position in the larger
image, bestMatch will contain an associative array with elements x, y,
width, height that describe the matching region.

### Parameters

`Imagick`  

`offset`  

`similarity`  
A new image that displays the amount of similarity at each pixel.

### Return Values

### Examples

**Example \#1 <span class="function">Imagick::subImageMatch</span>**

``` php
<?php
function subImageMatch($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick2 = clone $imagick;
    $imagick2->cropimage(40, 40, 250, 110);
    $imagick2->vignetteimage(0, 1, 3, 3);

    $similarity = null;
    $bestMatch = null;
    $comparison = $imagick->subImageMatch($imagick2, $bestMatch, $similarity);

    $comparison->setImageFormat('png');
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::swirlImage
===================

Swirls the pixels about the center of the image

### Description

<span class="type">bool</span> <span
class="methodname">Imagick::swirlImage</span> ( <span
class="methodparam"><span class="type">float</span> `$degrees`</span> )

Swirls the pixels about the center of the image, where degrees indicates
the sweep of the arc through which each pixel is moved. You get a more
dramatic effect as the degrees move from 1 to 360.

### Parameters

`degrees`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::swirlImage</span>**

``` php
<?php
function swirlImage($imagePath, $swirl) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->swirlImage($swirl);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::textureImage
=====================

Repeatedly tiles the texture image

### Description

<span class="type">Imagick</span> <span
class="methodname">Imagick::textureImage</span> ( <span
class="methodparam"><span class="type">Imagick</span>
`$texture_wand`</span> )

Repeatedly tiles the texture image across and down the image canvas.

### Parameters

`texture_wand`  
Imagick object to use as texture image

### Return Values

Returns a new Imagick object that has the repeated texture applied.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::textureImage</span>**

``` php
<?php
function textureImage($imagePath) {
    $image = new \Imagick();
    $image->newImage(640, 480, new \ImagickPixel('pink'));
    $image->setImageFormat("jpg");
    $texture = new \Imagick(realpath($imagePath));
    $texture->scaleimage($image->getimagewidth() / 4, $image->getimageheight() / 4);
    $image = $image->textureImage($texture);
    header("Content-Type: image/jpg");
    echo $image;
}

?>
```

Imagick::thresholdImage
=======================

Changes the value of individual pixels based on a threshold

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::thresholdImage</span> ( <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Changes the value of individual pixels based on the intensity of each
pixel compared to threshold. The result is a high-contrast, two color
image.

### Parameters

`threshold`  

`channel`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::thresholdImage</span>**

``` php
<?php
function thresholdimage($imagePath, $threshold, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->thresholdimage($threshold * \Imagick::getQuantum(), $channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::thumbnailImage
=======================

Changes the size of an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::thumbnailImage</span> ( <span
class="methodparam"><span class="type">int</span> `$columns`</span> ,
<span class="methodparam"><span class="type">int</span> `$rows`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$bestfit`<span class="initializer"> = **`false`**</span></span> \[,
<span class="methodparam"><span class="type">bool</span> `$fill`<span
class="initializer"> = **`false`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$legacy`<span
class="initializer"> = **`false`**</span></span> \]\]\] )

Changes the size of an image to the given dimensions and removes any
associated profiles. The goal is to produce small, low cost thumbnail
images suited for display on the Web. If **`true`** is given as a third
parameter then columns and rows parameters are used as maximums for each
side. Both sides will be scaled down until they match or are smaller
than the parameter given for the side.

> **Note**: <span class="simpara"> The behavior of the parameter
> `bestfit` changed in Imagick 3.0.0. Before this version given
> dimensions 400x400 an image of dimensions 200x150 would be left
> untouched. In Imagick 3.0.0 and later the image would be scaled up to
> size 400x300 as this is the "best fit" for the given dimensions. If
> `bestfit` parameter is used both width and height must be given.
> </span>

### Parameters

`columns`  
Image width

`rows`  
Image height

`bestfit`  
Whether to force maximum values

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::thumbnailImage</span>**

``` php
<?php
function thumbnailImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->setbackgroundcolor('rgb(64, 64, 64)');
    $imagick->thumbnailImage(100, 100, true, true);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::tintImage
==================

Applies a color vector to each pixel in the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::tintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$tint`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$opacity`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$legacy`<span class="initializer"> =
**`false`**</span></span> \] )

Applies a color vector to each pixel in the image. The length of the
vector is 0 for black and white and at its maximum for the midtones. The
vector weighing function is f(x)=(1-(4.0\*((x-0.5)\*(x-0.5)))).

### Parameters

`tint`  

`opacity`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Changelog

| Version            | Description                                                                                                                                                                                 |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as the first parameter and a float representing the opacity value as the second parameter. Previous versions allow only an ImagickPixel objects. |

### Examples

**Example \#1 <span class="function">Imagick::tintImage</span>**

``` php
<?php
function tintImage($r, $g, $b, $a) {
    $a = $a / 100;

    $imagick = new \Imagick();
    $imagick->newPseudoImage(400, 400, 'gradient:black-white');

    $tint = new \ImagickPixel("rgb($r, $g, $b)");
    $opacity = new \ImagickPixel("rgb(128, 128, 128, $a)");
    $imagick->tintImage($tint, $opacity);
    $imagick->setImageFormat('png');
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::\_\_toString
=====================

Returns the image as a string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Imagick::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the current image as string. This will only return a single
image; it should not be used for Imagick objects that contain multiple
images e.g. an animated GIF or PDF with multiple pages.

### Parameters

This function has no parameters.

### Return Values

Returns the string content on success or an empty string on failure.

### See Also

-   <span class="methodname">Imagick::getImageBlob</span>
-   <span class="methodname">Imagick::getImagesBlob</span>

Imagick::transformImage
=======================

Convenience method for setting crop size and the image geometry

**Warning**

This function has been *DEPRECATED* as of Imagick 3.4.4. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">Imagick</span>
<span class="methodname">Imagick::transformImage</span> ( <span
class="methodparam"><span class="type">string</span> `$crop`</span> ,
<span class="methodparam"><span class="type">string</span>
`$geometry`</span> )

A convenience method for setting crop size and the image geometry from
strings. This method is available if Imagick has been compiled against
ImageMagick version 6.2.9 or newer.

### Parameters

`crop`  
A crop geometry string. This geometry defines a subregion of the image
to crop.

`geometry`  
An image geometry string. This geometry defines the final size of the
image.

### Return Values

Returns an Imagick object containing the transformed image.

### Examples

**Example \#1 Using <span
class="function">Imagick::transformImage</span>:**

The example creates a 100x100 black image.

``` php
<?php
$image = new Imagick();
$image->newImage(300, 200, "black");
$new_image = $image->transformImage("100x100", "100x100");
$new_image->writeImage('test_out.jpg');
?>
```

### See Also

-   <span class="function">Imagick::cropImage</span>
-   <span class="function">Imagick::resizeImage</span>
-   <span class="function">Imagick::thumbnailImage</span>

Imagick::transformImageColorspace
=================================

Transforms an image to a new colorspace

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::transformImageColorspace</span> (
<span class="methodparam"><span class="type">int</span>
`$colorspace`</span> )

Transforms an image to a new colorspace.

### Parameters

`colorspace`  
The colorspace the image should be transformed to, one of the
<a href="/imagick/constants.html#COLORSPACE%20constants" class="link">COLORSPACE constants</a>
e.g. Imagick::COLORSPACE\_CMYK.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="methodname">Imagick::transformImageColorspace</span> example**

Transforms an image to a new colorspace, and then extracts a single
channel so that the individual channel values can be viewed.

``` php
<?php
function transformImageColorspace($imagePath, $colorSpace, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->transformimagecolorspace($colorSpace);
    //channel should be one of the channel constants e.g. \Imagick::CHANNEL_BLUE 
    $imagick->separateImageChannel($channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}
?>
```

### See Also

-   <span class="methodname">Imagick::setColorSpace</span>

### Examples

**Example \#2 <span
class="function">Imagick::transformImageColorspace</span>**

``` php
<?php
function transformImageColorspace($imagePath, $colorSpace, $channel) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->transformimagecolorspace($colorSpace);
    $imagick->separateImageChannel($channel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::transparentPaintImage
==============================

Paints pixels transparent

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::transparentPaintImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$target`</span> ,
<span class="methodparam"><span class="type">float</span>
`$alpha`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> , <span
class="methodparam"><span class="type">bool</span> `$invert`</span> )

Paints pixels matching the target color transparent. This method is
available if Imagick has been compiled against ImageMagick version 6.3.8
or newer.

### Parameters

`target`  
The target color to paint

`alpha`  
The level of transparency: 1.0 is fully opaque and 0.0 is fully
transparent.

`fuzz`  
The amount of fuzz. For example, set fuzz to 10 and the color red at
intensities of 100 and 102 respectively are now interpreted as the same
color.

`invert`  
If **`true`** paints any pixel that does not match the target color.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">Imagick::transparentPaintImage</span>**

``` php
<?php
function transparentPaintImage($color, $alpha, $fuzz) {
    $imagick = new \Imagick(realpath("images/BlueScreen.jpg"));

    //Need to be in a format that supports transparency
    $imagick->setimageformat('png');

    $imagick->transparentPaintImage(
        $color, $alpha, $fuzz * \Imagick::getQuantum(), false
    );

    //Not required, but helps tidy up left over pixels
    $imagick->despeckleimage();

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::transposeImage
=======================

Creates a vertical mirror image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::transposeImage</span> ( <span
class="methodparam">void</span> )

Creates a vertical mirror image by reflecting the pixels around the
central x-axis while rotating them 90-degrees. This method is available
if Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::transverseImage</span>

### Examples

**Example \#1 <span class="function">Imagick::transposeImage</span>**

``` php
<?php
function transposeImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->transposeImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::transverseImage
========================

Creates a horizontal mirror image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::transverseImage</span> ( <span
class="methodparam">void</span> )

Creates a horizontal mirror image by reflecting the pixels around the
central y-axis while rotating them 270-degrees. This method is available
if Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::transposeImage</span>

### Examples

**Example \#1 <span class="function">Imagick::transverseImage</span>**

``` php
<?php
function transverseImage($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->transverseImage();
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::trimImage
==================

Remove edges from the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::trimImage</span> ( <span
class="methodparam"><span class="type">float</span> `$fuzz`</span> )

Remove edges that are the background color from the image. This method
is available if Imagick has been compiled against ImageMagick version
6.2.9 or newer.

### Parameters

`fuzz`  
By default target must match a particular pixel color exactly. However,
in many cases two colors may differ by a small amount. The fuzz member
of image defines how much tolerance is acceptable to consider two colors
as the same. This parameter represents the variation on the quantum
range.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 Using <span class="function">Imagick::trimImage</span>:**

Trim an image, then display to the browser.

``` php
<?php
/* Create the object and read the image in */
$im = new Imagick("image.jpg");

/* Trim the image. */
$im->trimImage(0);

/* Ouput the image */
header("Content-Type: image/" . $im->getImageFormat());
echo $im;
?>
```

### See Also

-   <span class="function">Imagick::getQuantumDepth</span>
-   <span class="function">Imagick::getQuantumRange</span>
-   <span class="function">imagecropauto</span>

Imagick::uniqueImageColors
==========================

Discards all but one of any pixel color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::uniqueImageColors</span> ( <span
class="methodparam">void</span> )

Discards all but one of any pixel color. This method is available if
Imagick has been compiled against ImageMagick version 6.2.9 or newer.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">Imagick::uniqueImageColors</span>**

``` php
<?php
function uniqueImageColors($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    //Reduce the image to 256 colours nicely.
    $imagick->quantizeImage(256, \Imagick::COLORSPACE_YIQ, 0, false, false);
    $imagick->uniqueImageColors();
    $imagick->scaleimage($imagick->getImageWidth(), $imagick->getImageHeight() * 20);
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::unsharpMaskImage
=========================

Sharpens an image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::unsharpMaskImage</span> ( <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$sigma`</span> , <span class="methodparam"><span
class="type">float</span> `$amount`</span> , <span
class="methodparam"><span class="type">float</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$channel`<span class="initializer"> =
Imagick::CHANNEL\_DEFAULT</span></span> \] )

Sharpens an image. We convolve the image with a Gaussian operator of the
given radius and standard deviation (sigma). For reasonable results,
radius should be larger than sigma. Use a radius of 0 and
Imagick::UnsharpMaskImage() selects a suitable radius for you.

### Parameters

`radius`  

`sigma`  

`amount`  

`threshold`  

`channel`  

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### Examples

**Example \#1 <span class="function">Imagick::unsharpMaskImage</span>**

``` php
<?php
function unsharpMaskImage($imagePath, $radius, $sigma, $amount, $unsharpThreshold) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->unsharpMaskImage($radius, $sigma, $amount, $unsharpThreshold);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::valid
==============

Checks if the current item is valid

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::valid</span> ( <span
class="methodparam">void</span> )

Checks if the current item is valid.

### Return Values

Returns **`true`** on success.

Imagick::vignetteImage
======================

Adds vignette filter to the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::vignetteImage</span> ( <span
class="methodparam"><span class="type">float</span> `$blackPoint`</span>
, <span class="methodparam"><span class="type">float</span>
`$whitePoint`</span> , <span class="methodparam"><span
class="type">int</span> `$x`</span> , <span class="methodparam"><span
class="type">int</span> `$y`</span> )

Softens the edges of the image in vignette style. This method is
available if Imagick has been compiled against ImageMagick version 6.2.9
or newer.

### Parameters

`blackPoint`  
The black point.

`whitePoint`  
The white point

`x`  
X offset of the ellipse

`y`  
Y offset of the ellipse

### Return Values

Returns **`true`** on success.

### See Also

-   <span class="function">Imagick::waveImage</span>
-   <span class="function">Imagick::swirlImage</span>

### Examples

**Example \#1 <span class="function">Imagick::vignetteImage</span>**

``` php
<?php
function vignetteImage($imagePath, $blackPoint, $whitePoint, $x, $y) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->vignetteImage($blackPoint, $whitePoint, $x, $y);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::waveImage
==================

Applies wave filter to the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::waveImage</span> ( <span
class="methodparam"><span class="type">float</span> `$amplitude`</span>
, <span class="methodparam"><span class="type">float</span>
`$length`</span> )

Applies a wave filter to the image. This method is available if Imagick
has been compiled against ImageMagick version 6.2.9 or newer.

### Parameters

`amplitude`  
The amplitude of the wave.

`length`  
The length of the wave.

### Return Values

Returns **`true`** on success.

### Errors/Exceptions

Throws ImagickException on error.

### See Also

-   <span class="function">Imagick::solarizeImage</span>
-   <span class="function">Imagick::oilpaintImage</span>
-   <span class="function">Imagick::embossImage</span>
-   <span class="function">Imagick::addNoiseImage</span>
-   <span class="function">Imagick::swirlImage</span>

### Examples

**Example \#1 WaveImage can be quite slow <span
class="function">Imagick::waveImage</span>**

``` php
<?php
function waveImage($imagePath, $amplitude, $length) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->waveImage($amplitude, $length);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::whiteThresholdImage
============================

Force all pixels above the threshold into white

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::whiteThresholdImage</span> ( <span
class="methodparam"><span class="type">mixed</span> `$threshold`</span>
)

Is like Imagick::ThresholdImage() but force all pixels above the
threshold into white while leaving all pixels below the threshold
unchanged.

### Parameters

`threshold`  

### Return Values

Returns **`true`** on success.

### Changelog

| Version            | Description                                                                                                     |
|--------------------|-----------------------------------------------------------------------------------------------------------------|
| PECL imagick 2.1.0 | Now allows a string representing the color as a parameter. Previous versions allow only an ImagickPixel object. |

### Examples

**Example \#1 <span
class="function">Imagick::whiteThresholdImage</span>**

``` php
<?php
function whiteThresholdImage($imagePath, $color) {
    $imagick = new \Imagick(realpath($imagePath));
    $imagick->whiteThresholdImage($color);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();
}

?>
```

Imagick::writeImage
===================

Writes an image to the specified filename

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::writeImage</span> (\[ <span
class="methodparam"><span class="type">string</span> `$filename`<span
class="initializer"> = NULL</span></span> \] )

Writes an image to the specified filename. If the filename parameter is
NULL, the image is written to the filename set by Imagick::readImage()
or Imagick::setImageFilename().

### Parameters

`filename`  
Filename where to write the image. The extension of the filename defines
the type of the file. Format can be forced regardless of file extension
using format: prefix, for example "jpg:test.png".

### Return Values

Returns **`true`** on success.

Imagick::writeImageFile
=======================

Writes an image to a filehandle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::writeImageFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$format`</span> \] )

Writes the image sequence to an open filehandle. The handle must be
opened with for example fopen. This method is available if Imagick has
been compiled against ImageMagick version 6.3.6 or newer.

### Parameters

`filehandle`  
Filehandle where to write the image

### Return Values

Returns **`true`** on success.

Imagick::writeImages
====================

Writes an image or image sequence

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::writeImages</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">bool</span>
`$adjoin`</span> )

Writes an image or image sequence.

### Parameters

`filename`  

`adjoin`  

### Return Values

Returns **`true`** on success.

Imagick::writeImagesFile
========================

Writes frames to a filehandle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Imagick::writeImagesFile</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$format`</span> \] )

Writes all image frames into an open filehandle. This method can be used
to write animated gifs or other multiframe images into open filehandle.
This method is available if Imagick has been compiled against
ImageMagick version 6.3.6 or newer.

### Parameters

`filehandle`  
Filehandle where to write the images

### Return Values

Returns **`true`** on success.

Class synopsis
--------------

**ImagickDraw**

<span class="ooclass"> class **ImagickDraw**</span> {

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">affine</span> ( <span class="methodparam"><span
class="type">array</span> `$affine`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">annotation</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">arc</span> ( <span class="methodparam"><span
class="type">float</span> `$sx`</span> , <span class="methodparam"><span
class="type">float</span> `$sy`</span> , <span class="methodparam"><span
class="type">float</span> `$ex`</span> , <span class="methodparam"><span
class="type">float</span> `$ey`</span> , <span class="methodparam"><span
class="type">float</span> `$sd`</span> , <span class="methodparam"><span
class="type">float</span> `$ed`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bezier</span> ( <span class="methodparam"><span
class="type">array</span> `$coordinates`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">circle</span> ( <span class="methodparam"><span
class="type">float</span> `$ox`</span> , <span class="methodparam"><span
class="type">float</span> `$oy`</span> , <span class="methodparam"><span
class="type">float</span> `$px`</span> , <span class="methodparam"><span
class="type">float</span> `$py`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickDraw</span> <span class="methodname">clone</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">color</span> ( <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">int</span> `$paintMethod`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">comment</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">composite</span> ( <span
class="methodparam"><span class="type">int</span> `$compose`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> ,
<span class="methodparam"><span class="type">float</span>
`$width`</span> , <span class="methodparam"><span
class="type">float</span> `$height`</span> , <span
class="methodparam"><span class="type">Imagick</span>
`$compositeWand`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ellipse</span> ( <span
class="methodparam"><span class="type">float</span> `$ox`</span> , <span
class="methodparam"><span class="type">float</span> `$oy`</span> , <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> , <span
class="methodparam"><span class="type">float</span> `$start`</span> ,
<span class="methodparam"><span class="type">float</span> `$end`</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getClipPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getClipRule</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getClipUnits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getFillColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getFillOpacity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFillRule</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFont</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFontFamily</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getFontSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFontStretch</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFontStyle</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFontWeight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGravity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getStrokeAntialias</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getStrokeColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getStrokeDashArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getStrokeDashOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStrokeLineCap</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStrokeLineJoin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStrokeMiterLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getStrokeOpacity</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getStrokeWidth</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTextAlignment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getTextAntialias</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTextDecoration</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTextEncoding</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getTextInterlineSpacing</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getTextInterwordSpacing</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getTextKerning</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">getTextUnderColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getVectorGraphics</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">line</span> ( <span class="methodparam"><span
class="type">float</span> `$sx`</span> , <span class="methodparam"><span
class="type">float</span> `$sy`</span> , <span class="methodparam"><span
class="type">float</span> `$ex`</span> , <span class="methodparam"><span
class="type">float</span> `$ey`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">matte</span> ( <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">int</span> `$paintMethod`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathClose</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToQuadraticBezierAbsolute</span> (
<span class="methodparam"><span class="type">float</span> `$x1`</span> ,
<span class="methodparam"><span class="type">float</span> `$y1`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToQuadraticBezierRelative</span> (
<span class="methodparam"><span class="type">float</span> `$x1`</span> ,
<span class="methodparam"><span class="type">float</span> `$y1`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToQuadraticBezierSmoothAbsolute</span>
( <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToQuadraticBezierSmoothRelative</span>
( <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToSmoothAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathCurveToSmoothRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathEllipticArcAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> , <span
class="methodparam"><span class="type">float</span>
`$x_axis_rotation`</span> , <span class="methodparam"><span
class="type">bool</span> `$large_arc_flag`</span> , <span
class="methodparam"><span class="type">bool</span> `$sweep_flag`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathEllipticArcRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> , <span
class="methodparam"><span class="type">float</span>
`$x_axis_rotation`</span> , <span class="methodparam"><span
class="type">bool</span> `$large_arc_flag`</span> , <span
class="methodparam"><span class="type">bool</span> `$sweep_flag`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathFinish</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToHorizontalAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToHorizontalRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToVerticalAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathLineToVerticalRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathMoveToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathMoveToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pathStart</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">point</span> ( <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">polygon</span> ( <span
class="methodparam"><span class="type">array</span>
`$coordinates`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">polyline</span> ( <span
class="methodparam"><span class="type">array</span>
`$coordinates`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">popClipPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">popDefs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">popPattern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">push</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pushClipPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$clip_mask_id`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pushDefs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pushPattern</span> ( <span
class="methodparam"><span class="type">string</span>
`$pattern_id`</span> , <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">float</span> `$width`</span> , <span
class="methodparam"><span class="type">float</span> `$height`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rectangle</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">render</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resetVectorGraphics</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rotate</span> ( <span class="methodparam"><span
class="type">float</span> `$degrees`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">roundRectangle</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">scale</span> ( <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setClipPath</span> ( <span
class="methodparam"><span class="type">string</span> `$clip_mask`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setClipRule</span> ( <span
class="methodparam"><span class="type">int</span> `$fill_rule`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setClipUnits</span> ( <span
class="methodparam"><span class="type">int</span> `$clip_units`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFillAlpha</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFillColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$fill_pixel`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFillOpacity</span> ( <span
class="methodparam"><span class="type">float</span>
`$fillOpacity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFillPatternURL</span> ( <span
class="methodparam"><span class="type">string</span> `$fill_url`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFillRule</span> ( <span
class="methodparam"><span class="type">int</span> `$fill_rule`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFont</span> ( <span
class="methodparam"><span class="type">string</span> `$font_name`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFontFamily</span> ( <span
class="methodparam"><span class="type">string</span>
`$font_family`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFontSize</span> ( <span
class="methodparam"><span class="type">float</span> `$pointsize`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFontStretch</span> ( <span
class="methodparam"><span class="type">int</span> `$fontStretch`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFontStyle</span> ( <span
class="methodparam"><span class="type">int</span> `$style`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFontWeight</span> ( <span
class="methodparam"><span class="type">int</span> `$font_weight`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeAlpha</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeAntialias</span> ( <span
class="methodparam"><span class="type">bool</span>
`$stroke_antialias`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$stroke_pixel`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeDashArray</span> ( <span
class="methodparam"><span class="type">array</span> `$dashArray`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeDashOffset</span> ( <span
class="methodparam"><span class="type">float</span>
`$dash_offset`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeLineCap</span> ( <span
class="methodparam"><span class="type">int</span> `$linecap`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeLineJoin</span> ( <span
class="methodparam"><span class="type">int</span> `$linejoin`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeMiterLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$miterlimit`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeOpacity</span> ( <span
class="methodparam"><span class="type">float</span>
`$stroke_opacity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokePatternURL</span> ( <span
class="methodparam"><span class="type">string</span>
`$stroke_url`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStrokeWidth</span> ( <span
class="methodparam"><span class="type">float</span>
`$stroke_width`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextAlignment</span> ( <span
class="methodparam"><span class="type">int</span> `$alignment`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextAntialias</span> ( <span
class="methodparam"><span class="type">bool</span> `$antiAlias`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextDecoration</span> ( <span
class="methodparam"><span class="type">int</span> `$decoration`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextEncoding</span> ( <span
class="methodparam"><span class="type">string</span> `$encoding`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextInterlineSpacing</span> ( <span
class="methodparam"><span class="type">float</span> `$spacing`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextInterwordSpacing</span> ( <span
class="methodparam"><span class="type">float</span> `$spacing`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextKerning</span> ( <span
class="methodparam"><span class="type">float</span> `$kerning`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setTextUnderColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$under_color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setVectorGraphics</span> ( <span
class="methodparam"><span class="type">string</span> `$xml`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setViewbox</span> ( <span
class="methodparam"><span class="type">int</span> `$x1`</span> , <span
class="methodparam"><span class="type">int</span> `$y1`</span> , <span
class="methodparam"><span class="type">int</span> `$x2`</span> , <span
class="methodparam"><span class="type">int</span> `$y2`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">skewX</span> ( <span class="methodparam"><span
class="type">float</span> `$degrees`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">skewY</span> ( <span class="methodparam"><span
class="type">float</span> `$degrees`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">translate</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

}

ImagickDraw::affine
===================

Adjusts the current affine transformation matrix

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::affine</span> ( <span
class="methodparam"><span class="type">array</span> `$affine`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Adjusts the current affine transformation matrix with the specified
affine transformation matrix.

### Parameters

`affine`  
Affine matrix parameters

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::affine</span>**

``` php
<?php
function affine($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeWidth(1);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);

    $PI = 3.141592653589794;
    $angle = 60 * $PI / 360;

    //Scale the drawing co-ordinates.
    $affineScale = array("sx" => 1.75, "sy" => 1.75, "rx" => 0, "ry" => 0, "tx" => 0, "ty" => 0);

    //Shear the drawing co-ordinates.
    $affineShear = array("sx" => 1, "sy" => 1, "rx" => sin($angle), "ry" => -sin($angle), "tx" => 0, "ty" => 0);

    //Rotate the drawing co-ordinates. The shear affine matrix
    //produces incorrectly scaled drawings.
    $affineRotate = array("sx" => cos($angle), "sy" => cos($angle), "rx" => sin($angle), "ry" => -sin($angle), "tx" => 0, "ty" => 0,);

    //Translate (offset) the drawing
    $affineTranslate = array("sx" => 1, "sy" => 1, "rx" => 0, "ry" => 0, "tx" => 30, "ty" => 30);

    //The identiy affine matrix
    $affineIdentity = array("sx" => 1, "sy" => 1, "rx" => 0, "ry" => 0, "tx" => 0, "ty" => 0);

    $examples = [$affineScale, $affineShear, $affineRotate, $affineTranslate, $affineIdentity,];

    $count = 0;

    foreach ($examples as $example) {
        $draw->push();
        $draw->translate(($count % 2) * 250, intval($count / 2) * 250);
        $draw->translate(100, 100);
        $draw->affine($example);
        $draw->rectangle(-50, -50, 50, 50);
        $draw->pop();
        $count++;
    }

    //Create an image object which the draw commands can be rendered into
    $image = new \Imagick();
    $image->newImage(500, 750, $backgroundColor);
    $image->setImageFormat("png");

    //Render the draw commands in the ImagickDraw object 
    //into the image.
    $image->drawImage($draw);

    //Send the image to the browser
    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::annotation
=======================

Draws text on the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::annotation</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws text on the image.

### Parameters

`x`  
The x coordinate where text is drawn

`y`  
The y coordinate where text is drawn

`text`  
The text to draw on the image

### Return Values

No value is returned.

ImagickDraw::arc
================

Draws an arc

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::arc</span> ( <span
class="methodparam"><span class="type">float</span> `$sx`</span> , <span
class="methodparam"><span class="type">float</span> `$sy`</span> , <span
class="methodparam"><span class="type">float</span> `$ex`</span> , <span
class="methodparam"><span class="type">float</span> `$ey`</span> , <span
class="methodparam"><span class="type">float</span> `$sd`</span> , <span
class="methodparam"><span class="type">float</span> `$ed`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws an arc falling within a specified bounding rectangle on the image.

### Parameters

`sx`  
Starting x ordinate of bounding rectangle

`sy`  
starting y ordinate of bounding rectangle

`ex`  
ending x ordinate of bounding rectangle

`ey`  
ending y ordinate of bounding rectangle

`sd`  
starting degrees of rotation

`ed`  
ending degrees of rotation

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::arc</span>**

``` php
<?php
function arc($strokeColor, $fillColor, $backgroundColor, $startX, $startY, $endX, $endY, $startAngle, $endAngle) {

    //Create a ImagickDraw object to draw into.
    $draw = new \ImagickDraw();
    $draw->setStrokeWidth(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);

    $draw->arc($startX, $startY, $endX, $endY, $startAngle, $endAngle);

    //Create an image object which the draw commands can be rendered into
    $image = new \Imagick();
    $image->newImage(IMAGE_WIDTH, IMAGE_HEIGHT, $backgroundColor);
    $image->setImageFormat("png");

    //Render the draw commands in the ImagickDraw object 
    //into the image.
    $image->drawImage($draw);

    //Send the image to the browser
    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::bezier
===================

Draws a bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::bezier</span> ( <span
class="methodparam"><span class="type">array</span>
`$coordinates`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a bezier curve through a set of points on the image.

### Parameters

`coordinates`  
Multidimensional array like array( array( 'x' =\> 1, 'y' =\> 2 ), array(
'x' =\> 3, 'y' =\> 4 ) )

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::bezier</span>**

``` php
<?php
function bezier($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $strokeColor = new \ImagickPixel($strokeColor);
    $fillColor = new \ImagickPixel($fillColor);

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);

    $smoothPointsSet = [
        [
            ['x' => 10.0 * 5, 'y' => 10.0 * 5],
            ['x' => 30.0 * 5, 'y' => 90.0 * 5],
            ['x' => 25.0 * 5, 'y' => 10.0 * 5],
            ['x' => 50.0 * 5, 'y' => 50.0 * 5],
        ], 
        [
            ['x' => 50.0 * 5, 'y' => 50.0 * 5],
            ['x' => 75.0 * 5, 'y' => 90.0 * 5],
            ['x' => 70.0 * 5, 'y' => 10.0 * 5],
            ['x' => 90.0 * 5, 'y' => 40.0 * 5],
        ],
    ];

    foreach ($smoothPointsSet as $points) {
        $draw->bezier($points);
    }

    $disjointPoints = [
        [
            ['x' => 10 * 5, 'y' => 10 * 5], 
            ['x' => 30 * 5, 'y' => 90 * 5], 
            ['x' => 25 * 5, 'y' => 10 * 5],
            ['x' => 50 * 5, 'y' => 50 * 5],
        ],
        [
            ['x' => 50 * 5, 'y' => 50 * 5], 
            ['x' => 80 * 5, 'y' => 50 * 5],
            ['x' => 70 * 5, 'y' => 10 * 5],
            ['x' => 90 * 5, 'y' => 40 * 5],
         ]
    ];
    $draw->translate(0, 200);

    foreach ($disjointPoints as $points) {
        $draw->bezier($points);
    }

    //Create an image object which the draw commands can be rendered into
    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    //Render the draw commands in the ImagickDraw object 
    //into the image.
    $imagick->drawImage($draw);

    //Send the image to the browser
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::circle
===================

Draws a circle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::circle</span> ( <span
class="methodparam"><span class="type">float</span> `$ox`</span> , <span
class="methodparam"><span class="type">float</span> `$oy`</span> , <span
class="methodparam"><span class="type">float</span> `$px`</span> , <span
class="methodparam"><span class="type">float</span> `$py`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a circle on the image.

### Parameters

`ox`  
origin x coordinate

`oy`  
origin y coordinate

`px`  
perimeter x coordinate

`py`  
perimeter y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::circle</span>**

``` php
<?php
function circle($strokeColor, $fillColor, $backgroundColor, $originX, $originY, $endX, $endY) {

    //Create a ImagickDraw object to draw into.
    $draw = new \ImagickDraw();

    $strokeColor = new \ImagickPixel($strokeColor);
    $fillColor = new \ImagickPixel($fillColor);

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->circle($originX, $originY, $endX, $endY);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::clear
==================

Clears the ImagickDraw

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::clear</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Clears the ImagickDraw object of any accumulated commands, and resets
the settings it contains to their defaults.

### Return Values

Returns an ImagickDraw object.

ImagickDraw::clone
==================

Makes an exact copy of the specified ImagickDraw object

### Description

<span class="modifier">public</span> <span
class="type">ImagickDraw</span> <span
class="methodname">ImagickDraw::clone</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Makes an exact copy of the specified ImagickDraw object.

### Return Values

What the function returns, first on success, then on failure. See also
the &return.success; entity

ImagickDraw::color
==================

Draws color on image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::color</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$paintMethod`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws color on image using the current fill color, starting at specified
position, and using specified paint method.

### Parameters

`x`  
x coordinate of the paint

`y`  
y coordinate of the paint

`paintMethod`  
one of the PAINT\_ constants

### Return Values

No value is returned.

ImagickDraw::comment
====================

Adds a comment

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::comment</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Adds a comment to a vector output stream.

### Parameters

`comment`  
The comment string to add to vector output stream

### Return Values

No value is returned.

ImagickDraw::composite
======================

Composites an image onto the current image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::composite</span> ( <span
class="methodparam"><span class="type">int</span> `$compose`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> ,
<span class="methodparam"><span class="type">float</span>
`$width`</span> , <span class="methodparam"><span
class="type">float</span> `$height`</span> , <span
class="methodparam"><span class="type">Imagick</span>
`$compositeWand`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Composites an image onto the current image, using the specified
composition operator, specified position, and at the specified size.

### Parameters

`compose`  
composition operator. One of COMPOSITE\_ constants

`x`  
x coordinate of the top left corner

`y`  
y coordinate of the top left corner

`width`  
width of the composition image

`height`  
height of the composition image

`compositeWand`  
the Imagick object where composition image is taken from

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickDraw::composite</span>**

``` php
<?php
function composite($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setFillOpacity(1);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeWidth(2);
    $draw->setFont("../fonts/CANDY.TTF");
    $draw->setFontSize(140);
    $draw->rectangle(0, 0, 1000, 300);
    $draw->setFillColor('white');
    $draw->setfillopacity(1);
    $draw->annotation(50, 180, "Lorem Ipsum!");

    //Create an image object which the draw commands can be rendered into
    $imagick = new \Imagick();
    $imagick->newImage(1000, 302, $backgroundColor);
    $imagick->setImageFormat("png");

    //Render the draw commands in the ImagickDraw object 
    //into the image.
    $imagick->drawImage($draw);

    //Send the image to the browser
    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::\_\_construct
==========================

The ImagickDraw constructor

### Description

<span class="modifier">public</span> <span
class="methodname">ImagickDraw::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

The ImagickDraw constructor

### Return Values

No value is returned.

ImagickDraw::destroy
====================

Frees all associated resources

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::destroy</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Frees all resources associated with the ImagickDraw object.

### Return Values

No value is returned.

ImagickDraw::ellipse
====================

Draws an ellipse on the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::ellipse</span> ( <span
class="methodparam"><span class="type">float</span> `$ox`</span> , <span
class="methodparam"><span class="type">float</span> `$oy`</span> , <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> , <span
class="methodparam"><span class="type">float</span> `$start`</span> ,
<span class="methodparam"><span class="type">float</span> `$end`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws an ellipse on the image.

### Parameters

`ox`  

`oy`  

`rx`  

`ry`  

`start`  

`end`  

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::ellipse</span>**

``` php
<?php
function ellipse($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->ellipse(125, 70, 100, 50, 0, 360);
    $draw->ellipse(350, 70, 100, 50, 0, 315);

    $draw->push();
    $draw->translate(125, 250);
    $draw->rotate(30);
    $draw->ellipse(0, 0, 100, 50, 0, 360);
    $draw->pop();

    $draw->push();
    $draw->translate(350, 250);
    $draw->rotate(30);
    $draw->ellipse(0, 0, 100, 50, 0, 315);
    $draw->pop();

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::getClipPath
========================

Obtains the current clipping path ID

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickDraw::getClipPath</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Obtains the current clipping path ID.

### Return Values

Returns a string containing the clip path ID or false if no clip path
exists.

ImagickDraw::getClipRule
========================

Returns the current polygon fill rule

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getClipRule</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the current polygon fill rule to be used by the clipping path.

### Return Values

Returns one of the FILLRULE\_ constants.

ImagickDraw::getClipUnits
=========================

Returns the interpretation of clip path units

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getClipUnits</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the interpretation of clip path units.

### Return Values

Returns an int on success.

ImagickDraw::getFillColor
=========================

Returns the fill color

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">ImagickDraw::getFillColor</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the fill color used for drawing filled objects.

### Return Values

Returns an ImagickPixel object.

ImagickDraw::getFillOpacity
===========================

Returns the opacity used when drawing

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getFillOpacity</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the opacity used when drawing using the fill color or fill
texture. Fully opaque is 1.0.

### Return Values

The opacity.

ImagickDraw::getFillRule
========================

Returns the fill rule

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getFillRule</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the fill rule used while drawing polygons.

### Return Values

Returns a FILLRULE\_ constant

ImagickDraw::getFont
====================

Returns the font

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickDraw::getFont</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns a string specifying the font used when annotating with text.

### Return Values

Returns a string on success and false if no font is set.

ImagickDraw::getFontFamily
==========================

Returns the font family

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickDraw::getFontFamily</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the font family to use when annotating with text.

### Return Values

Returns the font family currently selected or false if font family is
not set.

ImagickDraw::getFontSize
========================

Returns the font pointsize

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getFontSize</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the font pointsize used when annotating with text.

### Return Values

Returns the font size associated with the current ImagickDraw object.

ImagickDraw::getFontStretch
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getFontStretch</span> ( <span
class="methodparam">void</span> )

Gets the font stretch to use when annotating with text. Returns a
StretchType.

### Parameters

This function has no parameters.

### Return Values

ImagickDraw::getFontStyle
=========================

Returns the font style

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getFontStyle</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the font style used when annotating with text.

### Return Values

Returns the font style constant (STYLE\_) associated with the
ImagickDraw object or 0 if no style is set.

ImagickDraw::getFontWeight
==========================

Returns the font weight

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getFontWeight</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the font weight used when annotating with text.

### Return Values

Returns an int on success and 0 if no weight is set.

ImagickDraw::getGravity
=======================

Returns the text placement gravity

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getGravity</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the text placement gravity used when annotating with text.

### Return Values

Returns a GRAVITY\_ constant on success and 0 if no gravity is set.

ImagickDraw::getStrokeAntialias
===============================

Returns the current stroke antialias setting

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::getStrokeAntialias</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the current stroke antialias setting. Stroked outlines are
antialiased by default. When antialiasing is disabled stroked pixels are
thresholded to determine if the stroke color or underlying canvas color
should be used.

### Return Values

Returns **`true`** if antialiasing is on and false if it is off.

ImagickDraw::getStrokeColor
===========================

Returns the color used for stroking object outlines

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">ImagickDraw::getStrokeColor</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the color used for stroking object outlines.

### Parameters

`stroke_color`  

### Return Values

Returns an ImagickPixel object which describes the color.

ImagickDraw::getStrokeDashArray
===============================

Returns an array representing the pattern of dashes and gaps used to
stroke paths

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickDraw::getStrokeDashArray</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns an array representing the pattern of dashes and gaps used to
stroke paths.

### Return Values

Returns an array on success and empty array if not set.

ImagickDraw::getStrokeDashOffset
================================

Returns the offset into the dash pattern to start the dash

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getStrokeDashOffset</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the offset into the dash pattern to start the dash.

### Return Values

Returns a float representing the offset and 0 if it's not set.

ImagickDraw::getStrokeLineCap
=============================

Returns the shape to be used at the end of open subpaths when they are
stroked

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getStrokeLineCap</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the shape to be used at the end of open subpaths when they are
stroked.

### Return Values

Returns one of the LINECAP\_ constants or 0 if stroke linecap is not
set.

ImagickDraw::getStrokeLineJoin
==============================

Returns the shape to be used at the corners of paths when they are
stroked

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getStrokeLineJoin</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the shape to be used at the corners of paths (or other vector
shapes) when they are stroked.

### Return Values

Returns one of the LINEJOIN\_ constants or 0 if stroke line join is not
set.

ImagickDraw::getStrokeMiterLimit
================================

Returns the stroke miter limit

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getStrokeMiterLimit</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the miter limit. When two line segments meet at a sharp angle
and miter joins have been specified for 'lineJoin', it is possible for
the miter to extend far beyond the thickness of the line stroking the
path. The 'miterLimit' imposes a limit on the ratio of the miter length
to the 'lineWidth'.

### Return Values

Returns an int describing the miter limit and 0 if no miter limit is
set.

ImagickDraw::getStrokeOpacity
=============================

Returns the opacity of stroked object outlines

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getStrokeOpacity</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the opacity of stroked object outlines.

### Return Values

Returns a double describing the opacity.

ImagickDraw::getStrokeWidth
===========================

Returns the width of the stroke used to draw object outlines

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getStrokeWidth</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the width of the stroke used to draw object outlines.

### Return Values

Returns a double describing the stroke width.

ImagickDraw::getTextAlignment
=============================

Returns the text alignment

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getTextAlignment</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the alignment applied when annotating with text.

### Return Values

Returns one of the ALIGN\_ constants and 0 if no align is set.

ImagickDraw::getTextAntialias
=============================

Returns the current text antialias setting

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::getTextAntialias</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the current text antialias setting, which determines whether
text is antialiased. Text is antialiased by default.

### Return Values

Returns **`true`** if text is antialiased and false if not.

ImagickDraw::getTextDecoration
==============================

Returns the text decoration

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickDraw::getTextDecoration</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the decoration applied when annotating with text.

### Return Values

Returns one of the DECORATION\_ constants and 0 if no decoration is set.

ImagickDraw::getTextEncoding
============================

Returns the code set used for text annotations

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickDraw::getTextEncoding</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns a string which specifies the code set used for text annotations.

### Return Values

Returns a string specifying the code set or false if text encoding is
not set.

ImagickDraw::getTextInterlineSpacing
====================================

Description

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getTextInterlineSpacing</span> (
<span class="methodparam">void</span> )

Gets the text interword spacing.

### Parameters

This function has no parameters.

### Return Values

ImagickDraw::getTextInterwordSpacing
====================================

Description

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getTextInterwordSpacing</span> (
<span class="methodparam">void</span> )

Gets the text interword spacing.

### Parameters

This function has no parameters.

### Return Values

ImagickDraw::getTextKerning
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickDraw::getTextKerning</span> ( <span
class="methodparam">void</span> )

Gets the text kerning.

### Parameters

This function has no parameters.

### Return Values

ImagickDraw::getTextUnderColor
==============================

Returns the text under color

### Description

<span class="modifier">public</span> <span
class="type">ImagickPixel</span> <span
class="methodname">ImagickDraw::getTextUnderColor</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the color of a background rectangle to place under text
annotations.

### Return Values

Returns an ImagickPixel object describing the color.

ImagickDraw::getVectorGraphics
==============================

Returns a string containing vector graphics

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickDraw::getVectorGraphics</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns a string which specifies the vector graphics generated by any
graphics calls made since the ImagickDraw object was instantiated.

### Return Values

Returns a string containing the vector graphics.

ImagickDraw::line
=================

Draws a line

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::line</span> ( <span
class="methodparam"><span class="type">float</span> `$sx`</span> , <span
class="methodparam"><span class="type">float</span> `$sy`</span> , <span
class="methodparam"><span class="type">float</span> `$ex`</span> , <span
class="methodparam"><span class="type">float</span> `$ey`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a line on the image using the current stroke color, stroke
opacity, and stroke width.

### Parameters

`sx`  
starting x coordinate

`sy`  
starting y coordinate

`ex`  
ending x coordinate

`ey`  
ending y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::line</span>**

``` php
<?php
function line($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->line(125, 70, 100, 50);
    $draw->line(350, 170, 100, 150);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::matte
==================

Paints on the image's opacity channel

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::matte</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> , <span
class="methodparam"><span class="type">int</span> `$paintMethod`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Paints on the image's opacity channel in order to set effected pixels to
transparent, to influence the opacity of pixels.

### Parameters

`x`  
x coordinate of the matte

`y`  
y coordinate of the matte

`paintMethod`  
PAINT\_ constant

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ImagickDraw::matte</span>**

``` php
<?php
function matte($strokeColor, $fillColor, $backgroundColor, $paintType) {
    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->matte(120, 120, $paintType);    
    $draw->rectangle(100, 100, 300, 200);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::pathClose
======================

Adds a path element to the current path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathClose</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Adds a path element to the current path which closes the current subpath
by drawing a straight line from the current point to the current
subpath's most recent starting point (usually, the most recent moveto
point).

### Return Values

No value is returned.

ImagickDraw::pathCurveToAbsolute
================================

Draws a cubic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathCurveToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a cubic Bezier curve from the current point to (x,y) using (x1,y1)
as the control point at the beginning of the curve and (x2,y2) as the
control point at the end of the curve using absolute coordinates. At the
end of the command, the new current point becomes the final (x,y)
coordinate pair used in the polybezier.

### Parameters

`x1`  
x coordinate of the first control point

`y1`  
y coordinate of the first control point

`x2`  
x coordinate of the second control point

`y2`  
y coordinate of the first control point

`x`  
x coordinate of the curve end

`y`  
y coordinate of the curve end

### Return Values

No value is returned.

ImagickDraw::pathCurveToQuadraticBezierAbsolute
===============================================

Draws a quadratic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierAbsolute</span>
( <span class="methodparam"><span class="type">float</span> `$x1`</span>
, <span class="methodparam"><span class="type">float</span> `$y1`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a quadratic Bezier curve from the current point to (x,y) using
(x1,y1) as the control point using absolute coordinates. At the end of
the command, the new current point becomes the final (x,y) coordinate
pair used in the polybezier.

### Parameters

`x1`  
x coordinate of the control point

`y1`  
y coordinate of the control point

`x`  
x coordinate of the end point

`y`  
y coordinate of the end point

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::pathCurveToQuadraticBezierAbsolute</span>**

``` php
<?php
function pathCurveToQuadraticBezierAbsolute($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->pathStart();
    $draw->pathMoveToAbsolute(50,250);

    // This specifies a quadratic bezier curve with the current position as the start
    // point, the control point is the first two params, and the end point is the last two params.
    $draw->pathCurveToQuadraticBezierAbsolute(
        150,50, 
        250,250
    );

    // This specifies a quadratic bezier curve with the current position as the start
    // point, the control point is mirrored from the previous curves control point
    // and the end point is defined by the x, y values.
    $draw->pathCurveToQuadraticBezierSmoothAbsolute(
        450,250
    );

    // This specifies a quadratic bezier curve with the current position as the start
    // point, the control point is mirrored from the previous curves control point
    // and the end point is defined relative from the current position by the x, y values.
    $draw->pathCurveToQuadraticBezierSmoothRelative(
        200,-100
    );

    $draw->pathFinish();

    $imagick = new \Imagick();
    $imagick->newImage(700, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();

}

?>
```

ImagickDraw::pathCurveToQuadraticBezierRelative
===============================================

Draws a quadratic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierRelative</span>
( <span class="methodparam"><span class="type">float</span> `$x1`</span>
, <span class="methodparam"><span class="type">float</span> `$y1`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a quadratic Bezier curve from the current point to (x,y) using
(x1,y1) as the control point using relative coordinates. At the end of
the command, the new current point becomes the final (x,y) coordinate
pair used in the polybezier.

### Parameters

`x1`  
starting x coordinate

`y1`  
starting y coordinate

`x`  
ending x coordinate

`y`  
ending y coordinate

### Return Values

No value is returned.

ImagickDraw::pathCurveToQuadraticBezierSmoothAbsolute
=====================================================

Draws a quadratic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierSmoothAbsolute</span>
( <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

Draws a quadratic Bezier curve (using absolute coordinates) from the
current point to (x,y). The control point is assumed to be the
reflection of the control point on the previous command relative to the
current point. (If there is no previous command or if the previous
command was not a DrawPathCurveToQuadraticBezierAbsolute,
DrawPathCurveToQuadraticBezierRelative,
DrawPathCurveToQuadraticBezierSmoothAbsolut or
DrawPathCurveToQuadraticBezierSmoothRelative, assume the control point
is coincident with the current point.). At the end of the command, the
new current point becomes the final (x,y) coordinate pair used in the
polybezier.

This function cannot be used to continue a cubic Bezier curve smoothly.
It can only continue from a quadratic curve smoothly.

### Parameters

`x`  
ending x coordinate

`y`  
ending y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierSmoothAbsolute</span>**

``` php
<?php
$draw = new \ImagickDraw();

$draw->setStrokeOpacity(1);
$draw->setStrokeColor("black");
$draw->setFillColor("blue");

$draw->setStrokeWidth(2);
$draw->setFontSize(72);

$draw->pathStart();
$draw->pathMoveToAbsolute(50,250);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is the first two params, and the end point is the last two params.
$draw->pathCurveToQuadraticBezierAbsolute(
    150,50, 
    250,250
);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is mirrored from the previous curves control point
// and the end point is defined by the x, y values.
$draw->pathCurveToQuadraticBezierSmoothAbsolute(
    450,250
);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is mirrored from the previous curves control point
// and the end point is defined relative from the current position by the x, y values.
$draw->pathCurveToQuadraticBezierSmoothRelative(
    200,-100
);

$draw->pathFinish();

$imagick = new \Imagick();
$imagick->newImage(700, 500, $backgroundColor);
$imagick->setImageFormat("png");

$imagick->drawImage($draw);

header("Content-Type: image/png");
echo $imagick->getImageBlob();
?>
```

ImagickDraw::pathCurveToQuadraticBezierSmoothRelative
=====================================================

Draws a quadratic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierSmoothRelative</span>
( <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a quadratic Bezier curve (using relative coordinates) from the
current point to (x, y). The control point is assumed to be the
reflection of the control point on the previous command relative to the
current point. (If there is no previous command or if the previous
command was not a DrawPathCurveToQuadraticBezierAbsolute,
DrawPathCurveToQuadraticBezierRelative,
DrawPathCurveToQuadraticBezierSmoothAbsolut or
DrawPathCurveToQuadraticBezierSmoothRelative, assume the control point
is coincident with the current point). At the end of the command, the
new current point becomes the final (x, y) coordinate pair used in the
polybezier.

This function cannot be used to continue a cubic Bezier curve smoothly.
It can only continue from a quadratic curve smoothly.

### Parameters

`x`  
ending x coordinate

`y`  
ending y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="methodname">ImagickDraw::pathCurveToQuadraticBezierSmoothRelative</span>**

``` php
<?php
$draw = new \ImagickDraw();

$draw->setStrokeOpacity(1);
$draw->setStrokeColor("black");
$draw->setFillColor("blue");

$draw->setStrokeWidth(2);
$draw->setFontSize(72);

$draw->pathStart();
$draw->pathMoveToAbsolute(50,250);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is the first two params, and the end point is the last two params.
$draw->pathCurveToQuadraticBezierAbsolute(
    150,50, 
    250,250
);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is mirrored from the previous curves control point
// and the end point is defined by the x, y values.
$draw->pathCurveToQuadraticBezierSmoothAbsolute(
    450,250
);

// This specifies a quadratic bezier curve with the current position as the start
// point, the control point is mirrored from the previous curves control point
// and the end point is defined relative from the current position by the x, y values.
$draw->pathCurveToQuadraticBezierSmoothRelative(
    200,-100
);

$draw->pathFinish();

$imagick = new \Imagick();
$imagick->newImage(700, 500, $backgroundColor);
$imagick->setImageFormat("png");

$imagick->drawImage($draw);

header("Content-Type: image/png");
echo $imagick->getImageBlob();
?>
```

ImagickDraw::pathCurveToRelative
================================

Draws a cubic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathCurveToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a cubic Bezier curve from the current point to (x,y) using (x1,y1)
as the control point at the beginning of the curve and (x2,y2) as the
control point at the end of the curve using relative coordinates. At the
end of the command, the new current point becomes the final (x,y)
coordinate pair used in the polybezier.

### Parameters

`x1`  
x coordinate of starting control point

`y1`  
y coordinate of starting control point

`x2`  
x coordinate of ending control point

`y2`  
y coordinate of ending control point

`x`  
ending x coordinate

`y`  
ending y coordinate

### Return Values

No value is returned.

ImagickDraw::pathCurveToSmoothAbsolute
======================================

Draws a cubic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathCurveToSmoothAbsolute</span> (
<span class="methodparam"><span class="type">float</span> `$x2`</span> ,
<span class="methodparam"><span class="type">float</span> `$y2`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a cubic Bezier curve from the current point to (x,y) using
absolute coordinates. The first control point is assumed to be the
reflection of the second control point on the previous command relative
to the current point. (If there is no previous command or if the
previous command was not an DrawPathCurveToAbsolute,
DrawPathCurveToRelative, DrawPathCurveToSmoothAbsolute or
DrawPathCurveToSmoothRelative, assume the first control point is
coincident with the current point.) (x2,y2) is the second control point
(i.e., the control point at the end of the curve). At the end of the
command, the new current point becomes the final (x,y) coordinate pair
used in the polybezier.

### Parameters

`x2`  
x coordinate of the second control point

`y2`  
y coordinate of the second control point

`x`  
x coordinate of the ending point

`y`  
y coordinate of the ending point

### Return Values

No value is returned.

ImagickDraw::pathCurveToSmoothRelative
======================================

Draws a cubic Bezier curve

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathCurveToSmoothRelative</span> (
<span class="methodparam"><span class="type">float</span> `$x2`</span> ,
<span class="methodparam"><span class="type">float</span> `$y2`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a cubic Bezier curve from the current point to (x,y) using
relative coordinates. The first control point is assumed to be the
reflection of the second control point on the previous command relative
to the current point. (If there is no previous command or if the
previous command was not an DrawPathCurveToAbsolute,
DrawPathCurveToRelative, DrawPathCurveToSmoothAbsolute or
DrawPathCurveToSmoothRelative, assume the first control point is
coincident with the current point.) (x2,y2) is the second control point
(i.e., the control point at the end of the curve). At the end of the
command, the new current point becomes the final (x,y) coordinate pair
used in the polybezier.

### Parameters

`x2`  
x coordinate of the second control point

`y2`  
y coordinate of the second control point

`x`  
x coordinate of the ending point

`y`  
y coordinate of the ending point

### Return Values

No value is returned.

ImagickDraw::pathEllipticArcAbsolute
====================================

Draws an elliptical arc

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathEllipticArcAbsolute</span> (
<span class="methodparam"><span class="type">float</span> `$rx`</span> ,
<span class="methodparam"><span class="type">float</span> `$ry`</span> ,
<span class="methodparam"><span class="type">float</span>
`$x_axis_rotation`</span> , <span class="methodparam"><span
class="type">bool</span> `$large_arc_flag`</span> , <span
class="methodparam"><span class="type">bool</span> `$sweep_flag`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws an elliptical arc from the current point to (x, y) using absolute
coordinates. The size and orientation of the ellipse are defined by two
radii (rx, ry) and an xAxisRotation, which indicates how the ellipse as
a whole is rotated relative to the current coordinate system. The center
(cx, cy) of the ellipse is calculated automatically to satisfy the
constraints imposed by the other parameters. largeArcFlag and sweepFlag
contribute to the automatic calculations and help determine how the arc
is drawn. If largeArcFlag is **`true`** then draw the larger of the
available arcs. If sweepFlag is true, then draw the arc matching a
clock-wise rotation.

### Parameters

`rx`  
x radius

`ry`  
y radius

`x_axis_rotation`  
x axis rotation

`large_arc_flag`  
large arc flag

`sweep_flag`  
sweep flag

`x`  
x coordinate

`y`  
y coordinate

### Return Values

No value is returned.

ImagickDraw::pathEllipticArcRelative
====================================

Draws an elliptical arc

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathEllipticArcRelative</span> (
<span class="methodparam"><span class="type">float</span> `$rx`</span> ,
<span class="methodparam"><span class="type">float</span> `$ry`</span> ,
<span class="methodparam"><span class="type">float</span>
`$x_axis_rotation`</span> , <span class="methodparam"><span
class="type">bool</span> `$large_arc_flag`</span> , <span
class="methodparam"><span class="type">bool</span> `$sweep_flag`</span>
, <span class="methodparam"><span class="type">float</span> `$x`</span>
, <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws an elliptical arc from the current point to (x, y) using relative
coordinates. The size and orientation of the ellipse are defined by two
radii (rx, ry) and an xAxisRotation, which indicates how the ellipse as
a whole is rotated relative to the current coordinate system. The center
(cx, cy) of the ellipse is calculated automatically to satisfy the
constraints imposed by the other parameters. largeArcFlag and sweepFlag
contribute to the automatic calculations and help determine how the arc
is drawn. If largeArcFlag is **`true`** then draw the larger of the
available arcs. If sweepFlag is true, then draw the arc matching a
clock-wise rotation.

### Parameters

`rx`  
x radius

`ry`  
y radius

`x_axis_rotation`  
x axis rotation

`large_arc_flag`  
large arc flag

`sweep_flag`  
sweep flag

`x`  
x coordinate

`y`  
y coordinate

### Return Values

No value is returned.

ImagickDraw::pathFinish
=======================

Terminates the current path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathFinish</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Terminates the current path.

### Return Values

No value is returned.

ImagickDraw::pathLineToAbsolute
===============================

Draws a line path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathLineToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a line path from the current point to the given coordinate using
absolute coordinates. The coordinate then becomes the new current point.

### Parameters

`x`  
starting x coordinate

`y`  
ending x coordinate

### Return Values

No value is returned.

ImagickDraw::pathLineToHorizontalAbsolute
=========================================

Draws a horizontal line path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathLineToHorizontalAbsolute</span> (
<span class="methodparam"><span class="type">float</span> `$x`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a horizontal line path from the current point to the target point
using absolute coordinates. The target point then becomes the new
current point.

### Parameters

`x`  
x coordinate

### Return Values

No value is returned.

ImagickDraw::pathLineToHorizontalRelative
=========================================

Draws a horizontal line

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickDraw::pathLineToHorizontalRelative</span> (
<span class="methodparam"><span class="type">float</span> `$x`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a horizontal line path from the current point to the target point
using relative coordinates. The target point then becomes the new
current point.

### Parameters

`x`  
x coordinate

### Return Values

No value is returned.

ImagickDraw::pathLineToRelative
===============================

Draws a line path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathLineToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a line path from the current point to the given coordinate using
relative coordinates. The coordinate then becomes the new current point.

### Parameters

`x`  
starting x coordinate

`y`  
starting y coordinate

### Return Values

No value is returned.

ImagickDraw::pathLineToVerticalAbsolute
=======================================

Draws a vertical line

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathLineToVerticalAbsolute</span>
( <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a vertical line path from the current point to the target point
using absolute coordinates. The target point then becomes the new
current point.

### Parameters

`y`  
y coordinate

### Return Values

No value is returned.

ImagickDraw::pathLineToVerticalRelative
=======================================

Draws a vertical line path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathLineToVerticalRelative</span>
( <span class="methodparam"><span class="type">float</span> `$y`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a vertical line path from the current point to the target point
using relative coordinates. The target point then becomes the new
current point.

### Parameters

`y`  
y coordinate

### Return Values

No value is returned.

ImagickDraw::pathMoveToAbsolute
===============================

Starts a new sub-path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathMoveToAbsolute</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Starts a new sub-path at the given coordinate using absolute
coordinates. The current point then becomes the specified coordinate.

### Parameters

`x`  
x coordinate of the starting point

`y`  
y coordinate of the starting point

### Return Values

No value is returned.

ImagickDraw::pathMoveToRelative
===============================

Starts a new sub-path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathMoveToRelative</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Starts a new sub-path at the given coordinate using relative
coordinates. The current point then becomes the specified coordinate.

### Parameters

`x`  
target x coordinate

`y`  
target y coordinate

### Return Values

No value is returned.

ImagickDraw::pathStart
======================

Declares the start of a path drawing list

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pathStart</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Declares the start of a path drawing list which is terminated by a
matching DrawPathFinish() command. All other DrawPath commands must be
enclosed between a and a DrawPathFinish() command. This is because path
drawing commands are subordinate commands and they do not function by
themselves.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::pathStart</span>**

``` php
<?php
function pathStart($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    $draw->pathStart();
    $draw->pathMoveToAbsolute(50, 50);
    $draw->pathLineToAbsolute(100, 50);
    $draw->pathLineToRelative(0, 50);
    $draw->pathLineToHorizontalRelative(-50);
    $draw->pathFinish();

    $draw->pathStart();
    $draw->pathMoveToAbsolute(50, 50);
    $draw->pathMoveToRelative(300, 0);
    $draw->pathLineToRelative(50, 0);
    $draw->pathLineToVerticalRelative(50);
    $draw->pathLineToHorizontalAbsolute(350);
    $draw->pathclose();
    $draw->pathFinish();

    $draw->pathStart();
    $draw->pathMoveToAbsolute(50, 300);
    $draw->pathCurveToAbsolute(50, 300, 100, 200, 300, 300);
    $draw->pathLineToVerticalAbsolute(350);
    $draw->pathFinish();

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::point
==================

Draws a point

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::point</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a point using the current stroke color and stroke thickness at the
specified coordinates.

### Parameters

`x`  
point's x coordinate

`y`  
point's y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::point</span>**

``` php
<?php
function point($fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setFillColor($fillColor);

    for ($x = 0; $x < 10000; $x++) {
        $draw->point(rand(0, 500), rand(0, 500));
    }

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::polygon
====================

Draws a polygon

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::polygon</span> ( <span
class="methodparam"><span class="type">array</span>
`$coordinates`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a polygon using the current stroke, stroke width, and fill color
or texture, using the specified array of coordinates.

### Parameters

`coordinates`  
multidimensional array like array( array( 'x' =\> 3, 'y' =\> 4 ), array(
'x' =\> 2, 'y' =\> 6 ) );

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickDraw::polygon</span>**

``` php
<?php
function polygon($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeWidth(4);

    $draw->setFillColor($fillColor);

    $points = [
        ['x' => 40 * 5, 'y' => 10 * 5],
        ['x' => 20 * 5, 'y' => 20 * 5], 
        ['x' => 70 * 5, 'y' => 50 * 5], 
        ['x' => 60 * 5, 'y' => 15 * 5],
    ];

    $draw->polygon($points);

    $image = new \Imagick();
    $image->newImage(500, 300, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::polyline
=====================

Draws a polyline

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::polyline</span> ( <span
class="methodparam"><span class="type">array</span>
`$coordinates`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a polyline using the current stroke, stroke width, and fill color
or texture, using the specified array of coordinates.

### Parameters

`coordinates`  
array of x and y coordinates: array( array( 'x' =\> 4, 'y' =\> 6 ),
array( 'x' =\> 8, 'y' =\> 10 ) )

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickDraw::polyline</span>**

``` php
<?php
function polyline($strokeColor, $fillColor, $backgroundColor) {
    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(5);

    $points = [
        ['x' => 40 * 5, 'y' => 10 * 5],
        ['x' => 20 * 5, 'y' => 20 * 5],
        ['x' => 70 * 5, 'y' => 50 * 5],
        ['x' => 60 * 5, 'y' => 15 * 5]
    ];

    $draw->polyline($points);

    $image = new \Imagick();
    $image->newImage(500, 300, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::pop
================

Destroys the current ImagickDraw in the stack, and returns to the
previously pushed ImagickDraw

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pop</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Destroys the current ImagickDraw in the stack, and returns to the
previously pushed ImagickDraw. Multiple ImagickDraws may exist. It is an
error to attempt to pop more ImagickDraws than have been pushed, and it
is proper form to pop all ImagickDraws which have been pushed.

### Return Values

Returns **`true`** on success and false on failure.

ImagickDraw::popClipPath
========================

Terminates a clip path definition

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::popClipPath</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Terminates a clip path definition.

### Return Values

No value is returned.

ImagickDraw::popDefs
====================

Terminates a definition list

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::popDefs</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Terminates a definition list.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::popDefs</span>**

``` php
<?php
function popDefs($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setstrokeOpacity(1);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);
    $draw->pushDefs();
    $draw->setStrokeColor('white');
    $draw->rectangle(50, 50, 200, 200);
    $draw->popDefs();

    $draw->rectangle(300, 50, 450, 200);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::popPattern
=======================

Terminates a pattern definition

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::popPattern</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Terminates a pattern definition.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ImagickDraw::push
=================

Clones the current ImagickDraw and pushes it to the stack

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::push</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Clones the current ImagickDraw to create a new ImagickDraw, which is
then added to the ImagickDraw stack. The original drawing ImagickDraw(s)
may be returned to by invoking pop(). The ImagickDraws are stored on a
ImagickDraw stack. For every Pop there must have already been an
equivalent Push.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ImagickDraw::push</span>**

``` php
<?php
function push($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillModifiedColor);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);
    $draw->push();
    $draw->translate(50, 50);
    $draw->rectangle(200, 200, 300, 300);
    $draw->pop();
    $draw->setFillColor($fillColor);
    $draw->rectangle(200, 200, 300, 300);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::pushClipPath
=========================

Starts a clip path definition

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pushClipPath</span> ( <span
class="methodparam"><span class="type">string</span>
`$clip_mask_id`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Starts a clip path definition which is comprised of any number of
drawing commands and terminated by a ImagickDraw::popClipPath() command.

### Parameters

`clip_mask_id`  
Clip mask Id

### Return Values

No value is returned.

ImagickDraw::pushDefs
=====================

Indicates that following commands create named elements for early
processing

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pushDefs</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Indicates that commands up to a terminating ImagickDraw::popDefs()
command create named elements (e.g. clip-paths, textures, etc.) which
may safely be processed earlier for the sake of efficiency.

### Return Values

No value is returned.

ImagickDraw::pushPattern
========================

Indicates that subsequent commands up to a ImagickDraw::opPattern()
command comprise the definition of a named pattern

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::pushPattern</span> ( <span
class="methodparam"><span class="type">string</span>
`$pattern_id`</span> , <span class="methodparam"><span
class="type">float</span> `$x`</span> , <span class="methodparam"><span
class="type">float</span> `$y`</span> , <span class="methodparam"><span
class="type">float</span> `$width`</span> , <span
class="methodparam"><span class="type">float</span> `$height`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Indicates that subsequent commands up to a DrawPopPattern() command
comprise the definition of a named pattern. The pattern space is
assigned top left corner coordinates, a width and height, and becomes
its own drawing space. Anything which can be drawn may be used in a
pattern definition. Named patterns may be used as stroke or brush
definitions.

### Parameters

`pattern_id`  
the pattern Id

`x`  
x coordinate of the top-left corner

`y`  
y coordinate of the top-left corner

`width`  
width of the pattern

`height`  
height of the pattern

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ImagickDraw::pushPattern</span>**

``` php
<?php
function pushPattern($strokeColor, $fillColor, $backgroundColor) {
    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(1);

    $draw->pushPattern("MyFirstPattern", 0, 0, 50, 50);
    for ($x = 0; $x < 50; $x += 10) {
        for ($y = 0; $y < 50; $y += 5) {
            $positionX = $x + (($y / 5) % 5);
            $draw->rectangle($positionX, $y, $positionX + 5, $y + 5);
        }
    }
    $draw->popPattern();

    $draw->setFillOpacity(0);
    $draw->rectangle(100, 100, 400, 400);
    $draw->setFillOpacity(1);

    $draw->setFillOpacity(1);

    $draw->push();
    $draw->setFillPatternURL('#MyFirstPattern');
    $draw->setFillColor('yellow');
    $draw->rectangle(100, 100, 400, 400);
    $draw->pop();

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::rectangle
======================

Draws a rectangle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::rectangle</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a rectangle given two coordinates and using the current stroke,
stroke width, and fill settings.

### Parameters

`x1`  
x coordinate of the top left corner

`y1`  
y coordinate of the top left corner

`x2`  
x coordinate of the bottom right corner

`y2`  
y coordinate of the bottom right corner

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::rectangle</span>**

``` php
<?php
function rectangle($strokeColor, $fillColor, $backgroundColor) {
    $draw = new \ImagickDraw();
    $strokeColor = new \ImagickPixel($strokeColor);
    $fillColor = new \ImagickPixel($fillColor);

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);

    $draw->rectangle(200, 200, 300, 300);
    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::render
===================

Renders all preceding drawing commands onto the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::render</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Renders all preceding drawing commands onto the image.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ImagickDraw::resetVectorGraphics
================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::resetVectorGraphics</span> ( <span
class="methodparam">void</span> )

Resets the vector graphics.

### Parameters

This function has no parameters.

### Return Values

Returns **`true`** on success.

ImagickDraw::rotate
===================

Applies the specified rotation to the current coordinate space

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::rotate</span> ( <span
class="methodparam"><span class="type">float</span> `$degrees`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Applies the specified rotation to the current coordinate space.

### Parameters

`degrees`  
degrees to rotate

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::rotate</span>**

``` php
<?php
function rotate($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor) {
    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeOpacity(1);
    $draw->setFillColor($fillColor);
    $draw->rectangle(200, 200, 300, 300);
    $draw->setFillColor($fillModifiedColor);
    $draw->rotate(15);
    $draw->rectangle(200, 200, 300, 300);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::roundRectangle
===========================

Draws a rounded rectangle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::roundRectangle</span> ( <span
class="methodparam"><span class="type">float</span> `$x1`</span> , <span
class="methodparam"><span class="type">float</span> `$y1`</span> , <span
class="methodparam"><span class="type">float</span> `$x2`</span> , <span
class="methodparam"><span class="type">float</span> `$y2`</span> , <span
class="methodparam"><span class="type">float</span> `$rx`</span> , <span
class="methodparam"><span class="type">float</span> `$ry`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Draws a rounded rectangle given two coordinates, x & y corner radiuses
and using the current stroke, stroke width, and fill settings.

### Parameters

`x1`  
x coordinate of the top left corner

`y1`  
y coordinate of the top left corner

`x2`  
x coordinate of the bottom right

`y2`  
y coordinate of the bottom right

`rx`  
x rounding

`ry`  
y rounding

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::roundRectangle</span>**

``` php
<?php
function roundRectangle($strokeColor, $fillColor, $backgroundColor, $startX, $startY, $endX, $endY, $roundX, $roundY) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);

    $draw->roundRectangle($startX, $startY, $endX, $endY, $roundX, $roundY);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::scale
==================

Adjusts the scaling factor

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::scale</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Adjusts the scaling factor to apply in the horizontal and vertical
directions to the current coordinate space.

### Parameters

`x`  
horizontal factor

`y`  
vertical factor

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::scale</span>**

``` php
<?php
function scale($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeWidth(4);
    $draw->setFillColor($fillColor);
    $draw->rectangle(200, 200, 300, 300);
    $draw->setFillColor($fillModifiedColor);
    $draw->scale(1.4, 1.4);
    $draw->rectangle(200, 200, 300, 300);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setClipPath
========================

Associates a named clipping path with the image

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setClipPath</span> ( <span
class="methodparam"><span class="type">string</span> `$clip_mask`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Associates a named clipping path with the image. Only the areas drawn on
by the clipping path will be modified as long as it remains in effect.

### Parameters

`clip_mask`  
the clipping path name

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setClipPath</span>**

``` php
<?php
function setClipPath($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);

    $clipPathName = 'testClipPath';

    $draw->pushClipPath($clipPathName);
    $draw->rectangle(0, 0, 250, 250);
    $draw->popClipPath();
    $draw->setClipPath($clipPathName);
    $draw->rectangle(100, 100, 400, 400);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setClipRule
========================

Set the polygon fill rule to be used by the clipping path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setClipRule</span> ( <span
class="methodparam"><span class="type">int</span> `$fill_rule`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Set the polygon fill rule to be used by the clipping path.

### Parameters

`fill_rule`  
FILLRULE\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setClipRule</span>**

``` php
<?php
function setClipRule($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);
    //\Imagick::FILLRULE_EVENODD
    //\Imagick::FILLRULE_NONZERO

    $clipPathName = 'testClipPath';
    $draw->pushClipPath($clipPathName);
    $draw->setClipRule(\Imagick::FILLRULE_EVENODD);
    $draw->rectangle(0, 0, 300, 500);
    $draw->rectangle(200, 0, 500, 500);
    $draw->popClipPath();
    $draw->setClipPath($clipPathName);
    $draw->rectangle(200, 200, 300, 300);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setClipUnits
=========================

Sets the interpretation of clip path units

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setClipUnits</span> ( <span
class="methodparam"><span class="type">int</span> `$clip_units`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the interpretation of clip path units.

### Parameters

`clip_units`  
the number of clip units

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setClipUnits</span>**

``` php
<?php
function setClipUnits($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);
    $clipPathName = 'testClipPath';
    $draw->setClipUnits(\Imagick::RESOLUTION_PIXELSPERINCH);
    $draw->pushClipPath($clipPathName);
    $draw->rectangle(0, 0, 250, 250);
    $draw->popClipPath();
    $draw->setClipPath($clipPathName);

    //RESOLUTION_PIXELSPERINCH
    //RESOLUTION_PIXELSPERCENTIMETER

    $draw->rectangle(200, 200, 300, 300);
    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFillAlpha
=========================

Sets the opacity to use when drawing using the fill color or fill
texture

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFillAlpha</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the opacity to use when drawing using the fill color or fill
texture. Fully opaque is 1.0.

### Parameters

`opacity`  
fill alpha

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFillAlpha</span>**

``` php
<?php
function setFillAlpha($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);
    $draw->rectangle(100, 200, 200, 300);
    @$draw->setFillAlpha(0.4);
    $draw->rectangle(300, 200, 400, 300);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFillColor
=========================

Sets the fill color to be used for drawing filled objects

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFillColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$fill_pixel`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the fill color to be used for drawing filled objects.

### Parameters

`fill_pixel`  
ImagickPixel to use to set the color

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFillColor</span>**

``` php
<?php
function setFillColor($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(1.5);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->rectangle(50, 50, 150, 150);

    $draw->setFillColor("rgb(200, 32, 32)");
    $draw->rectangle(200, 50, 300, 150);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setFillOpacity
===========================

Sets the opacity to use when drawing using the fill color or fill
texture

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFillOpacity</span> ( <span
class="methodparam"><span class="type">float</span>
`$fillOpacity`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the opacity to use when drawing using the fill color or fill
texture. Fully opaque is 1.0.

### Parameters

`fillOpacity`  
the fill opacity

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setFillOpacity</span>**

``` php
<?php
function setFillOpacity($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeOpacity(1);
    $draw->setStrokeWidth(2);

    $draw->rectangle(100, 200, 200, 300);

    $draw->setFillOpacity(0.4);
    $draw->rectangle(300, 200, 400, 300);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFillPatternURL
==============================

Sets the URL to use as a fill pattern for filling objects

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFillPatternURL</span> ( <span
class="methodparam"><span class="type">string</span> `$fill_url`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the URL to use as a fill pattern for filling objects. Only local
URLs ("\#identifier") are supported at this time. These local URLs are
normally created by defining a named fill pattern with
DrawPushPattern/DrawPopPattern.

### Parameters

`fill_url`  
URL to use to obtain fill pattern.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ImagickDraw::setFillRule
========================

Sets the fill rule to use while drawing polygons

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFillRule</span> ( <span
class="methodparam"><span class="type">int</span> `$fill_rule`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the fill rule to use while drawing polygons.

### Parameters

`fill_rule`  
FILLRULE\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFillRule</span>**

``` php
<?php
function setFillRule($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeWidth(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $fillRules = [\Imagick::FILLRULE_NONZERO, \Imagick::FILLRULE_EVENODD];

    $points = 11;
    $size = 150;

    $draw->translate(175, 160);

    for ($x = 0; $x < 2; $x++) {
        $draw->setFillRule($fillRules[$x]);
        $draw->pathStart();
        for ($n = 0; $n < $points * 2; $n++) {

            if ($n >= $points) {
                $angle = fmod($n * 360 * 4 / $points, 360) * pi() / 180;
            }
            else {
                $angle = fmod($n * 360 * 3 / $points, 360) * pi() / 180;
            }

            $positionX = $size * sin($angle);
            $positionY = $size * cos($angle);

            if ($n == 0) {
                $draw->pathMoveToAbsolute($positionX, $positionY);
            }
            else {
                $draw->pathLineToAbsolute($positionX, $positionY);
            }
        }

        $draw->pathClose();
        $draw->pathFinish();

        $draw->translate(325, 0);
    }

    $image = new \Imagick();
    $image->newImage(700, 320, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setFont
====================

Sets the fully-specified font to use when annotating with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFont</span> ( <span
class="methodparam"><span class="type">string</span> `$font_name`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the fully-specified font to use when annotating with text.

### Parameters

`font_name`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFont</span>**

``` php
<?php
function setFont($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);
    $draw->setFontSize(36);

    $draw->setFont("../fonts/Arial.ttf");
    $draw->annotation(50, 50, "Lorem Ipsum!");

    $draw->setFont("../fonts/Consolas.ttf");
    $draw->annotation(50, 100, "Lorem Ipsum!");

    $draw->setFont("../fonts/CANDY.TTF");
    $draw->annotation(50, 150, "Lorem Ipsum!");

    $draw->setFont("../fonts/Inconsolata-dz.otf");
    $draw->annotation(50, 200, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(500, 300, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFontFamily
==========================

Sets the font family to use when annotating with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFontFamily</span> ( <span
class="methodparam"><span class="type">string</span>
`$font_family`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the font family to use when annotating with text.

### Parameters

`font_family`  
the font family

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFontFamily</span>**

``` php
<?php
function setFontFamily($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $strokeColor = new \ImagickPixel($strokeColor);
    $fillColor = new \ImagickPixel($fillColor);

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(2);

    $draw->setFontSize(48);

    $draw->setFontFamily("Times");
    $draw->annotation(50, 50, "Lorem Ipsum!");

    $draw->setFontFamily("AvantGarde");
    $draw->annotation(50, 100, "Lorem Ipsum!");

    $draw->setFontFamily("NewCenturySchlbk");    
    $draw->annotation(50, 150, "Lorem Ipsum!");

    $draw->setFontFamily("Palatino");
    $draw->annotation(50, 200, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(450, 250, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFontSize
========================

Sets the font pointsize to use when annotating with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFontSize</span> ( <span
class="methodparam"><span class="type">float</span> `$pointsize`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the font pointsize to use when annotating with text.

### Parameters

`pointsize`  
the point size

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFontSize</span>**

``` php
<?php
function setFontSize($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeOpacity(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFont("../fonts/Arial.ttf");

    $sizes = [24, 36, 48, 60, 72];

    foreach ($sizes as $size) {
        $draw->setFontSize($size);
        $draw->annotation(50, ($size * $size / 16), "Lorem Ipsum!");
    }

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFontStretch
===========================

Sets the font stretch to use when annotating with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFontStretch</span> ( <span
class="methodparam"><span class="type">int</span> `$fontStretch`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the font stretch to use when annotating with text. The AnyStretch
enumeration acts as a wild-card "don't care" option.

### Parameters

`fontStretch`  
STRETCH\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setFontStretch</span>**

``` php
<?php
function setFontStretch($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(36);

    $fontStretchTypes = [
        \Imagick::STRETCH_ULTRACONDENSED, 
        \Imagick::STRETCH_CONDENSED, 
        \Imagick::STRETCH_SEMICONDENSED, 
        \Imagick::STRETCH_SEMIEXPANDED, 
        \Imagick::STRETCH_EXPANDED, 
        \Imagick::STRETCH_EXTRAEXPANDED, 
        \Imagick::STRETCH_ULTRAEXPANDED, 
        \Imagick::STRETCH_ANY
    ];

    $offset = 0;
    foreach ($fontStretchTypes as $fontStretch) {
        $draw->setFontStretch($fontStretch);
        $draw->annotation(50, 75 + $offset, "Lorem Ipsum!");
        $offset += 50;
    }

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFontStyle
=========================

Sets the font style to use when annotating with text

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFontStyle</span> ( <span
class="methodparam"><span class="type">int</span> `$style`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the font style to use when annotating with text. The AnyStyle
enumeration acts as a wild-card "don't care" option.

### Parameters

`style`  
STYLETYPE\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setFontStyle</span>**

``` php
<?php
function setFontStyle($fillColor, $strokeColor, $backgroundColor) {
    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setFontSize(36);
    $draw->setFontStyle(\Imagick::STYLE_NORMAL);
    $draw->annotation(50, 50, "Lorem Ipsum!");

    $draw->setFontStyle(\Imagick::STYLE_ITALIC);
    $draw->annotation(50, 100, "Lorem Ipsum!");

    $draw->setFontStyle(\Imagick::STYLE_OBLIQUE);
    $draw->annotation(50, 150, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(350, 300, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setFontWeight
==========================

Sets the font weight

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setFontWeight</span> ( <span
class="methodparam"><span class="type">int</span> `$font_weight`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the font weight to use when annotating with text.

### Parameters

`font_weight`  

### Return Values

### Examples

**Example \#1 <span class="function">ImagickDraw::setFontWeight</span>**

``` php
<?php
function setFontWeight($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(1);

    $draw->setFontSize(36);

    $draw->setFontWeight(100);
    $draw->annotation(50, 50, "Lorem Ipsum!");

    $draw->setFontWeight(200);
    $draw->annotation(50, 100, "Lorem Ipsum!");

    $draw->setFontWeight(400);
    $draw->annotation(50, 150, "Lorem Ipsum!");

    $draw->setFontWeight(800);
    $draw->annotation(50, 200, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setGravity
=======================

Sets the text placement gravity

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setGravity</span> ( <span
class="methodparam"><span class="type">int</span> `$gravity`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the text placement gravity to use when annotating with text.

### Parameters

`gravity`  
GRAVITY\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setGravity</span>**

``` php
<?php
function setGravity($fillColor, $strokeColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setFontSize(24);

    $gravitySettings = array(
        \Imagick::GRAVITY_NORTHWEST => 'NorthWest',
        \Imagick::GRAVITY_NORTH => 'North',
        \Imagick::GRAVITY_NORTHEAST => 'NorthEast',
        \Imagick::GRAVITY_WEST => 'West',
        \Imagick::GRAVITY_CENTER => 'Centre',
        \Imagick::GRAVITY_SOUTHWEST => 'SouthWest',
        \Imagick::GRAVITY_SOUTH => 'South',
        \Imagick::GRAVITY_SOUTHEAST => 'SouthEast',
        \Imagick::GRAVITY_EAST => 'East'
    );

    $draw->setFont("../fonts/Arial.ttf");

    foreach ($gravitySettings as $type => $description) {
        $draw->setGravity($type);
        $draw->annotation(50, 50, '"' . $description . '"');
    }

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setResolution
==========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setResolution</span> ( <span
class="methodparam"><span class="type">float</span>
`$x_resolution`</span> , <span class="methodparam"><span
class="type">float</span> `$y_resolution`</span> )

Sets the resolution.

### Parameters

`x_resolution`  

`y_resolution`  

### Return Values

Returns **`true`** on success.

ImagickDraw::setStrokeAlpha
===========================

Specifies the opacity of stroked object outlines

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeAlpha</span> ( <span
class="methodparam"><span class="type">float</span> `$opacity`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the opacity of stroked object outlines.

### Parameters

`opacity`  
opacity

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeAlpha</span>**

``` php
<?php
function setStrokeAlpha($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(4);
    $draw->line(100, 100, 400, 145);
    $draw->rectangle(100, 200, 225, 350);
    $draw->setStrokeOpacity(0.1);
    $draw->line(100, 120, 400, 165);
    $draw->rectangle(275, 200, 400, 350);

    $image = new \Imagick();
    $image->newImage(500, 400, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeAntialias
===============================

Controls whether stroked outlines are antialiased

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeAntialias</span> ( <span
class="methodparam"><span class="type">bool</span>
`$stroke_antialias`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Controls whether stroked outlines are antialiased. Stroked outlines are
antialiased by default. When antialiasing is disabled stroked pixels are
thresholded to determine if the stroke color or underlying canvas color
should be used.

### Parameters

`stroke_antialias`  
the antialias setting

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeAntialias</span>**

``` php
<?php
function setStrokeAntialias($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setStrokeAntialias(false);
    $draw->line(100, 100, 400, 105);

    $draw->line(100, 140, 400, 185);

    $draw->setStrokeAntialias(true);
    $draw->line(100, 110, 400, 115);
    $draw->line(100, 150, 400, 195);

    $image = new \Imagick();
    $image->newImage(500, 250, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeColor
===========================

Sets the color used for stroking object outlines

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$stroke_pixel`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the color used for stroking object outlines.

### Parameters

`stroke_pixel`  
the stroke color

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeColor</span>**

``` php
<?php
function setStrokeColor($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(5);

    $draw->line(100, 100, 400, 145);
    $draw->rectangle(100, 200, 225, 350);

    $draw->setStrokeOpacity(0.1);
    $draw->line(100, 120, 400, 165);
    $draw->rectangle(275, 200, 400, 350);

    $image = new \Imagick();
    $image->newImage(500, 400, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeDashArray
===============================

Specifies the pattern of dashes and gaps used to stroke paths

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeDashArray</span> ( <span
class="methodparam"><span class="type">array</span> `$dashArray`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the pattern of dashes and gaps used to stroke paths. The
strokeDashArray represents an array of numbers that specify the lengths
of alternating dashes and gaps in pixels. If an odd number of values is
provided, then the list of values is repeated to yield an even number of
values. To remove an existing dash array, pass a zero number\_elements
argument and null dash\_array. A typical strokeDashArray\_ array might
contain the members 5 3 2.

### Parameters

`dashArray`  
array of floats

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeDashArray</span>**

``` php
<?php
function setStrokeDashArray($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(4);

    $draw->setStrokeDashArray([10, 10]);
    $draw->rectangle(100, 50, 225, 175);

    $draw->setStrokeDashArray([20, 5, 20, 5, 5, 5,]);
    $draw->rectangle(275, 50, 400, 175);

    $draw->setStrokeDashArray([20, 5, 20, 5, 5]);
    $draw->rectangle(100, 200, 225, 350);

    $draw->setStrokeDashArray([1, 1, 1, 1, 2, 2, 3, 3, 5, 5, 8, 8, 13, 13, 21, 21, 34, 34, 55, 55, 89, 89, 144, 144, 233, 233, 377, 377, 610, 610, 987, 987, 1597, 1597, 2584, 2584, 4181, 4181,]);

    $draw->rectangle(275, 200, 400, 350);

    $image = new \Imagick();
    $image->newImage(500, 400, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeDashOffset
================================

Specifies the offset into the dash pattern to start the dash

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeDashOffset</span> ( <span
class="methodparam"><span class="type">float</span>
`$dash_offset`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the offset into the dash pattern to start the dash.

### Parameters

`dash_offset`  
dash offset

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeDashOffset</span>**

``` php
<?php
function setStrokeDashOffset($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(4);
    $draw->setStrokeDashArray([20, 20]);
    $draw->setStrokeDashOffset(0);
    $draw->rectangle(100, 50, 225, 175);

    //Start the dash effect halfway through the solid portion
    $draw->setStrokeDashOffset(10);
    $draw->rectangle(275, 50, 400, 175);

    //Start the dash effect on the space portion
    $draw->setStrokeDashOffset(20);
    $draw->rectangle(100, 200, 225, 350);
    $draw->setStrokeDashOffset(5);
    $draw->rectangle(275, 200, 400, 350);

    $image = new \Imagick();
    $image->newImage(500, 400, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeLineCap
=============================

Specifies the shape to be used at the end of open subpaths when they are
stroked

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeLineCap</span> ( <span
class="methodparam"><span class="type">int</span> `$linecap`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the shape to be used at the end of open subpaths when they are
stroked.

### Parameters

`linecap`  
LINECAP\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeLineCap</span>**

``` php
<?php
function setStrokeLineCap($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(25);

    $lineTypes = [\Imagick::LINECAP_BUTT, \Imagick::LINECAP_ROUND, \Imagick::LINECAP_SQUARE,];

    $offset = 0;

    foreach ($lineTypes as $lineType) {
        $draw->setStrokeLineCap($lineType);
        $draw->line(50 + $offset, 50, 50 + $offset, 250);
        $offset += 50;
    }

    $imagick = new \Imagick();
    $imagick->newImage(300, 300, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setStrokeLineJoin
==============================

Specifies the shape to be used at the corners of paths when they are
stroked

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeLineJoin</span> ( <span
class="methodparam"><span class="type">int</span> `$linejoin`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the shape to be used at the corners of paths (or other vector
shapes) when they are stroked.

### Parameters

`linejoin`  
LINEJOIN\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeLineJoin</span>**

``` php
<?php
function setStrokeLineJoin($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeWidth(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);

    $draw->setStrokeWidth(20);

    $offset = 220;

    $lineJoinStyle = [
        \Imagick::LINEJOIN_MITER,
        \Imagick::LINEJOIN_ROUND,
        \Imagick::LINEJOIN_BEVEL,
        ];

    for ($x = 0; $x < count($lineJoinStyle); $x++) {
        $draw->setStrokeLineJoin($lineJoinStyle[$x]);
        $points = [
            ['x' => 40 * 5, 'y' => 10 * 5 + $x * $offset],
            ['x' => 20 * 5, 'y' => 20 * 5 + $x * $offset],
            ['x' => 70 * 5, 'y' => 50 * 5 + $x * $offset],
            ['x' => 40 * 5, 'y' => 10 * 5 + $x * $offset],
        ];

        $draw->polyline($points);
    }

    $image = new \Imagick();
    $image->newImage(500, 700, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeMiterLimit
================================

Specifies the miter limit

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeMiterLimit</span> ( <span
class="methodparam"><span class="type">int</span> `$miterlimit`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the miter limit. When two line segments meet at a sharp angle
and miter joins have been specified for 'lineJoin', it is possible for
the miter to extend far beyond the thickness of the line stroking the
path. The miterLimit' imposes a limit on the ratio of the miter length
to the 'lineWidth'.

### Parameters

`miterlimit`  
the miter limit

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeMiterLimit</span>**

``` php
<?php
function setStrokeMiterLimit($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeOpacity(0.6);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(10);

    $yOffset = 100;

    $draw->setStrokeLineJoin(\Imagick::LINEJOIN_MITER);

    for ($y = 0; $y < 3; $y++) {

        $draw->setStrokeMiterLimit(40 * $y);

        $points = [
            ['x' => 22 * 3, 'y' => 15 * 4 + $y * $yOffset],
            ['x' => 20 * 3, 'y' => 20 * 4 + $y * $yOffset],
            ['x' => 70 * 5, 'y' => 45 * 4 + $y * $yOffset],
        ];

        $draw->polygon($points);
    }

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    $image->setImageType(\Imagick::IMGTYPE_PALETTE);
    $image->setImageCompressionQuality(100);
    $image->stripImage();

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokeOpacity
=============================

Specifies the opacity of stroked object outlines

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeOpacity</span> ( <span
class="methodparam"><span class="type">float</span>
`$stroke_opacity`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the opacity of stroked object outlines.

### Parameters

`stroke_opacity`  
stroke opacity. 1.0 is fully opaque

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeOpacity</span>**

``` php
<?php
function setStrokeOpacity($strokeColor, $fillColor, $backgroundColor) {
    $draw = new \ImagickDraw();

    $draw->setStrokeWidth(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(10);
    $draw->setStrokeOpacity(1);
    $draw->line(100, 80, 400, 125);
    $draw->rectangle(25, 200, 150, 350);
    $draw->setStrokeOpacity(0.5);
    $draw->line(100, 100, 400, 145);
    $draw->rectangle(200, 200, 325, 350);
    $draw->setStrokeOpacity(0.2);
    $draw->line(100, 120, 400, 165);
    $draw->rectangle(375, 200, 500, 350);

    $image = new \Imagick();
    $image->newImage(550, 400, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setStrokePatternURL
================================

Sets the pattern used for stroking object outlines

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokePatternURL</span> ( <span
class="methodparam"><span class="type">string</span>
`$stroke_url`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the pattern used for stroking object outlines.

### Parameters

`stroke_url`  
stroke URL

### Return Values

imagick.imagickdraw.return.success;

ImagickDraw::setStrokeWidth
===========================

Sets the width of the stroke used to draw object outlines

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setStrokeWidth</span> ( <span
class="methodparam"><span class="type">float</span>
`$stroke_width`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the width of the stroke used to draw object outlines.

### Parameters

`stroke_width`  
stroke width

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setStrokeWidth</span>**

``` php
<?php
function setStrokeWidth($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeWidth(1);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->line(100, 100, 400, 145);
    $draw->rectangle(100, 200, 225, 350);
    $draw->setStrokeWidth(5);
    $draw->line(100, 120, 400, 165);
    $draw->rectangle(275, 200, 400, 350);

    $image = new \Imagick();
    $image->newImage(500, 400, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::setTextAlignment
=============================

Specifies a text alignment

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextAlignment</span> ( <span
class="methodparam"><span class="type">int</span> `$alignment`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies a text alignment to be applied when annotating with text.

### Parameters

`alignment`  
ALIGN\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setTextAlignment</span>**

``` php
<?php
function setTextAlignment($strokeColor, $fillColor, $backgroundColor) {
    $draw = new \ImagickDraw();
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setFontSize(36);

    $draw->setTextAlignment(\Imagick::ALIGN_LEFT);
    $draw->annotation(250, 75, "Lorem Ipsum!");
    $draw->setTextAlignment(\Imagick::ALIGN_CENTER);
    $draw->annotation(250, 150, "Lorem Ipsum!");
    $draw->setTextAlignment(\Imagick::ALIGN_RIGHT);
    $draw->annotation(250, 225, "Lorem Ipsum!");
    $draw->line(250, 0, 250, 500);

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setTextAntialias
=============================

Controls whether text is antialiased

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextAntialias</span> ( <span
class="methodparam"><span class="type">bool</span> `$antiAlias`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Controls whether text is antialiased. Text is antialiased by default.

### Parameters

`antiAlias`  

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setTextAntialias</span>**

``` php
<?php
function setTextAntialias($fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();
    $draw->setStrokeColor('none');
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(1);
    $draw->setFontSize(32);
    $draw->setTextAntialias(false);
    $draw->annotation(5, 30, "Lorem Ipsum!");
    $draw->setTextAntialias(true);
    $draw->annotation(5, 65, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(220, 80, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    //Scale the image so that people can see the aliasing.
    $imagick->scaleImage(220 * 6, 80 * 6);
    $imagick->cropImage(640, 480, 0, 0);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setTextDecoration
==============================

Specifies a decoration

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextDecoration</span> ( <span
class="methodparam"><span class="type">int</span> `$decoration`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies a decoration to be applied when annotating with text.

### Parameters

`decoration`  
DECORATION\_ constant

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setTextDecoration</span>**

``` php
<?php
function setTextDecoration($strokeColor, $fillColor, $backgroundColor, $textDecoration) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);
    $draw->setTextDecoration($textDecoration);
    $draw->annotation(50, 75, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(500, 200, $backgroundColor);
    $imagick->setImageFormat("png");
    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setTextEncoding
============================

Specifies the text code set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextEncoding</span> ( <span
class="methodparam"><span class="type">string</span> `$encoding`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the code set to use for text annotations. The only character
encoding which may be specified at this time is "UTF-8" for representing
Unicode as a sequence of bytes. Specify an empty string to set text
encoding to the system's default. Successful text annotation using
Unicode may require fonts designed to support Unicode.

### Parameters

`encoding`  
the encoding name

### Return Values

No value is returned.

ImagickDraw::setTextInterlineSpacing
====================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextInterlineSpacing</span> (
<span class="methodparam"><span class="type">float</span>
`$spacing`</span> )

Sets the text interline spacing.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`spacing`  

### Return Values

Returns **`true`** on success.

ImagickDraw::setTextInterwordSpacing
====================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextInterwordSpacing</span> (
<span class="methodparam"><span class="type">float</span>
`$spacing`</span> )

Sets the text interword spacing.

### Parameters

`spacing`  

### Return Values

Returns **`true`** on success.

ImagickDraw::setTextKerning
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextKerning</span> ( <span
class="methodparam"><span class="type">float</span> `$kerning`</span> )

Sets the text kerning

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`kerning`  

### Return Values

Returns **`true`** on success.

ImagickDraw::setTextUnderColor
==============================

Specifies the color of a background rectangle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setTextUnderColor</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$under_color`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Specifies the color of a background rectangle to place under text
annotations.

### Parameters

`under_color`  
the under color

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setTextUnderColor</span>**

``` php
<?php
function setTextUnderColor($strokeColor, $fillColor, $backgroundColor, $textUnderColor) {
    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);
    $draw->annotation(50, 75, "Lorem Ipsum!");
    $draw->setTextUnderColor($textUnderColor);
    $draw->annotation(50, 175, "Lorem Ipsum!");

    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setVectorGraphics
==============================

Sets the vector graphics

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setVectorGraphics</span> ( <span
class="methodparam"><span class="type">string</span> `$xml`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the vector graphics associated with the specified ImagickDraw
object. Use this method with ImagickDraw::getVectorGraphics() as a
method to persist the vector graphics state.

### Parameters

`xml`  
xml containing the vector graphics

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span
class="function">ImagickDraw::setVectorGraphics</span>**

``` php
<?php
function setVectorGraphics() {
    //Setup a draw object with some drawing in it.
    $draw = new \ImagickDraw();
    $draw->setFillColor("red");
    $draw->circle(20, 20, 50, 50);
    $draw->setFillColor("blue");
    $draw->circle(50, 70, 50, 50);
    $draw->rectangle(50, 120, 80, 150);

    //Get the drawing as a string
    $SVG = $draw->getVectorGraphics();
    
    //$svg is a string, and could be saved anywhere a string can be saved

    //Use the saved drawing to generate a new draw object
    $draw2 = new \ImagickDraw();
    //Apparently the SVG text is missing the root element. 
    $draw2->setVectorGraphics("<root>".$SVG."</root>");

    $imagick = new \Imagick();
    $imagick->newImage(200, 200, 'white');
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw2);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::setViewbox
=======================

Sets the overall canvas size

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::setViewbox</span> ( <span
class="methodparam"><span class="type">int</span> `$x1`</span> , <span
class="methodparam"><span class="type">int</span> `$y1`</span> , <span
class="methodparam"><span class="type">int</span> `$x2`</span> , <span
class="methodparam"><span class="type">int</span> `$y2`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the overall canvas size to be recorded with the drawing vector
data. Usually this will be specified using the same size as the canvas
image. When the vector data is saved to SVG or MVG formats, the viewbox
is use to specify the size of the canvas image that a viewer will render
the vector data on.

### Parameters

`x1`  
left x coordinate

`y1`  
left y coordinate

`x2`  
right x coordinate

`y2`  
right y coordinate

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::setViewBox</span>**

``` php
<?php
function setViewBox($strokeColor, $fillColor, $backgroundColor) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->setStrokeWidth(2);
    $draw->setFontSize(72);

    /*
     
    Sets the overall canvas size to be recorded with the drawing vector data. Usually this will be specified using the same size as the canvas image. When the vector data is saved to SVG or MVG formats, the viewbox is use to specify the size of the canvas image that a viewer will render the vector data on.
    
     */

    $draw->circle(250, 250, 250, 0);
    $draw->setviewbox(0, 0, 200, 200);
    $draw->circle(125, 250, 250, 250);
    $draw->translate(250, 125);
    $draw->circle(0, 0, 125, 0);


    $imagick = new \Imagick();
    $imagick->newImage(500, 500, $backgroundColor);
    $imagick->setImageFormat("png");

    $imagick->drawImage($draw);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickDraw::skewX
==================

Skews the current coordinate system in the horizontal direction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::skewX</span> ( <span
class="methodparam"><span class="type">float</span> `$degrees`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Skews the current coordinate system in the horizontal direction.

### Parameters

`degrees`  
degrees to skew

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::skewX</span>**

``` php
<?php
function skewX($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor, 
               $startX, $startY, $endX, $endY, $skew) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeWidth(2);
    $draw->setFillColor($fillColor);
    $draw->rectangle($startX, $startY, $endX, $endY);
    $draw->setFillColor($fillModifiedColor);
    $draw->skewX($skew);
    $draw->rectangle($startX, $startY, $endX, $endY);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::skewY
==================

Skews the current coordinate system in the vertical direction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::skewY</span> ( <span
class="methodparam"><span class="type">float</span> `$degrees`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Skews the current coordinate system in the vertical direction.

### Parameters

`degrees`  
degrees to skew

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::skewY</span>**

``` php
<?php
function skewY($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor, 
               $startX, $startY, $endX, $endY, $skew) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setStrokeWidth(2);
    $draw->setFillColor($fillColor);
    $draw->rectangle($startX, $startY, $endX, $endY);
    $draw->setFillColor($fillModifiedColor);
    $draw->skewY($skew);
    $draw->rectangle($startX, $startY, $endX, $endY);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");
    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickDraw::translate
======================

Applies a translation to the current coordinate system

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickDraw::translate</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Applies a translation to the current coordinate system which moves the
coordinate system origin to the specified coordinate.

### Parameters

`x`  
horizontal translation

`y`  
vertical translation

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ImagickDraw::translate</span>**

``` php
<?php
function translate($strokeColor, $fillColor, $backgroundColor, $fillModifiedColor, 
                   $startX, $startY, $endX, $endY, $translateX, $translateY) {

    $draw = new \ImagickDraw();

    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->rectangle($startX, $startY, $endX, $endY);

    $draw->setFillColor($fillModifiedColor);
    $draw->translate($translateX, $translateY);
    $draw->rectangle($startX, $startY, $endX, $endY);

    $image = new \Imagick();
    $image->newImage(500, 500, $backgroundColor);
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

Class synopsis
--------------

**ImagickPixel**

<span class="ooclass"> class **ImagickPixel**</span> {

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$color`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getColor</span> (\[ <span
class="methodparam"><span class="type">int</span> `$normalized`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getColorAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getColorCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getColorQuantum</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getColorValue</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">getColorValueQuantum</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getHSL</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getIndex</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPixelSimilar</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPixelSimilarQuantum</span> ( <span
class="methodparam"><span class="type">string</span> `$color`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$fuzz`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isSimilar</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setColor</span> ( <span
class="methodparam"><span class="type">string</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setcolorcount</span> ( <span
class="methodparam"><span class="type">int</span> `$colorCount`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setColorValue</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> ,
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setColorValueQuantum</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> ,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setHSL</span> ( <span class="methodparam"><span
class="type">float</span> `$hue`</span> , <span
class="methodparam"><span class="type">float</span> `$saturation`</span>
, <span class="methodparam"><span class="type">float</span>
`$luminosity`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

}

ImagickPixel::clear
===================

Clears resources associated with this object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::clear</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Clears the ImagickPixel object, leaving it in a fresh state. This also
unsets any color associated with the object.

### Return Values

Returns **`true`** on success.

ImagickPixel::\_\_construct
===========================

The ImagickPixel constructor

### Description

<span class="modifier">public</span> <span
class="methodname">ImagickPixel::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$color`</span> \]
)

**Warning**

This function is currently not documented; only its argument list is
available.

Constructs an ImagickPixel object. If a color is specified, the object
is constructed and then initialised with that color before being
returned.

### Parameters

`color`  
The optional color string to use as the initial value of this object.

### Return Values

Returns an ImagickPixel object on success, throwing
ImagickPixelException on failure.

### Examples

**Example \#1 <span class="function">ImagickPixel::construct</span>**

``` php
<?php
function construct() {

    $columns = 4;
    
    $exampleColors = array(
        "rgba(100%, 0%, 0%, 0.5)",
        "hsb(33.3333%, 100%,  75%)", // medium green
        "hsl(120, 255,   191.25)", //medium green
        "graya(50%, 0.5)", //  semi-transparent mid gray
        "LightCoral", "none", //"cmyk(0.9, 0.48, 0.83, 0.50)",
        "#f00", //  #rgb
        "#ff0000", //  #rrggbb
        "#ff0000ff", //  #rrggbbaa
        "#ffff00000000", //  #rrrrggggbbbb
        "#ffff00000000ffff", //  #rrrrggggbbbbaaaa
        "rgb(255, 0, 0)", //  an integer in the range 0—255 for each component
        "rgb(100.0%, 0.0%, 0.0%)", //  a float in the range 0—100% for each component
        "rgb(255, 0, 0)", //  range 0 - 255
        "rgba(255, 0, 0, 1.0)", //  the same, with an explicit alpha value
        "rgb(100%, 0%, 0%)", //  range 0.0% - 100.0%
        "rgba(100%, 0%, 0%, 1.0)", //  the same, with an explicit alpha value
    );

    $draw = new \ImagickDraw();
    $count = 0;
    $black = new \ImagickPixel('rgb(0, 0, 0)');

    foreach ($exampleColors as $exampleColor) {
        $color = new \ImagickPixel($exampleColor);

        $draw->setstrokewidth(1.0);
        $draw->setStrokeColor($black);
        $draw->setFillColor($color);
        $offsetX = ($count % $columns) * 50 + 5;
        $offsetY = intval($count / $columns) * 50 + 5;
        $draw->rectangle(0 + $offsetX, 0 + $offsetY, 40 + $offsetX, 40 + $offsetY);
        $count++;
    }

    $image = new \Imagick();
    $image->newImage(350, 350, "blue");
    $image->setImageFormat("png");
    $image->drawImage($draw);
    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickPixel::destroy
=====================

Deallocates resources associated with this object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::destroy</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Deallocates any resources used by the ImagickPixel object, and unsets
any associated color. The object should not be used after the destroy
function has been called.

### Return Values

Returns **`true`** on success.

ImagickPixel::getColor
======================

Returns the color

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickPixel::getColor</span> (\[ <span
class="methodparam"><span class="type">int</span> `$normalized`<span
class="initializer"> = 0</span></span> \] )

Returns the color described by the ImagickPixel object, as an array. If
the color has an opacity channel set, this is provided as a fourth value
in the list.

### Parameters

`normalized`  
Normalize the color values. Possible values are *0*, *1* or *2*.

| `normalized` | Description                                                                                                                                                                                 |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`0`**      | The RGB values are returned as <span class="type">int</span>s in the range *0* to *255* (inclusive.) The alpha value is returned as <span class="type">int</span> and is either *0* or *1*. |
| **`1`**      | The RGBA values are returned as <span class="type">float</span>s in the range *0* to *1* (inclusive.)                                                                                       |
| **`2`**      | The RGBA values are returned as <span class="type">int</span>s in the range *0* to *255* (inclusive.)                                                                                       |

### Return Values

An array of channel values. Throws ImagickPixelException on error.

### Examples

**Example \#1 Basic <span class="function">Imagick::getColor</span>
usage**

``` php
<?php

//Create an ImagickPixel with the predefined color 'brown'
$color = new ImagickPixel('brown');

//Set the color to have an alpha of 25%
$color->setColorValue(Imagick::COLOR_ALPHA, 64 / 256.0);

$colorInfo = $color->getColor();

echo "Standard values".PHP_EOL;
print_r($colorInfo);

$colorInfo = $color->getColor(1);

echo "Normalized values:".PHP_EOL;
print_r($colorInfo);

?>
```

The above example will output:

    Standard values
    Array
    (
        [r] => 165
        [g] => 42
        [b] => 42
        [a] => 0
    )
    Normalized values:
    Array
    (
        [r] => 0.64705882352941
        [g] => 0.16470588235294
        [b] => 0.16470588235294
        [a] => 0.25000381475547
    )
        

ImagickPixel::getColorAsString
==============================

Returns the color as a string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ImagickPixel::getColorAsString</span> ( <span
class="methodparam">void</span> )

Returns the color of the ImagickPixel object as a string.

### Parameters

This function has no parameters.

### Return Values

Returns the color of the ImagickPixel object as a string.

### Examples

**Example \#1 Basic <span
class="function">Imagick::getColorAsString</span> usage**

``` php
<?php

//Create an ImagickPixel with the predefined color 'brown'
$color = new ImagickPixel('brown');

$color->setColorValue(Imagick::COLOR_ALPHA, 64 / 256.0);

$colorInfo = $color->getColorAsString();

print_r($colorInfo);
?>
```

The above example will output:

    rgb(165,42,42)

### Notes

> **Note**: **Alpha not returned**  
>
> This function does not return the alpha value of the color in the
> string.

ImagickPixel::getColorCount
===========================

Returns the color count associated with this color

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickPixel::getColorCount</span> ( <span
class="methodparam">void</span> )

Returns the color count associated with this color.

The color count is the number of pixels in the image that have the same
color as this ImagickPixel.

ImagickPixel::getColorCount appears to only work for ImagickPixel
objects created through Imagick::getImageHistogram()

### Return Values

Returns the color count as an integer on success, throws
ImagickPixelException on failure.

### Examples

**Example \#1 ImagickPixel <span class="function">getColorCount</span>**

``` php
<?php
    $imagick = new \Imagick();
    $imagick->newPseudoImage(640, 480, "magick:logo");
    $histogramElements = $imagick->getImageHistogram();
    $lastColor = array_pop($histogramElements);
    echo "Last pixel color count is: ".$lastColor->getColorCount();
?>
```

The output for this will be similar to:

    Last pixel color count is: 256244

ImagickPixel::getColorQuantum
=============================

Description

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickPixel::getColorQuantum</span> ( <span
class="methodparam">void</span> )

Returns the color of the pixel in an array as Quantum values. If
ImageMagick was compiled as HDRI these will be floats, otherwise they
will be integers.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns an array with keys *"r"*, *"g"*, *"b"*, *"a"*.

ImagickPixel::getColorValue
===========================

Gets the normalized value of the provided color channel

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">ImagickPixel::getColorValue</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Retrieves the value of the color channel specified, as a floating-point
number between 0 and 1.

### Parameters

`color`  
The color to get the value of, specified as one of the Imagick color
constants. This can be one of the RGB colors, CMYK colors, alpha and
opacity e.g (Imagick::COLOR\_BLUE, Imagick::COLOR\_MAGENTA).

### Return Values

The value of the channel, as a normalized floating-point number,
throwing ImagickPixelException on error.

### Examples

**Example \#1 Basic <span class="function">Imagick::getColorValue</span>
usage**

``` php
<?php
    
$color = new ImagickPixel('rgba(90%, 20%, 20%, 0.75)');

echo "Alpha value is ".$color->getColorValue(Imagick::COLOR_ALPHA).PHP_EOL;
echo "".PHP_EOL;
echo "Red value is ".$color->getColorValue(Imagick::COLOR_RED).PHP_EOL;
echo "Green value is ".$color->getColorValue(Imagick::COLOR_GREEN).PHP_EOL;
echo "Blue value is ".$color->getColorValue(Imagick::COLOR_BLUE).PHP_EOL;
echo "".PHP_EOL;
echo "Cyan value is ".$color->getColorValue(Imagick::COLOR_CYAN).PHP_EOL;
echo "Magenta value is ".$color->getColorValue(Imagick::COLOR_MAGENTA).PHP_EOL;
echo "Yellow value is ".$color->getColorValue(Imagick::COLOR_YELLOW).PHP_EOL;
echo "Black value is ".$color->getColorValue(Imagick::COLOR_BLACK).PHP_EOL;

?>
```

The above example will output:

    Alpha value is 0.74999618524453

    Red value is 0.90000762951095
    Green value is 0.2
    Blue value is 0.2

    Cyan value is 0.90000762951095
    Magenta value is 0.2
    Yellow value is 0.2
    Black value is 0

ImagickPixel::getColorValueQuantum
==================================

Description

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">ImagickPixel::getColorValueQuantum</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Gets the quantum value of a color in the ImagickPixel. Return value is a
float if ImageMagick was compiled with HDRI, otherwise an integer.

### Parameters

This function has no parameters.

### Return Values

The quantum value of the color element. Float if ImageMagick was
compiled with HDRI, otherwise an int.

### Examples

**Example \#1 <span
class="function">ImagickPixel::getColorValueQuantum</span>**

``` php
<?php
        $color = new \ImagickPixel('rgb(128, 5, 255)');
        $colorRed = $color->getColorValueQuantum(\Imagick::COLOR_RED);
        $colorGreen = $color->getColorValueQuantum(\Imagick::COLOR_GREEN);
        $colorBlue = $color->getColorValueQuantum(\Imagick::COLOR_BLUE);
        $colorAlpha = $color->getColorValueQuantum(\Imagick::COLOR_ALPHA);

        printf(
            "Red: %s Green: %s  Blue %s Alpha: %s",
            $colorRed,
            $colorGreen,
            $colorBlue,
            $colorAlpha
        );

?>
```

ImagickPixel::getHSL
====================

Returns the normalized HSL color of the ImagickPixel object

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickPixel::getHSL</span> ( <span
class="methodparam">void</span> )

Returns the normalized HSL color described by the ImagickPixel object,
with each of the three values as floating point numbers between 0.0 and
1.0.

### Return Values

Returns the HSL value in an array with the keys "hue", "saturation", and
"luminosity". Throws ImagickPixelException on failure.

### Examples

**Example \#1 Basic <span class="function">Imagick::getHSL</span>
example**

``` php
<?php

$color = new ImagickPixel('rgb(90%, 10%, 10%)');

$colorInfo = $color->getHSL();

print_r($colorInfo);

?>
```

The above example will output:

    Array
    (
        [hue] => 0
        [saturation] => 0.80001220740379
        [luminosity] => 0.50000762951095
    )

### Notes

> **Note**:
>
> Available with ImageMagick library version 6.2.9 and higher.

ImagickPixel::getIndex
======================

Description

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickPixel::getIndex</span> ( <span
class="methodparam">void</span> )

Gets the colormap index of the pixel wand.

### Parameters

This function has no parameters.

### Return Values

ImagickPixel::isPixelSimilar
============================

Check the distance between this color and another

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::isPixelSimilar</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

Checks the distance between the color described by this ImagickPixel
object and that of the provided object, by plotting their RGB values on
the color cube. If the distance between the two points is less than the
fuzz value given, the colors are similar. This method replaces
<a href="/class/imagickpixel.html#ImagickPixel::isSimilar" class="link">ImagickPixel::isSimilar()</a>
and correctly normalises the fuzz value to ImageMagick QuantumRange.

### Parameters

`color`  
The ImagickPixel object to compare this object against.

`fuzz`  
The maximum distance within which to consider these colors as similar.
The theoretical maximum for this value is the square root of three
(1.732).

### Return Values

Returns **`true`** on success.

ImagickPixel::isPixelSimilarQuantum
===================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::isPixelSimilarQuantum</span> (
<span class="methodparam"><span class="type">string</span>
`$color`</span> \[, <span class="methodparam"><span
class="type">string</span> `$fuzz`</span> \] )

Returns true if the distance between two colors is less than the
specified distance. The fuzz value should be in the range
0-QuantumRange. The maximum value represents the longest possible
distance in the colorspace. e.g. from RGB(0, 0, 0) to RGB(255, 255, 255)
for the RGB colorspace

### Parameters

`color`  

`fuzz`  

### Return Values

ImagickPixel::isSimilar
=======================

Check the distance between this color and another

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::isSimilar</span> ( <span
class="methodparam"><span class="type">ImagickPixel</span>
`$color`</span> , <span class="methodparam"><span
class="type">float</span> `$fuzz`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Checks the distance between the color described by this ImagickPixel
object and that of the provided object, by plotting their RGB values on
the color cube. If the distance between the two points is less than the
fuzz value given, the colors are similar. Deprecated in favour of
<a href="/class/imagickpixel.html#ImagickPixel::isPixelSimilar" class="link">ImagickPixel::isPixelSimilar()</a>.

### Parameters

`color`  
The ImagickPixel object to compare this object against.

`fuzz`  
The maximum distance within which to consider these colors as similar.
The theoretical maximum for this value is the square root of three
(1.732).

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span class="function">ImagickPixel::isSimilar</span>**

``` php
<?php
        // The tests below are written with the maximum distance expressed as 255
        // so we need to scale them by the square root of 3 - the diagonal length
        // of a unit cube.
        $root3 = 1.732050807568877;

        $tests = array(
            ['rgb(245, 0, 0)',      'rgb(255, 0, 0)',   9 / $root3,         false,],
            ['rgb(245, 0, 0)',      'rgb(255, 0, 0)',  10 / $root3,         true,],
            ['rgb(0, 0, 0)',        'rgb(7, 7, 0)',     9 / $root3,         false,],
            ['rgb(0, 0, 0)',        'rgb(7, 7, 0)',    10 / $root3,         true,],
            ['rgba(0, 0, 0, 1)',    'rgba(7, 7, 0, 1)', 9 / $root3,         false,],
            ['rgba(0, 0, 0, 1)',    'rgba(7, 7, 0, 1)',    10 / $root3,     true,],
            ['rgb(128, 128, 128)',  'rgb(128, 128, 120)',   7 / $root3,     false,],
            ['rgb(128, 128, 128)',  'rgb(128, 128, 120)',   8 / $root3,     true,],
            ['rgb(0, 0, 0)',        'rgb(255, 255, 255)',   254.9,          false,],
            ['rgb(0, 0, 0)',        'rgb(255, 255, 255)',   255,            true,],
            ['rgb(255, 0, 0)',      'rgb(0, 255, 255)',     254.9,          false,],
            ['rgb(255, 0, 0)',      'rgb(0, 255, 255)',     255,            true,],
            ['black',               'rgba(0, 0, 0)',        0.0,            true],
            ['black',               'rgba(10, 0, 0, 1.0)',  10.0 / $root3,  true],);

        $output = "<table width='100%' class='infoTable'><thead>
                <tr>
                <th>
                Color 1
                </th>
                <th>
                Color 2
                </th>
                <th>
                    Test distance * 255
                </th>
                <th>
                    Is within distance
                </th>
                </tr>
        </thead>";

        $output .= "<tbody>";

        foreach ($tests as $testInfo) {
            $color1 = $testInfo[0];
            $color2 = $testInfo[1];
            $distance = $testInfo[2];
            $expectation = $testInfo[3];
            $testDistance = ($distance / 255.0);

            $color1Pixel = new \ImagickPixel($color1);
            $color2Pixel = new \ImagickPixel($color2);

            $isSimilar = $color1Pixel->isPixelSimilar($color2Pixel, $testDistance);


            if ($isSimilar !== $expectation) {
                echo "Test distance failed. Color [$color1] compared to color [$color2] is not within distance $testDistance FAILED.".NL;
            }

            $layout = "<tr>
                <td>%s</td>
                <td>%s</td>
                <td>%s</td>
                <td style='text-align: center;'>%s</td>
            </tr>";
            
            $output .= sprintf(
                $layout,
                $color1,
                $color2,
                $distance,
                $isSimilar ? 'yes' : 'no'
            );
        }

        $output .= "</tbody></table>";
        
        return $output;

?>
```

ImagickPixel::setColor
======================

Sets the color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setColor</span> ( <span
class="methodparam"><span class="type">string</span> `$color`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the color described by the ImagickPixel object, with a string (e.g.
"blue", "\#0000ff", "rgb(0,0,255)", "cmyk(100,100,100,10)", etc.).

### Parameters

`color`  
The color definition to use in order to initialise the ImagickPixel
object.

### Return Values

Returns **`true`** if the specified color was set, **`false`**
otherwise.

### Examples

**Example \#1 <span class="function">ImagickPixel::setColor</span>**

``` php
<?php
function setColor() {
    $draw = new \ImagickDraw();

    $strokeColor = new \ImagickPixel('green');
    $fillColor = new \ImagickPixel();
    $fillColor->setColor('rgba(100%, 75%, 0%, 1.0)');

    $draw->setstrokewidth(3.0);
    $draw->setStrokeColor($strokeColor);
    $draw->setFillColor($fillColor);
    $draw->rectangle(200, 200, 300, 300);

    $image = new \Imagick();
    $image->newImage(500, 500, "SteelBlue2");
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickPixel::setColorCount
===========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setcolorcount</span> ( <span
class="methodparam"><span class="type">int</span> `$colorCount`</span> )

Sets the color count associated with this color.

### Parameters

`colorCount`  

### Return Values

Returns **`true`** on success.

ImagickPixel::setColorValue
===========================

Sets the normalized value of one of the channels

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setColorValue</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> ,
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

Sets the value of the specified channel of this object to the provided
value, which should be between 0 and 1. This function can be used to
provide an opacity channel to an ImagickPixel object.

### Parameters

`color`  
One of the Imagick color constants e.g. \\Imagick::COLOR\_GREEN or
\\Imagick::COLOR\_ALPHA.

`value`  
The value to set this channel to, ranging from 0 to 1.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Basic <span class="function">Imagick::setColorValue</span>
usage**

``` php
<?php

$color  = new \ImagickPixel('firebrick');

$color->setColorValue(Imagick::COLOR_ALPHA, 0.5);

print_r($color->getcolor(true));
?>
```

The above example will output:

    Array
    (
        [r] => 0.69803921568627
        [g] => 0.13333333333333
        [b] => 0.13333333333333
        [a] => 0.50000762951095
    )

ImagickPixel::setColorValueQuantum
==================================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setColorValueQuantum</span> (
<span class="methodparam"><span class="type">int</span> `$color`</span>
, <span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$value`</span> )

Sets the quantum value of a color element of the ImagickPixel.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`color`  
Which color element to set e.g. \\Imagick::COLOR\_GREEN.

`value`  
The quantum value to set the color element to. This should be a float if
ImageMagick was compiled with HDRI otherwise an int in the range 0 to
Imagick::getQuantum().

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickPixel::setColorValueQuantum</span>**

``` php
<?php
function setColorValueQuantum() {
    $image = new \Imagick();

    $quantumRange = $image->getQuantumRange();

    $draw = new \ImagickDraw();
    $color = new \ImagickPixel('blue');
    $color->setcolorValueQuantum(\Imagick::COLOR_RED, 128 * $quantumRange['quantumRangeLong'] / 256);

    $draw->setstrokewidth(1.0);
    $draw->setStrokeColor($color);
    $draw->setFillColor($color);
    $draw->rectangle(200, 200, 300, 300);

    $image->newImage(500, 500, "SteelBlue2");
    $image->setImageFormat("png");

    $image->drawImage($draw);

    header("Content-Type: image/png");
    echo $image->getImageBlob();
}

?>
```

ImagickPixel::setHSL
====================

Sets the normalized HSL color

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setHSL</span> ( <span
class="methodparam"><span class="type">float</span> `$hue`</span> ,
<span class="methodparam"><span class="type">float</span>
`$saturation`</span> , <span class="methodparam"><span
class="type">float</span> `$luminosity`</span> )

Sets the color described by the ImagickPixel object using normalized
values for hue, saturation and luminosity.

### Parameters

`hue`  
The normalized value for hue, described as a fractional arc (between 0
and 1) of the hue circle, where the zero value is red.

`saturation`  
The normalized value for saturation, with 1 as full saturation.

`luminosity`  
The normalized value for luminosity, on a scale from black at 0 to white
at 1, with the full HS value at 0.5 luminosity.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 Use <span class="function">ImagickPixel::setHSL</span> to
modify a color**

``` php
<?php

//Create an almost pure red color
$color = new ImagickPixel('rgb(90%, 10%, 10%)');

//Get it's HSL values
$colorInfo = $color->getHSL();

//Rotate the hue by 180 degrees
$newHue = $colorInfo['hue'] + 0.5;
if ($newHue > 1) {
    $newHue = $newHue - 1;
}

//Set the ImagickPixel to the new color
$colorInfo = $color->setHSL($newHue, $colorInfo['saturation'], $colorInfo['luminosity']);

//Check that the new color is blue/green
$colorInfo = $color->getcolor();
print_r($colorInfo);

?>
```

The above example will output:

    Array
    (
        [r] => 26
        [g] => 230
        [b] => 230
        [a] => 255
    )

### Notes

> **Note**:
>
> Available with ImageMagick library version 6.2.9 and higher.

ImagickPixel::setIndex
======================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixel::setIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Sets the colormap index of the pixel wand.

### Parameters

`index`  

### Return Values

Returns **`true`** on success.

Class synopsis
--------------

**ImagickPixelIterator**

<span class="ooclass"> class **ImagickPixelIterator**</span> {

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$wand`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getCurrentIteratorRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getIteratorRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getNextIteratorRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getPreviousIteratorRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">newPixelIterator</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$wand`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">newPixelRegionIterator</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$wand`</span> ,
<span class="methodparam"><span class="type">int</span> `$x`</span> ,
<span class="methodparam"><span class="type">int</span> `$y`</span> ,
<span class="methodparam"><span class="type">int</span>
`$columns`</span> , <span class="methodparam"><span
class="type">int</span> `$rows`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resetIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIteratorFirstRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIteratorLastRow</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIteratorRow</span> ( <span
class="methodparam"><span class="type">int</span> `$row`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">syncIterator</span> ( <span
class="methodparam">void</span> )

}

ImagickPixelIterator::clear
===========================

Clear resources associated with a PixelIterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::clear</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Clear resources associated with a PixelIterator.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickPixelIterator::clear</span>**

``` php
<?php
function clear($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));

    $imageIterator = $imagick->getPixelRegionIterator(100, 100, 250, 200);

    /* Loop through pixel rows */
    foreach ($imageIterator as $pixels) { 
        /** @var $pixel \ImagickPixel */
        /* Loop through the pixels in the row (columns) */
        foreach ($pixels as $column => $pixel) { 
            if ($column % 2) {
                /* Paint every second pixel black*/
                $pixel->setColor("rgba(0, 0, 0, 0)"); 
            }
        }
        /* Sync the iterator, this is important to do on each iteration */
        $imageIterator->syncIterator();
    }

    $imageIterator->clear();

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

ImagickPixelIterator::\_\_construct
===================================

The ImagickPixelIterator constructor

### Description

<span class="modifier">public</span> <span
class="methodname">ImagickPixelIterator::\_\_construct</span> ( <span
class="methodparam"><span class="type">Imagick</span> `$wand`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

The ImagickPixelIterator constructor

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickPixelIterator::construct</span>**

``` php
<?php
function construct($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imageIterator = new \ImagickPixelIterator($imagick);

    /* Loop through pixel rows */
    foreach ($imageIterator as $pixels) { 
        /* Loop through the pixels in the row (columns) */
        foreach ($pixels as $column => $pixel) { 
            /** @var $pixel \ImagickPixel */
            if ($column % 2) {
                /* Paint every second pixel black*/
                $pixel->setColor("rgba(0, 0, 0, 0)");
            }
        }
        /* Sync the iterator, this is important to do on each iteration */
        $imageIterator->syncIterator();
    }

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

ImagickPixelIterator::destroy
=============================

Deallocates resources associated with a PixelIterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::destroy</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Deallocates resources associated with a PixelIterator.

### Return Values

Returns **`true`** on success.

ImagickPixelIterator::getCurrentIteratorRow
===========================================

Returns the current row of ImagickPixel objects

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ImagickPixelIterator::getCurrentIteratorRow</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the current row as an array of ImagickPixel objects from the
pixel iterator.

### Return Values

Returns a row as an array of ImagickPixel objects that can themselves be
iterated.

ImagickPixelIterator::getIteratorRow
====================================

Returns the current pixel iterator row

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ImagickPixelIterator::getIteratorRow</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the current pixel iterator row.

### Return Values

Returns the integer offset of the row, throwing
ImagickPixelIteratorException on error.

ImagickPixelIterator::getNextIteratorRow
========================================

Returns the next row of the pixel iterator

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickPixelIterator::getNextIteratorRow</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the next row as an array of pixel wands from the pixel iterator.

### Return Values

Returns the next row as an array of ImagickPixel objects, throwing
ImagickPixelIteratorException on error.

### Examples

**Example \#1 <span
class="function">ImagickPixelIterator::getNextIteratorRow</span>**

``` php
<?php
function getNextIteratorRow($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imageIterator = $imagick->getPixelIterator();

    $count = 0;
    while ($pixels = $imageIterator->getNextIteratorRow()) {
        if (($count % 3) == 0) {
            /* Loop through the pixels in the row (columns) */
            foreach ($pixels as $column => $pixel) { 
                /** @var $pixel \ImagickPixel */
                if ($column % 2) {
                    /* Paint every second pixel black*/
                    $pixel->setColor("rgba(0, 0, 0, 0)");
                }
            }
            /* Sync the iterator, this is important to do on each iteration */
            $imageIterator->syncIterator(); 
        }

        $count += 1;
    }

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

ImagickPixelIterator::getPreviousIteratorRow
============================================

Returns the previous row

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span
class="methodname">ImagickPixelIterator::getPreviousIteratorRow</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns the previous row as an array of pixel wands from the pixel
iterator.

### Return Values

Returns the previous row as an array of ImagickPixelWand objects from
the ImagickPixelIterator, throwing ImagickPixelIteratorException on
error.

ImagickPixelIterator::newPixelIterator
======================================

Returns a new pixel iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::newPixelIterator</span> (
<span class="methodparam"><span class="type">Imagick</span>
`$wand`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns a new pixel iterator.

### Return Values

Returns **`true`** on success. Throwing ImagickPixelIteratorException.

ImagickPixelIterator::newPixelRegionIterator
============================================

Returns a new pixel iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickPixelIterator::newPixelRegionIterator</span> (
<span class="methodparam"><span class="type">Imagick</span>
`$wand`</span> , <span class="methodparam"><span class="type">int</span>
`$x`</span> , <span class="methodparam"><span class="type">int</span>
`$y`</span> , <span class="methodparam"><span class="type">int</span>
`$columns`</span> , <span class="methodparam"><span
class="type">int</span> `$rows`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Returns a new pixel iterator.

### Parameters

`wand`  

`x`  

`y`  

`columns`  

`rows`  

### Return Values

Returns a new ImagickPixelIterator on success; on failure, throws
ImagickPixelIteratorException.

ImagickPixelIterator::resetIterator
===================================

Resets the pixel iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::resetIterator</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Resets the pixel iterator. Use it in conjunction with
ImagickPixelIterator::getNextIteratorRow() to iterate over all the
pixels in a pixel container.

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickPixelIterator::resetIterator</span>**

``` php
<?php
function resetIterator($imagePath) {

    $imagick = new \Imagick(realpath($imagePath));

    $imageIterator = $imagick->getPixelIterator();

    /* Loop trough pixel rows */
    foreach ($imageIterator as $pixels) {
        /* Loop through the pixels in the row (columns) */
        foreach ($pixels as $column => $pixel) {
            /** @var $pixel \ImagickPixel */
            if ($column % 2) {

                /* Make every second pixel 25% red*/
                $pixel->setColorValue(\Imagick::COLOR_RED, 64); 
            }
        }
        /* Sync the iterator, this is important to do on each iteration */
        $imageIterator->syncIterator();
    }

    $imageIterator->resetiterator();

    /* Loop trough pixel rows */
    foreach ($imageIterator as $pixels) {
        /* Loop through the pixels in the row (columns) */
        foreach ($pixels as $column => $pixel) {
            /** @var $pixel \ImagickPixel */
            if ($column % 3) {
                $pixel->setColorValue(\Imagick::COLOR_BLUE, 64); /* Make every second pixel a little blue*/
                //$pixel->setColor("rgba(0, 0, 128, 0)"); /* Paint every second pixel black*/
            }
        }
        $imageIterator->syncIterator(); /* Sync the iterator, this is important to do on each iteration */
    }

    $imageIterator->clear();

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

ImagickPixelIterator::setIteratorFirstRow
=========================================

Sets the pixel iterator to the first pixel row

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span
class="methodname">ImagickPixelIterator::setIteratorFirstRow</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the pixel iterator to the first pixel row.

### Return Values

Returns **`true`** on success.

ImagickPixelIterator::setIteratorLastRow
========================================

Sets the pixel iterator to the last pixel row

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::setIteratorLastRow</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Sets the pixel iterator to the last pixel row.

### Return Values

Returns **`true`** on success.

ImagickPixelIterator::setIteratorRow
====================================

Set the pixel iterator row

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::setIteratorRow</span> (
<span class="methodparam"><span class="type">int</span> `$row`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Set the pixel iterator row.

### Parameters

`row`  

### Return Values

Returns **`true`** on success.

### Examples

**Example \#1 <span
class="function">ImagickPixelIterator::setIteratorRow</span>**

``` php
<?php
function setIteratorRow($imagePath) {
    $imagick = new \Imagick(realpath($imagePath));
    $imageIterator = $imagick->getPixelRegionIterator(200, 100, 200, 200);

    for ($x = 0; $x < 20; $x++) {        
        $imageIterator->setIteratorRow($x * 5);
        $pixels = $imageIterator->getCurrentIteratorRow();
        /* Loop through the pixels in the row (columns) */
        foreach ($pixels as $pixel) {
            /** @var $pixel \ImagickPixel */
            /* Paint every second pixel black*/
            $pixel->setColor("rgba(0, 0, 0, 0)"); 
        }

        /* Sync the iterator, this is important to do on each iteration */
        $imageIterator->syncIterator();
    }

    header("Content-Type: image/jpg");
    echo $imagick;
}

?>
```

ImagickPixelIterator::syncIterator
==================================

Syncs the pixel iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ImagickPixelIterator::syncIterator</span> (
<span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

Syncs the pixel iterator.

### Return Values

Returns **`true`** on success.

Introduction
------------

Class synopsis
--------------

**ImagickKernel**

<span class="ooclass"> class **ImagickKernel** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addKernel</span> ( <span
class="methodparam"><span class="type">ImagickKernel</span>
`$ImagickKernel`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addUnityKernel</span> ( <span
class="methodparam"><span class="type">float</span> `$scale`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">ImagickKernel</span>
<span class="methodname">fromBuiltin</span> ( <span
class="methodparam"><span class="type">int</span> `$kernelType`</span> ,
<span class="methodparam"><span class="type">string</span>
`$kernelString`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">ImagickKernel</span>
<span class="methodname">fromMatrix</span> ( <span
class="methodparam"><span class="type">array</span> `$matrix`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$origin`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getMatrix</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">scale</span> ( <span class="methodparam"><span
class="type">float</span> `$scale`</span> \[, <span
class="methodparam"><span class="type">int</span>
`$normalizeFlag`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">separate</span> ( <span
class="methodparam">void</span> )

}

ImagickKernel::addKernel
========================

Description

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ImagickKernel::addKernel</span> ( <span
class="methodparam"><span class="type">ImagickKernel</span>
`$ImagickKernel`</span> )

Attach another kernel to this kernel to allow them to both be applied in
a single morphology or filter function. Returns the new combined kernel.

### Parameters

`ImagickKernel`  

### Return Values

### Examples

**Example \#1 <span class="function">ImagickKernel::addKernel</span>**

``` php
<?php
function addKernel($imagePath) {
    $matrix1 = [
        [-1, -1, -1],
        [ 0,  0,  0],
        [ 1,  1,  1],
    ];

    $matrix2 = [
        [-1,  0,  1],
        [-1,  0,  1],
        [-1,  0,  1],
    ];

    $kernel1 = ImagickKernel::fromMatrix($matrix1);
    $kernel2 = ImagickKernel::fromMatrix($matrix2);
    $kernel1->addKernel($kernel2);

    $imagick = new \Imagick(realpath($imagePath));
    $imagick->filter($kernel1);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();

}

?>
```

ImagickKernel::addUnityKernel
=============================

Description

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ImagickKernel::addUnityKernel</span> ( <span
class="methodparam"><span class="type">float</span> `$scale`</span> )

Adds a given amount of the 'Unity' Convolution Kernel to the given
pre-scaled and normalized Kernel. This in effect adds that amount of the
original image into the resulting convolution kernel. The resulting
effect is to convert the defined kernels into blended soft-blurs,
unsharp kernels or into sharpening kernels.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span
class="function">ImagickKernel::addUnityKernel</span>**

``` php
<?php



    function renderKernelTable($matrix) {
        $output = "<table class='infoTable'>";
    
        foreach ($matrix as $row) {
            $output .= "<tr>";
            foreach ($row as $cell) {
                $output .= "<td style='text-align:left'>";
                if ($cell === false) {
                    $output .= "false";
                }
                else {
                    $output .= round($cell, 3);
                }
                $output .= "</td>";
            }
            $output .= "</tr>";
        }
    
        $output .= "</table>";
    
        return $output;
    }

    $matrix = [
        [-1, 0, -1],
        [ 0, 4,  0],
        [-1, 0, -1],
    ];

    $kernel = \ImagickKernel::fromMatrix($matrix);
    $kernel->scale(1, \Imagick::NORMALIZE_KERNEL_VALUE);
    $output = "Before adding unity kernel: <br/>";
    $output .= renderKernelTable($kernel->getMatrix());
    $kernel->addUnityKernel(0.5);
    $output .= "After adding unity kernel: <br/>";
    $output .= renderKernelTable($kernel->getMatrix());
    
    
    $kernel->scale(1, \Imagick::NORMALIZE_KERNEL_VALUE);
    $output .= "After renormalizing kernel: <br/>";
    $output .= renderKernelTable($kernel->getMatrix());

    echo $output;

?>
```

**Example \#2 <span
class="function">ImagickKernel::addUnityKernel</span>**

``` php
<?php
function addUnityKernel($imagePath) {

    $matrix = [
        [-1, 0, -1],
        [ 0, 4,  0],
        [-1, 0, -1],
    ];

    $kernel = ImagickKernel::fromMatrix($matrix);

    $kernel->scale(4, \Imagick::NORMALIZE_KERNEL_VALUE);
    $kernel->addUnityKernel(0.5);


    $imagick = new \Imagick(realpath($imagePath));
    $imagick->filter($kernel);
    header("Content-Type: image/jpg");
    echo $imagick->getImageBlob();

}

?>
```

ImagickKernel::fromBuiltIn
==========================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">ImagickKernel</span>
<span class="methodname">ImagickKernel::fromBuiltin</span> ( <span
class="methodparam"><span class="type">int</span> `$kernelType`</span> ,
<span class="methodparam"><span class="type">string</span>
`$kernelString`</span> )

Create a kernel from a builtin in kernel. See
http://www.imagemagick.org/Usage/morphology/\#kernel for examples.
Currently the 'rotation' symbols are not supported. Example:
$diamondKernel = ImagickKernel::fromBuiltIn(\\Imagick::KERNEL\_DIAMOND,
"2");

### Parameters

`kerneltype`  
The type of kernel to build e.g. \\Imagick::KERNEL\_DIAMOND

`kernelString`  
A string that describes the parameters e.g. "4,2.5"

### Return Values

### Examples

**Example \#1 <span class="function">ImagickKernel::fromBuiltin</span>**

``` php
<?php


function renderKernel(ImagickKernel $imagickKernel) {
    $matrix = $imagickKernel->getMatrix();
    
    $imageMargin = 20;
    
    $tileSize = 20;
    $tileSpace = 4;
    $shadowSigma = 4;
    $shadowDropX = 20;
    $shadowDropY = 0;

    $radius = ($tileSize / 2) * 0.9;
    
    $rows = count($matrix);
    $columns = count($matrix[0]);
 
    $imagickDraw = new \ImagickDraw();

    $imagickDraw->setFillColor('#afafaf');
    $imagickDraw->setStrokeColor('none');
    
    $imagickDraw->translate($imageMargin, $imageMargin);
    $imagickDraw->push();

    ksort($matrix);
    
    foreach ($matrix as $row) {
        ksort($row);
        $imagickDraw->push();
        foreach ($row as $cell) {
            if ($cell !== false) {
                $color = intval(255 * $cell);
                $colorString = sprintf("rgb(%f, %f, %f)", $color, $color, $color);
                $imagickDraw->setFillColor($colorString);
                $imagickDraw->rectangle(0, 0, $tileSize, $tileSize);
            }
            $imagickDraw->translate(($tileSize + $tileSpace), 0);
        }
        $imagickDraw->pop();
        $imagickDraw->translate(0, ($tileSize + $tileSpace));
    }

    $imagickDraw->pop();

    $width = ($columns * $tileSize) + (($columns - 1) * $tileSpace);
    $height = ($rows * $tileSize) + (($rows - 1) * $tileSpace);

    $imagickDraw->push();
    $imagickDraw->translate($width/2 , $height/2);
    $imagickDraw->setFillColor('rgba(0, 0, 0, 0)');
    $imagickDraw->setStrokeColor('white');
    $imagickDraw->circle(0, 0, $radius - 1, 0);
    $imagickDraw->setStrokeColor('black');
    $imagickDraw->circle(0, 0, $radius, 0);
    $imagickDraw->pop();

    $canvasWidth = $width + (2 * $imageMargin); 
    $canvasHeight = $height + (2 * $imageMargin);

    $kernel = new \Imagick();
    $kernel->newPseudoImage(
        $canvasWidth,
        $canvasHeight,
        'canvas:none'
    );

    $kernel->setImageFormat('png');
    $kernel->drawImage($imagickDraw);
 
    /* create drop shadow on it's own layer */
    $canvas = $kernel->clone();
    $canvas->setImageBackgroundColor(new \ImagickPixel('rgb(0, 0, 0)'));
    $canvas->shadowImage(100, $shadowSigma, $shadowDropX, $shadowDropY);

    $canvas->setImagePage($canvasWidth, $canvasHeight, -5, -5);
    $canvas->cropImage($canvasWidth, $canvasHeight, 0, 0);
    
    /* composite original text_layer onto shadow_layer */
    $canvas->compositeImage($kernel, \Imagick::COMPOSITE_OVER, 0, 0);
    $canvas->setImageFormat('png');

    return $canvas;
}


function createFromBuiltin($kernelType, $kernelFirstTerm, $kernelSecondTerm, $kernelThirdTerm) {
    $string = '';

    if ($kernelFirstTerm != false && strlen(trim($kernelFirstTerm)) != 0) {
        $string .= $kernelFirstTerm;

        if ($kernelSecondTerm != false && strlen(trim($kernelSecondTerm)) != 0) {
            $string .= ','.$kernelSecondTerm;
            if ($kernelThirdTerm != false && strlen(trim($kernelThirdTerm)) != 0) {
                $string .= ','.$kernelThirdTerm;
            }
        }
    }

    $kernel = ImagickKernel::fromBuiltIn(
        $kernelType,
        $string
    );

    return $kernel;
}
    
function fromBuiltin($kernelType, $kernelFirstTerm, $kernelSecondTerm, $kernelThirdTerm) {
    $diamondKernel = createFromBuiltin($kernelType, $kernelFirstTerm, $kernelSecondTerm, $kernelThirdTerm);
    $imagick = renderKernel($diamondKernel);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

fromBuiltin(\Imagick::KERNEL_DIAMOND, 2, false, false);


?>
```

ImagickKernel::fromMatrix
=========================

Description

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">ImagickKernel</span>
<span class="methodname">ImagickKernel::fromMatrix</span> ( <span
class="methodparam"><span class="type">array</span> `$matrix`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$origin`</span> \] )

Create a kernel from an 2d matrix of values. Each value should either be
a float (if the element should be used) or 'false' if the element should
be skipped. For matrices that are odd sizes in both dimensions the
origin pixel will default to the centre of the kernel. For all other
kernel sizes the origin pixel must be specified.

### Parameters

`array`  
A matrix (i.e. 2d array) of values that define the kernel. Each element
should be either a float value, or FALSE if that element shouldn't be
used by the kernel.

`array`  
Which element of the kernel should be used as the origin pixel. e.g. For
a 3x3 matrix specifying the origin as \[2, 2\] would specify that the
bottom right element should be the origin pixel.

### Return Values

The generated ImagickKernel.

### Examples

**Example \#1 <span class="function">ImagickKernel::fromMatrix</span>**

``` php
<?php

function renderKernel(ImagickKernel $imagickKernel) {
    $matrix = $imagickKernel->getMatrix();
    
    $imageMargin = 20;
    
    $tileSize = 20;
    $tileSpace = 4;
    $shadowSigma = 4;
    $shadowDropX = 20;
    $shadowDropY = 0;

    $radius = ($tileSize / 2) * 0.9;
    
    $rows = count($matrix);
    $columns = count($matrix[0]);
 
    $imagickDraw = new \ImagickDraw();

    $imagickDraw->setFillColor('#afafaf');
    $imagickDraw->setStrokeColor('none');
    
    $imagickDraw->translate($imageMargin, $imageMargin);
    $imagickDraw->push();

    ksort($matrix);
    
    foreach ($matrix as $row) {
        ksort($row);
        $imagickDraw->push();
        foreach ($row as $cell) {
            if ($cell !== false) {
                $color = intval(255 * $cell);
                $colorString = sprintf("rgb(%f, %f, %f)", $color, $color, $color);
                $imagickDraw->setFillColor($colorString);
                $imagickDraw->rectangle(0, 0, $tileSize, $tileSize);
            }
            $imagickDraw->translate(($tileSize + $tileSpace), 0);
        }
        $imagickDraw->pop();
        $imagickDraw->translate(0, ($tileSize + $tileSpace));
    }

    $imagickDraw->pop();

    $width = ($columns * $tileSize) + (($columns - 1) * $tileSpace);
    $height = ($rows * $tileSize) + (($rows - 1) * $tileSpace);

    $imagickDraw->push();
    $imagickDraw->translate($width/2 , $height/2);
    $imagickDraw->setFillColor('rgba(0, 0, 0, 0)');
    $imagickDraw->setStrokeColor('white');
    $imagickDraw->circle(0, 0, $radius - 1, 0);
    $imagickDraw->setStrokeColor('black');
    $imagickDraw->circle(0, 0, $radius, 0);
    $imagickDraw->pop();

    $canvasWidth = $width + (2 * $imageMargin); 
    $canvasHeight = $height + (2 * $imageMargin);

    $kernel = new \Imagick();
    $kernel->newPseudoImage(
        $canvasWidth,
        $canvasHeight,
        'canvas:none'
    );

    $kernel->setImageFormat('png');
    $kernel->drawImage($imagickDraw);
 
    /* create drop shadow on it's own layer */
    $canvas = $kernel->clone();
    $canvas->setImageBackgroundColor(new \ImagickPixel('rgb(0, 0, 0)'));
    $canvas->shadowImage(100, $shadowSigma, $shadowDropX, $shadowDropY);

    $canvas->setImagePage($canvasWidth, $canvasHeight, -5, -5);
    $canvas->cropImage($canvasWidth, $canvasHeight, 0, 0);
    
    /* composite original text_layer onto shadow_layer */
    $canvas->compositeImage($kernel, \Imagick::COMPOSITE_OVER, 0, 0);
    $canvas->setImageFormat('png');

    return $canvas;
}

function createFromMatrix() {
    $matrix = [
        [0.5, 0, 0.2],
        [0, 1, 0],
        [0.9, 0, false],
    ];

    $kernel = \ImagickKernel::fromMatrix($matrix);

    return $kernel;
}
    
function fromMatrix() {
    $kernel = createFromMatrix();
    $imagick = renderKernel($kernel);

    header("Content-Type: image/png");
    echo $imagick->getImageBlob();
}

?>
```

ImagickKernel::getMatrix
========================

Description

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickKernel::getMatrix</span> ( <span
class="methodparam">void</span> )

Get the 2d matrix of values used in this kernel. The elements are either
float for elements that are used or 'false' if the element should be
skipped.

### Parameters

This function has no parameters.

### Return Values

A matrix (2d array) of the values that represent the kernel.

### Examples

**Example \#1 <span class="function">ImagickKernel::getMatrix</span>**

``` php
<?php


function renderKernelTable($matrix) {
    $output = "<table class='infoTable'>";

    foreach ($matrix as $row) {
        $output .= "<tr>";
        foreach ($row as $cell) {
            $output .= "<td style='text-align:left'>";
            if ($cell === false) {
                $output .= "false";
            }
            else {
                $output .= round($cell, 3);
            }
            $output .= "</td>";
        }
        $output .= "</tr>";
    }

    $output .= "</table>";

    return $output;
}

    $output = "The built-in kernel name 'ring' with parameters of '2,3.5':<br/>";
    $kernel = \ImagickKernel::fromBuiltIn(
        \Imagick::KERNEL_RING,
        "2,3.5"
    );
    $matrix = $kernel->getMatrix();
    $output .= renderKernelTable($matrix);

    echo $output;

?>
```

ImagickKernel::scale
====================

Description

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ImagickKernel::scale</span> ( <span
class="methodparam"><span class="type">float</span> `$scale`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$normalizeFlag`</span> \] )

ScaleKernelInfo() scales the given kernel list by the given amount, with
or without normalization of the sum of the kernel values (as per given
flags). The exact behaviour of this function depends on the
normalization type being used please see
http://www.imagemagick.org/api/morphology.php\#ScaleKernelInfo for
details. Flag should be one of Imagick::NORMALIZE\_KERNEL\_VALUE,
Imagick::NORMALIZE\_KERNEL\_CORRELATE,
Imagick::NORMALIZE\_KERNEL\_PERCENT or not set.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span class="function">ImagickKernel::scale</span>**

``` php
<?php


    function renderKernelTable($matrix) {
        $output = "<table class='infoTable'>";
    
        foreach ($matrix as $row) {
            $output .= "<tr>";
            foreach ($row as $cell) {
                $output .= "<td style='text-align:left'>";
                if ($cell === false) {
                    $output .= "false";
                }
                else {
                    $output .= round($cell, 3);
                }
                $output .= "</td>";
            }
            $output .= "</tr>";
        }
    
        $output .= "</table>";
    
        return $output;
    }


    $output = "";
    
    $matrix = [
        [-1, 0, -1],
        [ 0, 4,  0],
        [-1, 0, -1],
    ];

    $kernel = \ImagickKernel::fromMatrix($matrix);
    $kernelClone = clone $kernel;

    $output .= "Start kernel<br/>";
    $output .= renderKernelTable($kernel->getMatrix());
    
    
    $output .= "Scaling with NORMALIZE_KERNEL_VALUE. The  <br/>";
    $kernel->scale(2, \Imagick::NORMALIZE_KERNEL_VALUE);
    $output .= renderKernelTable($kernel->getMatrix());


    $kernel = clone $kernelClone;
    $output .= "Scaling by percent<br/>";
    $kernel->scale(2, \Imagick::NORMALIZE_KERNEL_PERCENT);
    $output .= renderKernelTable($kernel->getMatrix());
    
    $matrix2 = [
        [-1, -1, 1],
        [ -1, false,  1],
        [1, 1, 1],
    ];
    
    $kernel = \ImagickKernel::fromMatrix($matrix2);
    $output .= "Scaling by correlate<br/>";
    $kernel->scale(1, \Imagick::NORMALIZE_KERNEL_CORRELATE);
    $output .= renderKernelTable($kernel->getMatrix());

    return $output; 
?>
```

ImagickKernel::separate
=======================

Description

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ImagickKernel::separate</span> ( <span
class="methodparam">void</span> )

Separates a linked set of kernels and returns an array of
ImagickKernels.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span class="function">ImagickKernel::separate</span>**

``` php
<?php


    
    function renderKernelTable($matrix) {

        $output = "<table class='infoTable'>";
        foreach ($matrix as $row) {
            $output .= "<tr>";
            foreach ($row as $cell) {
                $output .= "<td style='text-align:left'>";
                if ($cell === false) {
                    $output .= "false";
                }
                else {
                    $output .= round($cell, 3);
                }
                $output .= "</td>";
            }
            $output .= "</tr>";
        }
    
        $output .= "</table>";
    
        return $output;
    }


    $matrix = [
        [-1, 0, -1],
        [ 0, 4,  0],
        [-1, 0, -1],
    ];

    $kernel = \ImagickKernel::fromMatrix($matrix);
    $kernel->scale(4, \Imagick::NORMALIZE_KERNEL_VALUE);
    $diamondKernel = \ImagickKernel::fromBuiltIn(
        \Imagick::KERNEL_DIAMOND,
        "2"
    );

    $kernel->addKernel($diamondKernel);
    
    $kernelList = $kernel->separate();
    
    $output = '';
    $count = 0;
    foreach ($kernelList as $kernel) {
        $output .= "<br/>Kernel $count<br/>";
        $output .= renderKernelTable($kernel->getMatrix());
        $count++;
    }

    return $output;

?>
```
