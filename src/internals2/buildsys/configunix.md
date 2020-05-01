Talking to the UNIX build system: config.m4
-------------------------------------------

The `config.m4` file for an extension tells the UNIX build system what
`configure` options your extension supports, what external libraries and
includes you require, and what source files are to be compiled as part
of it. A reference to all the commonly used autoconf macros, both
PHP-specific and those built into autoconf, is given in the
<a href="/internals2/apiref.html" class="xref">Zend Engine 2 API reference</a>
section.

**Tip**

The version of **autoconf** you have installed makes a difference when
developing an extension. For PHP 5.3 and earlier, you will have the best
results with **autoconf** version 2.13 but versions up to and including
2.59 will work. For PHP 5.4 and later the oldest **autoconf** version
you can use is 2.59 and you will have better results with later
versions.

**Example \#1 An example config.m4 file**

``` autoconf
dnl $Id$
dnl config.m4 for extension example
```

``` autoconf
PHP_ARG_WITH(example, for example support,
[  --with-example[=FILE]       Include example support. File is the optional path to example-config])
PHP_ARG_ENABLE(example-debug, whether to enable debugging support in example,
[  --enable-example-debug        example: Enable debugging support in example], no, no)
PHP_ARG_WITH(example-extra, for extra libraries for example,
[  --with-example-extra=DIR      example: Location of extra libraries for example], no, no)

dnl Check whether the extension is enabled at all
if test "$PHP_EXAMPLE" != "no"; then
  
  dnl Check for example-config. First try any path that was given to us, then look in $PATH
  AC_MSG_CHECKING([for example-config])
  EXAMPLE_CONFIG="example-config"
  if test "$PHP_EXAMPLE" != "yes"; then
    EXAMPLE_PATH=$PHP_EXAMPLE
  else
    EXAMPLE_PATH=`$php_shtool path $EXAMPLE_CONFIG`
  fi
  
  dnl If a usable example-config was found, use it
  if test -f "$EXAMPLE_PATH" && test -x "$EXAMPLE_PATH" && $EXAMPLE_PATH --version > /dev/null 2>&1; then
    AC_MSG_RESULT([$EXAMPLE_PATH])
    EXAMPLE_LIB_NAME=`$EXAMPLE_PATH --libname`
    EXAMPLE_INCDIRS=`$EXAMPLE_PATH --incdirs`
    EXAMPLE_LIBS=`$EXAMPLE_PATH --libs`
    
    dnl Check that the library works properly
    PHP_CHECK_LIBRARY($EXAMPLE_LIB_NAME, example_critical_function,
    [
      dnl Add the necessary include dirs
      PHP_EVAL_INCLINE($EXAMPLE_INCDIRS)
      dnl Add the necessary libraries and library dirs
      PHP_EVAL_LIBLINE($EXAMPLE_LIBS, EXAMPLE_SHARED_LIBADD)
    ],[
      dnl Bail out
      AC_MSG_ERROR([example library not found. Check config.log for more information.])
    ],[$EXAMPLE_LIBS]
    )
  else
    dnl No usable example-config, bail  
    AC_MSG_RESULT([not found])
    AC_MSG_ERROR([Please check your example installation.])
  fi
  
  dnl Check whether to enable debugging
  if test "$PHP_EXAMPLE_DEBUG" != "no"; then
    dnl Yes, so set the C macro
    AC_DEFINE(USE_EXAMPLE_DEBUG,1,[Include debugging support in example])
  fi
  
  dnl Check for the extra support
  if test "$PHP_EXAMPLE_EXTRA" != "no"; then
    if test "$PHP_EXAMPLE_EXTRA" == "yes"; then
      AC_MSG_ERROR([You must specify a path when using --with-example-extra])
    fi
    
    PHP_CHECK_LIBRARY(example-extra, example_critical_extra_function,
    [
      dnl Add the neccessary paths
      PHP_ADD_INCLUDE($PHP_EXAMPLE_EXTRA/include)
      PHP_ADD_LIBRARY_WITH_PATH(example-extra, $PHP_EXAMPLE_EXTRA/lib, EXAMPLE_SHARED_LIBADD)
      AC_DEFINE(HAVE_EXAMPLEEXTRALIB,1,[Whether example-extra support is present and requested])
      EXAMPLE_SOURCES="$EXAMPLE_SOURCES example_extra.c"
    ],[
      AC_MSG_ERROR([example-extra lib not found. See config.log for more information.])
    ],[-L$PHP_EXAMPLE_EXTRA/lib]
    )
  fi
  
  dnl Finally, tell the build system about the extension and what files are needed
  PHP_NEW_EXTENSION(example, example.c $EXAMPLE_SOURCES, $ext_shared)
  PHP_SUBST(EXAMPLE_SHARED_LIBADD)
fi
```

### A short introduction to autoconf syntax

`config.m4` files are written using the GNU **autoconf** syntax. It can
be described in a nutshell as shell scripting augmented by a powerful
macro language. Comments are delimited by the string *dnl*, and strings
are quoted using left and right brackets (e.g. *\[* and *\]*). Quoting
of strings can be nested as many times as needed. A full reference to
the syntax can be found in the **autoconf** manual at
<a href="http://www.gnu.org/software/autoconf/manual/" class="link external">» http://www.gnu.org/software/autoconf/manual/</a>.

### PHP\_ARG\_\*: Giving users the option

The very first thing seen in the example `config.m4` above, aside from a
couple of comments, are three lines using <span
class="function">PHP\_ARG\_WITH</span> and <span
class="function">PHP\_ARG\_ENABLE</span>. These provide **configure**
with the options and help text seen when running **./configure --help**.
As the names suggest, the difference between the two is whether they
create a **--with-\*** option or an **--enable-\*** option. Every
extension should provide at least one or the other with the extension
name, so that users can choose whether or not to build the extension
into PHP. By convention, <span class="function">PHP\_ARG\_WITH</span> is
used for an option which takes a parameter, such as the location of a
library or program required by an extension, while <span
class="function">PHP\_ARG\_ENABLE</span> is used for an option which
represents a simple flag.

**Example \#2 Sample configure output**

    $ ./configure --help
    ...
      --with-example[=FILE]       Include example support. FILE is the optional path to example-config
      --enable-example-debug        example: Enable debugging support in example
      --with-example-extra=DIR      example: Location of extra libraries for example
    ...

    $ ./configure --with-example=/some/library/path/example-config --disable-example-debug --with-example-extra=/another/library/path
    ...
    checking for example support... yes
    checking whether to enable debugging support in example... no
    checking for extra libraries for example... /another/library/path
    ...

> **Note**:
>
> Regardless of the order in which options are specified on the command
> line when **configure** is called, the checks will be run in the order
> they are specified in `config.m4`.

### Processing the user's choices

Now that `config.m4` can provide the user with some choices of what to
do, it's time to act upon those choices. In the example above, the
obvious default for all three options, if any of them are unspecified,
is "no". As a matter of convention, it is best to use this as the
default for the option which enables the extension, as it will be
overridden by **phpize** for extensions built separately, and should not
clutter the extension space by default when being built into PHP. The
code to process the three options is by far the most complicated.

#### Handling the --with-example\[=FILE\] option

The first check made of the **--with-example\[=FILE\]** option is
whether it was set at all. As this option controls the inclusion of the
entire extension, if it was unspecified, given in the negative form
(**--without-example**), or given the value "no", nothing else is done
at all. In the example above, it is specified with the value
*/some/library/path/example-config*, so the first test succeeds.

Next, the code calls <span class="function">AC\_MSG\_CHECKING</span>, an
**autoconf** macro which outputs a standard "checking for something"
line, and checks whether the user gave an explicit path to the fictional
**example-config**. In this example, *PHP\_EXAMPLE* got the value
*/some/library/path/example-config*, which is now copied into the
EXAMPLE\_PATH variable. Had the user specified only **--with-example**,
the code would have executed **$php\_shtool path $EXAMPLE\_CONFIG**,
which would try to guess the location of **example-config** using the
user's current `PATH`. Either way, the next step is to check whether the
chosen *EXAMPLE\_PATH* is a regular file, is executable, and can be run
successfully. If so, <span class="function">AC\_MSG\_RESULT</span> is
called, which completes the output line started by <span
class="function">AC\_MSG\_CHECKING</span>. Otherwise, <span
class="function">AC\_MSG\_ERROR</span> is called, which prints the given
message and halts **configure** immediately.

The code now determines some site-specific configuration information by
running **example-config** several times. The next call is to <span
class="function">PHP\_CHECK\_LIBRARY</span>, a macro provided by the PHP
buildsystem as a wrapper around **autoconf**'s <span
class="function">AC\_CHECK\_LIB</span>. <span
class="function">PHP\_CHECK\_LIBRARY</span> attempts to compile, link,
and run a program which calls the symbol specified by the second
parameter in the library specified by the first, using the string given
in the fifth as extra linker options. If the attempt succeeds, the
script given in the third parameter is run. This script tells the PHP
buildsystem to extract include paths, library paths, and library names
from the raw option strings **example-config** provided. If the attempt
fails, the script in the fourth parameter is run instead. In this case,
<span class="function">AC\_MSG\_ERROR</span> is called to stop
processing.

#### Handling the --enable-example-debug option

Processing the **--enable-example-debug** is much simpler. A simple
check for its truth value is performed. If that check succeeds, <span
class="function">AC\_DEFINE</span> is called to make the C macro
*USE\_EXAMPLE\_DEBUG* available to the source of the extension. The
third parameter is a comment string for `config.h`; it is safe to leave
this empty, and often is.

#### Handling the --with-example-extra=DIR option

For the sake of this example, the fictional "extra" functionality
requested by the **--with-example-extra=DIR** option does not share the
fictional **example-config** program, nor does it have any default paths
to search. Therefore, the user is required to provide the installation
prefix of the necessary library. This setup is somewhat unlikely in a
real-world extension, but is considered illustrative.

The code begins in a now-familiar way by checking the truth value of
*PHP\_EXAMPLE\_EXTRA*. If a negative form was provided, no further
processing is done; the user did not request extra functionality. If a
positive form was provided without a parameter, <span
class="function">AC\_MSG\_ERROR</span> is called to halt processing. The
next step is another invocation of <span
class="function">PHP\_CHECK\_LIBRARY</span>. This time, since there is
no set of predefined compiler options provided, <span
class="function">PHP\_ADD\_INCLUDE</span> and <span
class="function">PHP\_ADD\_LIBRARY\_WITH\_PATH</span> are used to
construct the necessary include paths, library paths, and library flags
for the extra functionality. <span class="function">AC\_DEFINE</span> is
also called to indicate to the code that the extra functionality was
both requested and available, and a variable is set to tell later code
that there are extra source files to build. If the check fails, the
familiar <span class="function">AC\_MSG\_ERROR</span> is called. A
different way to handle the failure would have been to call <span
class="function">AC\_MSG\_WARNING</span> instead, e.g.:

``` autoconf
AC_MSG_WARNING([example-extra lib not found. example will be built without extra functionality.])
```

In this case, **configure** would print a warning message rather than an
error, and continue processing. Which way such failures are handled is a
design decision left to the extension developer.

### Telling the buildsystem what was decided

With all the necessary includes and libraries specified, with all the
options processed and macros defined, one more thing remains to be done:
The build system must be told to build the extension itself, and which
files are to be used for that. To do this, the <span
class="function">PHP\_NEW\_EXTENSION</span> macro is called. The first
parameter is the name of the extension, which is the same as the name of
the directory containing it. The second parameter is the list of all
source files which are part of the extension. See <span
class="function">PHP\_ADD\_BUILD\_DIR</span> for information about
adding source files in subdirectories to the build process. The third
parameter should always be *$ext\_shared*, a value which was determined
by **configure** when <span class="function">PHP\_ARG\_WITH</span> was
called for **--with-example\[=FILE\]**. The fourth parameter specifies a
"SAPI class", and is only useful for extensions which require the CGI or
CLI SAPIs specifically. It should be left empty in all other cases. The
fifth parameter specifies a list of flags to be added to *CFLAGS* while
building the extension; the sixth is a boolean value which, if "yes",
will force the entire extension to be built using *$CXX* instead of
*$CC*. All parameters after the third are optional. Finally, <span
class="function">PHP\_SUBST</span> is called to enable shared builds of
the extension. See
<a href="/internals2/faq.html" class="xref">Extension FAQs</a> for more
information on disabling support for building an extension in shared
mode.

### The counter extension's config.m4 file

The counter extension previously documented has a much simpler
`config.m4` file than that described above, as it doesn't make use of
many buildsystem features. This is a preferred method of operation for
any extension that doesn't use an external or bundled library.

**Example \#3 counter's config.m4 file**

``` autoconf
dnl
```

``` autoconf
$
```

``` autoconf
Id$
dnl config.m4 for extension counter

PHP_ARG_ENABLE(counter, for counter support,
[  --enable-counter            Include counter support])

dnl Check whether the extension is enabled at all
if test "$PHP_COUNTER" != "no"; then
  dnl Finally, tell the build system about the extension and what files are needed
  PHP_NEW_EXTENSION(counter, counter.c counter_util.c, $ext_shared)
  PHP_SUBST(COUNTER_SHARED_LIBADD)
fi
```
