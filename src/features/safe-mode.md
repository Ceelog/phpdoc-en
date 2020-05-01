Safe Mode
=========

**Table of Contents**

-   [Security and Safe Mode](/ini/sect/safe-mode.html)
-   [Functions restricted/disabled by safe
    mode](/features/safe-mode/functions.html)

The PHP safe mode is an attempt to solve the shared-server security
problem. It is architecturally incorrect to try to solve this problem at
the PHP level, but since the alternatives at the web server and OS
levels aren't very realistic, many people, especially ISP's, use safe
mode for now.

**Warning**

This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

| Version | Description                                                                          |
|---------|--------------------------------------------------------------------------------------|
| 5.4.0   | Removed from PHP, and generates a fatal **`E_CORE_ERROR`** level error when enabled. |
| 5.3.0   | Deprecated, and **`E_DEPRECATED`** errors were added.                                |
