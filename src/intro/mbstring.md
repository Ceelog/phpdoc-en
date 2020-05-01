While there are many languages in which every necessary character can be
represented by a one-to-one mapping to an 8-bit value, there are also
several languages which require so many characters for written
communication that they cannot be contained within the range a mere byte
can code (A byte is made up of eight bits. Each bit can contain only two
distinct values, one or zero. Because of this, a byte can only represent
256 unique values (two to the power of eight)). Multibyte character
encoding schemes were developed to express more than 256 characters in
the regular bytewise coding system.

When you manipulate (trim, split, splice, etc.) strings encoded in a
multibyte encoding, you need to use special functions since two or more
consecutive bytes may represent a single character in such encoding
schemes. Otherwise, if you apply a non-multibyte-aware string function
to the string, it probably fails to detect the beginning or ending of
the multibyte character and ends up with a corrupted garbage string that
most likely loses its original meaning.

*mbstring* provides multibyte specific string functions that help you
deal with multibyte encodings in PHP. In addition to that, *mbstring*
handles character encoding conversion between the possible encoding
pairs. *mbstring* is designed to handle Unicode-based encodings such as
UTF-8 and UCS-2 and many single-byte encodings for convenience (listed
below).
