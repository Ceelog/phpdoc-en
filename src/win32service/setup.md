Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/win32service/setup.html#Requirements)
-   [Installation](/win32service/setup.html#Installation)
-   [Runtime
    Configuration](/win32service/setup.html#Runtime%20Configuration)
-   [Resource Types](/win32service/setup.html#Resource%20Types)
-   [Security
    consideration](/win32service/setup.html#Security%20consideration)

Requirements
------------

Windows NT, Windows 2000, Windows XP or Windows Server 2003. Any version
of Windows derived from Windows NT should be compatible.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/win32service" class="link external">» https://pecl.php.net/package/win32service</a>

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Security consideration
----------------------

This extension needs administrator privileges for some actions such as
<a href="/ref/win32service.html#win32_create_service" class="link">create</a>,
<a href="/ref/win32service.html#win32_delete_service" class="link">delete</a>,
<a href="/ref/win32service.html#win32_start_service" class="link">start</a>,
<a href="/ref/win32service.html#win32_stop_service" class="link">stop</a>,
<a href="/ref/win32service.html#win32_pause_service" class="link">pause</a>
and
<a href="/ref/win32service.html#win32_continue_service" class="link">continue</a>.
This requirement can cause an elevation of privileges if the service
control is available from the web interface or remote control.

You can set the ACL on the service after adding it into SCM to delegate
the current administration tasks to an non administrator account or
service account. For further instructions, see the
<a href="https://support.microsoft.com/en-us/help/914392/best-practices-and-guidance-for-writers-of-service-discretionary-acces" class="link external">» Microsoft Knowledge Base</a>.
