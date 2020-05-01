Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/pspell/setup.html#Requirements)
-   [Installation](/pspell/setup.html#Installation)
-   [Runtime Configuration](/pspell/setup.html#Runtime%20Configuration)
-   [Resource Types](/pspell/setup.html#Resource%20Types)

Requirements
------------

To compile PHP with pspell support, you need the aspell library,
available from
<a href="http://aspell.net/" class="link external">» http://aspell.net/</a>.

Installation
------------

If you have the libraries needed add the **--with-pspell\[=dir\]**
option when compiling PHP.

> **Note**: **Note to Win32 Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `aspell-15.dll`
> from the `bin` folder of the aspell installation.
>
> Win32 support requires at least aspell version 0.50.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.
