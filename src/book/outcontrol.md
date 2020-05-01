Output Buffering Control
========================

**Table of Contents**

-   [Introduction](/intro/outcontrol.html)
-   [Installing/Configuring](/outcontrol/setup.html)
    -   [Requirements](/outcontrol/setup.html#Requirements)
    -   [Installation](/outcontrol/setup.html#Installation)
    -   [Runtime
        Configuration](/outcontrol/setup.html#Runtime%20Configuration)
    -   [Resource Types](/outcontrol/setup.html#Resource%20Types)
-   [Predefined Constants](/outcontrol/constants.html)
-   [Examples](/outcontrol/examples.html)
    -   [Basic usage](/outcontrol/examples.html#Basic%20usage)
    -   [Output rewrite
        usage](/outcontrol/examples.html#Output%20rewrite%20usage)
-   [Output Control Functions](/ref/outcontrol.html)
    -   [flush](/ref/outcontrol.html#flush) — Flush system output buffer
    -   [ob\_clean](/ref/outcontrol.html#ob_clean) — Clean (erase) the
        output buffer
    -   [ob\_end\_clean](/ref/outcontrol.html#ob_end_clean) — Clean
        (erase) the output buffer and turn off output buffering
    -   [ob\_end\_flush](/ref/outcontrol.html#ob_end_flush) — Flush
        (send) the output buffer and turn off output buffering
    -   [ob\_flush](/ref/outcontrol.html#ob_flush) — Flush (send) the
        output buffer
    -   [ob\_get\_clean](/ref/outcontrol.html#ob_get_clean) — Get
        current buffer contents and delete current output buffer
    -   [ob\_get\_contents](/ref/outcontrol.html#ob_get_contents) —
        Return the contents of the output buffer
    -   [ob\_get\_flush](/ref/outcontrol.html#ob_get_flush) — Flush the
        output buffer, return it as a string and turn off output
        buffering
    -   [ob\_get\_length](/ref/outcontrol.html#ob_get_length) — Return
        the length of the output buffer
    -   [ob\_get\_level](/ref/outcontrol.html#ob_get_level) — Return the
        nesting level of the output buffering mechanism
    -   [ob\_get\_status](/ref/outcontrol.html#ob_get_status) — Get
        status of output buffers
    -   [ob\_gzhandler](/ref/outcontrol.html#ob_gzhandler) — ob\_start
        callback function to gzip output buffer
    -   [ob\_implicit\_flush](/ref/outcontrol.html#ob_implicit_flush) —
        Turn implicit flush on/off
    -   [ob\_list\_handlers](/ref/outcontrol.html#ob_list_handlers) —
        List all output handlers in use
    -   [ob\_start](/ref/outcontrol.html#ob_start) — Turn on output
        buffering
    -   [output\_add\_rewrite\_var](/ref/outcontrol.html#output_add_rewrite_var)
        — Add URL rewriter values
    -   [output\_reset\_rewrite\_vars](/ref/outcontrol.html#output_reset_rewrite_vars)
        — Reset URL rewriter values
