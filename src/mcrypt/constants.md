Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

Mcrypt can operate in four block cipher modes (*CBC*, *OFB*, *CFB*, and
*ECB*). If linked against libmcrypt-2.4.x or higher the functions can
also operate in the block cipher mode *nOFB* and in *STREAM* mode. Below
you find a list with all supported encryption modes together with the
constants that are defined for the encryption mode. For a more complete
reference and discussion see Applied Cryptography by Schneier (ISBN
0-471-11709-9).

-   <span class="simpara"> **`MCRYPT_MODE_ECB`** (*electronic codebook*)
    is a block cipher mode that is generally unsuitable for most
    purposes. The use of this mode is not recommended. </span>
-   <span class="simpara"> **`MCRYPT_MODE_CBC`** (*cipher block
    chaining*) is a block cipher mode that is significantly more secure
    than *ECB* mode. </span>
-   <span class="simpara"> **`MCRYPT_MODE_CFB`** (*cipher feedback, in
    8-bit mode*) is a stream cipher mode. It is recommended to use
    *NCFB* mode rather than *CFB* mode. </span>
-   <span class="simpara"> **`MCRYPT_MODE_OFB`** (*output feedback, in
    8-bit mode*) is a stream cipher mode comparable to *CFB*, but can be
    used in applications where error propagation cannot be tolerated. It
    is recommended to use *NOFB* mode rather than *OFB* mode. </span>
-   <span class="simpara"> **`MCRYPT_MODE_NOFB`** (*output feedback, in
    n-bit mode*) is comparable to *OFB* mode, but operates on the full
    block size of the algorithm. </span>
-   <span class="simpara"> **`MCRYPT_MODE_STREAM`** is an extra mode to
    include some stream algorithms like *"WAKE"* or *"RC4"*. </span>

Mcrypt supports some other modes of operation for which there are no
predefined constants. They can be utilised by passing a string in place
of the missing constants.

-   <span class="simpara"> **`"ctr"`** (*counter mode*) is a stream
    cipher mode. </span>
-   <span class="simpara"> **`"ncfb"`** (*cipher feedback, in n-bit
    mode*) is comparable to *CFB* mode, but operates on the full block
    size of the algorithm. </span>

Some other mode and random device constants:

**`MCRYPT_ENCRYPT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MCRYPT_DECRYPT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MCRYPT_DEV_RANDOM`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MCRYPT_DEV_URANDOM`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MCRYPT_RAND`** (<span class="type">integer</span>)  
<span class="simpara"> </span>
