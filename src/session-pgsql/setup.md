Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/session-pgsql/setup.html#Requirements)
-   [Installation](/session-pgsql/setup.html#Installation)
-   [Runtime
    Configuration](/session-pgsql/setup.html#Runtime%20Configuration)
-   [Resource Types](/session-pgsql/setup.html#Resource%20Types)

Requirements
------------

You need at least PHP \>= 4.3.0, and PostgreSQL \>=7.2.0 as database
server. *libpq* that comes with PostgreSQL 7.2.0 or later (and header
files to build) and
<a href="http://www.ossp.org/pkg/lib/mm/" class="link external">» libmm</a>
(and header files).

Installation
------------

This extension is considered unmaintained and dead. However, the source
code for this extension is still available within PECL SVN here:
<a href="https://svn.php.net/viewvc/pecl/session_pgsql" class="link external">» https://svn.php.net/viewvc/pecl/session_pgsql</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

PostgreSQL session save handler is still under development. Refer to the
`README` file in the source distribution for configuration details.

Resource Types
--------------

This extension has no resource types defined.
