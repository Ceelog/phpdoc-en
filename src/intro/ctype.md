The functions provided by this extension check whether a character or
string falls into a certain character class according to the current
locale (see also <span class="function">setlocale</span>).

When called with an integer argument these functions behave exactly like
their C counterparts from `ctype.h`. It means that if you pass an
integer smaller than 256 it will use the ASCII value of it to see if it
fits in the specified range (digits are in 0x30-0x39). If the number is
between -128 and -1 inclusive then 256 will be added and the check will
be done on that.

When called with a string argument they will check every character in
the string and will only return **`TRUE`** if every character in the
string matches the requested criteria. When called with an empty string
the result will always be **`TRUE`** in PHP \< 5.1 and **`FALSE`** since
5.1.

Passing anything else but a string or integer will return **`FALSE`**
immediately.

It should be noted that ctype functions are always preferred over
regular expressions, and even to some equivalent *"str\_\*"* and
*"is\_\*"* functions. This is because of the fact that ctype uses a
native C library and thus processes significantly faster.

> **Note**:
>
> These functions are not related to the Python "ctypes" library at all.
> The extension name stems from the `ctype.h` C header file that their C
> equivalents are defined in.
>
> This extension also predates Python "ctypes" so any confusion caused
> by this naming is hardly our fault ...
