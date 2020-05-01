Talking to the Windows build system: config.w32
-----------------------------------------------

An extension's `config.w32` file is similar in usage to the `config.m4`
file, with two critical differences: first, it is used for Windows
builds, and second, it is written in JavaScript. This section makes no
attempt to cover JavaScript syntax. For the moment, this section is
incomplete in lieu of a Win32 testbed, and an experimental-only port of
the example `config.m4` is the only example provided.

**Example \#1 An example config.w32 file**

``` javascript
// $Id$
// vim:ft=javascript
```

``` javascript
ARG_WITH("example", "for example support", "no");
ARG_ENABLE("example-debug", "for debugging support in example", "no")
ARG_WITH("example-extra", "for extra functionality in example", "no")
if (PHP_EXAMPLE != "no") {
    if (CHECK_LIB("libexample.lib", "example", PHP_EXAMPLE) &&
        CHECK_HEADER_ADD_INCLUDE("example.h", "CFLAGS_EXAMPLE", PHP_EXAMPLE + "\\include")) {
        
        if (PHP_EXAMPLE_DEBUG != "no") {
            AC_DEFINE('USE_EXAMPLE_DEBUG', 1, 'Debug support in example');
        }
        
        if (PHP_EXAMPLE_EXTRA != "no" &&
            CHECK_LIB("libexample-extra.lib", "example", PHP_EXAMPLE) &&
            CHECK_HEADER_ADD_INCLUDE("example-extra.h", "CFLAGS_EXAMPLE", PHP_EXAMPLE + ";" + PHP_PHP_BUILD + "\\include") {
            AC_DEFINE('HAVE_EXAMPLEEXTRA', 1, 'Extra functionality in example');
            HAVE_EXTRA = 1;
        } else {
            WARNING( "extra example functionality not enabled, lib not found" );
        }
        
        EXTENSION("example", "example.c");
        if (HAVE_EXTRA == 1) {
            ADD_SOURCES("example-extra.c");
        }
    } else {
        WARNING( "example not enabled; libraries not found" );
    }
}
```

### The counter extension's config.w32 file

The counter extension previously documented has a much simpler
`config.w32` file than that described above, as it doesn't make use of
many buildsystem features.

**Example \#2 counter's config.w32 file**

``` autoconf
// $Id$
// vim:ft=javascript
```

``` autoconf
ARG_ENABLE("counter", "for counter support", "no");
if (PHP_COUNTER != "no") {
    EXTENSION("counter", "counter.c");
    ADD_SOURCE("counter-util.c");
}
```
