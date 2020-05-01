Direct IO
=========

**Table of Contents**

-   [Introduction](/intro/dio.html)
-   [Installing/Configuring](/dio/setup.html)
    -   [Requirements](/dio/setup.html#Requirements)
    -   [Installation](/dio/setup.html#Installation)
    -   [Runtime Configuration](/dio/setup.html#Runtime%20Configuration)
    -   [Resource Types](/dio/setup.html#Resource%20Types)
-   [Predefined Constants](/dio/constants.html)
-   [Direct IO Functions](/ref/dio.html)
    -   [dio\_close](/ref/dio.html#dio_close) — Closes the file
        descriptor given by fd
    -   [dio\_fcntl](/ref/dio.html#dio_fcntl) — Performs a c library
        fcntl on fd
    -   [dio\_open](/ref/dio.html#dio_open) — Opens a file (creating it
        if necessary) at a lower level than the C library input/ouput
        stream functions allow
    -   [dio\_read](/ref/dio.html#dio_read) — Reads bytes from a file
        descriptor
    -   [dio\_seek](/ref/dio.html#dio_seek) — Seeks to pos on fd from
        whence
    -   [dio\_stat](/ref/dio.html#dio_stat) — Gets stat information
        about the file descriptor fd
    -   [dio\_tcsetattr](/ref/dio.html#dio_tcsetattr) — Sets terminal
        attributes and baud rate for a serial port
    -   [dio\_truncate](/ref/dio.html#dio_truncate) — Truncates file
        descriptor fd to offset bytes
    -   [dio\_write](/ref/dio.html#dio_write) — Writes data to fd with
        optional truncation at length
