The ext\_skel script
--------------------

A PHP extension is composed of several files common to all extensions.
As the details of many of those files are similar from extension to
extension, it can be laborious to duplicate the content for each one.
Fortunately, there is a script which can do all of the initial setup for
you. It's called **ext\_skel**, and it's been distributed with PHP since
4.0.

Running **ext\_skel** with no parameters produces this output in PHP
5.2.2:

    php-5.2.2/ext$ ./ext_skel 
    ./ext_skel --extname=module [--proto=file] [--stubs=file] [--xml[=file]]
               [--skel=dir] [--full-xml] [--no-help]

      --extname=module   module is the name of your extension
      --proto=file       file contains prototypes of functions to create
      --stubs=file       generate only function stubs in file
      --xml              generate xml documentation to be added to phpdoc-cvs
      --skel=dir         path to the skeleton directory
      --full-xml         generate xml documentation for a self-contained extension
                         (not yet implemented)
      --no-help          don't try to be nice and create comments in the code
                         and helper functions to test if the module compiled

Generally, when developing a new extension the only parameters you will
be interested in are *--extname* and *--no-help*. Unless you are already
experienced with the structure of an extension, you will *not* want to
use *--no-help*; specifying it causes **ext\_skel** to leave out many
helpful comments in the files it generates.

This leaves you with *--extname*, which tells **ext\_skel** what the
name of your extension is. This "name" is an all-lowercase identifier
containing only letters and underscores which is unique among everything
in the `ext/` folder of your PHP distribution.

The *--proto* option is intended to allow the developer to specify a
header file from which a set of PHP functions will be created,
ostensibly for the purpose of developing an extension based on a
library, but it often functions poorly with most modern header files. A
test run on the `zlib.h` header resulted in a very large number of empty
and nonsense prototypes in the **ext\_skel** output files. The *--xml*
and *--full-xml* options are entirely nonfunctional thus far. The
*--skel* option can be used to specify a modified set of skeleton files
to work from, a topic which is beyond the scope of this section.
