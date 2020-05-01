Predefined Constants
====================

The constants below are always available as part of the PHP core.

| Constant               | Value | Description                                                                                                                                                                                                                                       |
|------------------------|-------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`CREDITS_GROUP`**    | 1     | A list of the core developers                                                                                                                                                                                                                     |
| **`CREDITS_GENERAL`**  | 2     | General credits: Language design and concept, PHP authors and SAPI module.                                                                                                                                                                        |
| **`CREDITS_SAPI`**     | 4     | A list of the server API modules for PHP, and their authors.                                                                                                                                                                                      |
| **`CREDITS_MODULES`**  | 8     | A list of the extension modules for PHP, and their authors.                                                                                                                                                                                       |
| **`CREDITS_DOCS`**     | 16    | The credits for the documentation team.                                                                                                                                                                                                           |
| **`CREDITS_FULLPAGE`** | 32    | Usually used in combination with the other flags. Indicates that a complete stand-alone HTML page needs to be printed including the information indicated by the other flags.                                                                     |
| **`CREDITS_QA`**       | 64    | The credits for the quality assurance team.                                                                                                                                                                                                       |
| **`CREDITS_ALL`**      | -1    | All the credits, equivalent to using: *CREDITS\_DOCS + CREDITS\_GENERAL + CREDITS\_GROUP + CREDITS\_MODULES + CREDITS\_QA CREDITS\_FULLPAGE*. It generates a complete stand-alone HTML page with the appropriate tags. This is the default value. |

| Constant                 | Value | Description                                                                                                                                          |
|--------------------------|-------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`INFO_GENERAL`**       | 1     | The configuration line, `php.ini` location, build date, Web Server, System and more.                                                                 |
| **`INFO_CREDITS`**       | 2     | PHP Credits. See also <span class="function">phpcredits</span>.                                                                                      |
| **`INFO_CONFIGURATION`** | 4     | Current Local and Master values for PHP directives. See also <span class="function">ini\_get</span>.                                                 |
| **`INFO_MODULES`**       | 8     | Loaded modules and their respective settings.                                                                                                        |
| **`INFO_ENVIRONMENT`**   | 16    | Environment Variable information that's also available in `$_ENV`.                                                                                   |
| **`INFO_VARIABLES`**     | 32    | Shows all <a href="/language/variables/predefined.html" class="link">predefined variables</a> from *EGPCS* (Environment, GET, POST, Cookie, Server). |
| **`INFO_LICENSE`**       | 64    | PHP License information. See also the <a href="https://www.php.net/license/" class="link external">» license faq</a>.                                |
| **`INFO_ALL`**           | -1    | Shows all of the above. This is the default value.                                                                                                   |

| Constant      | Value | Description |
|---------------|-------|-------------|
| *INI\_USER*   | 1     | Unused      |
| *INI\_PERDIR* | 2     | Unused      |
| *INI\_SYSTEM* | 4     | Unused      |
| *INI\_ALL*    | 7     | Unused      |

Assert constants, these values are used to set the assertion options in
<span class="function">assert\_options</span>.

| Constant                | INI Setting        | Description                                                        |
|-------------------------|--------------------|--------------------------------------------------------------------|
| **`ASSERT_ACTIVE`**     | assert.active      | Enable <span class="function">assert</span> evaluation.            |
| **`ASSERT_CALLBACK`**   | assert.callback    | Callback to call on failed assertions.                             |
| **`ASSERT_BAIL`**       | assert.bail        | Terminate execution on failed assertions.                          |
| **`ASSERT_WARNING`**    | assert.warning     | Issues a PHP warning for each failed assertion                     |
| **`ASSERT_QUIET_EVAL`** | assert.quiet\_eval | Disable *error\_reporting* during assertion expression evaluation. |

The following constants are only available if the host operating system
is Windows, and can tell different versioning information so its
possible to detect various features and make use of them. They are all
available as of PHP 5.3.0.

| Constant                               | Description                                                                                                                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`PHP_WINDOWS_VERSION_MAJOR`**        | The major version of Windows, this can be either *4* (NT4/Me/98/95), *5* (XP/2003 R2/2003/2000) or *6* (Vista/2008/7/8/8.1).                                                        |
| **`PHP_WINDOWS_VERSION_MINOR`**        | The minor version of Windows, this can be either *0* (Vista/2008/2000/NT4/95), *1* (XP), *2* (2003 R2/2003/XP x64), *10* (98) or *90* (ME).                                         |
| **`PHP_WINDOWS_VERSION_BUILD`**        | The Windows build number (for example, Windows Vista with SP1 applied is build 6001)                                                                                                |
| **`PHP_WINDOWS_VERSION_PLATFORM`**     | The platform that PHP currently is running on, this value is *2* on Windows Vista/XP/2000/NT4, Server 2008/2003 and on Windows ME/98/95 this value is *1*.                          |
| **`PHP_WINDOWS_VERSION_SP_MAJOR`**     | The major version of the service pack installed, this value is *0* if no service pack is installed. For example, Windows XP with service pack 3 installed will make this value *3*. |
| **`PHP_WINDOWS_VERSION_SP_MINOR`**     | The minor version of the service pack installed, this value is *0* if no service pack is installed.                                                                                 |
| **`PHP_WINDOWS_VERSION_SUITEMASK`**    | The suitemask is a bitmask that can tell if various features of Windows is installed, see the table below for possible bitfield values.                                             |
| **`PHP_WINDOWS_VERSION_PRODUCTTYPE`**  | This contains the value used to determine the *PHP\_WINDOWS\_NT\_\** constants. This value may be one of the *PHP\_WINDOWS\_NT\_\** constants indicating the platform type.         |
| **`PHP_WINDOWS_NT_DOMAIN_CONTROLLER`** | This is a domain controller                                                                                                                                                         |
| **`PHP_WINDOWS_NT_SERVER`**            | This is a server system (eg. Server 2008/2003/2000), note that if this is a domain controller its reported as **`PHP_WINDOWS_NT_DOMAIN_CONTROLLER`**.                               |
| **`PHP_WINDOWS_NT_WORKSTATION`**       | This is a workstation system (eg. Vista/XP/2000/NT4)                                                                                                                                |

This table shows a list of features that can be checked for using the
**`PHP_WINDOWS_VERSION_SUITEMASK`** bitmask.

| Bits         | Description                                                                                                                                                        |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *0x00000004* | Microsoft BackOffice components are installed.                                                                                                                     |
| *0x00000400* | Windows Server 2003, Web Edition is installed.                                                                                                                     |
| *0x00004000* | Windows Server 2003, Compute Cluster Edition is installed.                                                                                                         |
| *0x00000080* | Windows Server 2008 Datacenter, Windows Server 2003, Datacenter Edition or Windows 2000 Datacenter Server is installed.                                            |
| *0x00000002* | Windows Server 2008 Enterprise, Windows Server 2003, Enterprise Edition, Windows 2000 Advanced Server, or Windows NT Server 4.0 Enterprise Edition is installed.   |
| *0x00000040* | Windows XP Embedded is installed.                                                                                                                                  |
| *0x00000200* | Windows Vista Home Premium, Windows Vista Home Basic, or Windows XP Home Edition is installed.                                                                     |
| *0x00000100* | Remote Desktop is supported, but only one interactive session is supported. This value is set unless the system is running in application server mode.             |
| *0x00000001* | Microsoft Small Business Server was once installed on the system, but may have been upgraded to another version of Windows.                                        |
| *0x00000020* | Microsoft Small Business Server is installed with the restrictive client license in force.                                                                         |
| *0x00002000* | Windows Storage Server 2003 R2 or Windows Storage Server 2003 is installed.                                                                                        |
| *0x00000010* | Terminal Services is installed. This value is always set. If this value is set but *0x00000100* is not set, then the system is running in application server mode. |
| *0x00008000* | Windows Home Server is installed.                                                                                                                                  |
