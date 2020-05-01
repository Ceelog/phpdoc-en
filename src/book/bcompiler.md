PHP bytecode Compiler
=====================

**Table of Contents**

-   [Introduction](/intro/bcompiler.html)
-   [Installing/Configuring](/bcompiler/setup.html)
    -   [Requirements](/bcompiler/setup.html#Requirements)
    -   [Installation](/bcompiler/setup.html#Installation)
    -   [Runtime
        Configuration](/bcompiler/setup.html#Runtime%20Configuration)
    -   [Resource Types](/bcompiler/setup.html#Resource%20Types)
-   [Predefined Constants](/bcompiler/constants.html)
-   [bcompiler Functions](/ref/bcompiler.html)
    -   [bcompiler\_load\_exe](/ref/bcompiler.html#bcompiler_load_exe) —
        Reads and creates classes from a bcompiler exe file
    -   [bcompiler\_load](/ref/bcompiler.html#bcompiler_load) — Reads
        and creates classes from a bz compressed file
    -   [bcompiler\_parse\_class](/ref/bcompiler.html#bcompiler_parse_class)
        — Reads the bytecodes of a class and calls back to a user
        function
    -   [bcompiler\_read](/ref/bcompiler.html#bcompiler_read) — Reads
        and creates classes from a filehandle
    -   [bcompiler\_write\_class](/ref/bcompiler.html#bcompiler_write_class)
        — Writes a defined class as bytecodes
    -   [bcompiler\_write\_constant](/ref/bcompiler.html#bcompiler_write_constant)
        — Writes a defined constant as bytecodes
    -   [bcompiler\_write\_exe\_footer](/ref/bcompiler.html#bcompiler_write_exe_footer)
        — Writes the start pos, and sig to the end of a exe type file
    -   [bcompiler\_write\_file](/ref/bcompiler.html#bcompiler_write_file)
        — Writes a php source file as bytecodes
    -   [bcompiler\_write\_footer](/ref/bcompiler.html#bcompiler_write_footer)
        — Writes the single character \\x00 to indicate End of compiled
        data
    -   [bcompiler\_write\_function](/ref/bcompiler.html#bcompiler_write_function)
        — Writes a defined function as bytecodes
    -   [bcompiler\_write\_functions\_from\_file](/ref/bcompiler.html#bcompiler_write_functions_from_file)
        — Writes all functions defined in a file as bytecodes
    -   [bcompiler\_write\_header](/ref/bcompiler.html#bcompiler_write_header)
        — Writes the bcompiler header
    -   [bcompiler\_write\_included\_filename](/ref/bcompiler.html#bcompiler_write_included_filename)
        — Writes an included file as bytecodes
