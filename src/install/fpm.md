FastCGI Process Manager (FPM)
=============================

**Table of Contents**

-   [Installation](/install/fpm/install.html)
-   [Configuration](/install/fpm/configuration.html)

FPM (FastCGI Process Manager) is an alternative PHP FastCGI
implementation with some additional features (mostly) useful for
heavy-loaded sites.

These features include:

-   advanced process management with graceful stop/start;

-   ability to start workers with different uid/gid/chroot/environment,
    listening on different ports and using different php.ini (replaces
    safe\_mode);

-   stdout and stderr logging;

-   emergency restart in case of accidental opcode cache destruction;

-   accelerated upload support;

-   "slowlog" - logging scripts (not just their names, but their PHP
    backtraces too, using ptrace and similar things to read remote
    process' execute\_data) that are executed unusually slow;

-   <span class="function">fastcgi\_finish\_request</span> - special
    function to finish request and flush all data while continuing to do
    something time-consuming (video converting, stats processing etc.);

-   dynamic/static child spawning;

-   basic SAPI status info (similar to Apache mod\_status);

-   php.ini-based config file.
