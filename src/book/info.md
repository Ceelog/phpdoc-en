PHP Options and Information
===========================

**Table of Contents**

-   [Introduction](/intro/info.html)
-   [Installing/Configuring](/info/setup.html)
    -   [Requirements](/info/setup.html#Requirements)
    -   [Installation](/info/setup.html#Installation)
    -   [Runtime
        Configuration](/info/setup.html#Runtime%20Configuration)
    -   [Resource Types](/info/setup.html#Resource%20Types)
-   [Predefined Constants](/info/constants.html)
-   [PHP Options/Info Functions](/ref/info.html)
    -   [assert\_options](/ref/info.html#assert_options) — Set/get the
        various assert flags
    -   [assert](/ref/info.html#assert) — Checks if assertion is FALSE
    -   [cli\_get\_process\_title](/ref/info.html#cli_get_process_title)
        — Returns the current process title
    -   [cli\_set\_process\_title](/ref/info.html#cli_set_process_title)
        — Sets the process title
    -   [dl](/ref/info.html#dl) — Loads a PHP extension at runtime
    -   [extension\_loaded](/ref/info.html#extension_loaded) — Find out
        whether an extension is loaded
    -   [gc\_collect\_cycles](/ref/info.html#gc_collect_cycles) — Forces
        collection of any existing garbage cycles
    -   [gc\_disable](/ref/info.html#gc_disable) — Deactivates the
        circular reference collector
    -   [gc\_enable](/ref/info.html#gc_enable) — Activates the circular
        reference collector
    -   [gc\_enabled](/ref/info.html#gc_enabled) — Returns status of the
        circular reference collector
    -   [gc\_mem\_caches](/ref/info.html#gc_mem_caches) — Reclaims
        memory used by the Zend Engine memory manager
    -   [gc\_status](/ref/info.html#gc_status) — Gets information about
        the garbage collector
    -   [get\_cfg\_var](/ref/info.html#get_cfg_var) — Gets the value of
        a PHP configuration option
    -   [get\_current\_user](/ref/info.html#get_current_user) — Gets the
        name of the owner of the current PHP script
    -   [get\_defined\_constants](/ref/info.html#get_defined_constants)
        — Returns an associative array with the names of all the
        constants and their values
    -   [get\_extension\_funcs](/ref/info.html#get_extension_funcs) —
        Returns an array with the names of the functions of a module
    -   [get\_include\_path](/ref/info.html#get_include_path) — Gets the
        current include\_path configuration option
    -   [get\_included\_files](/ref/info.html#get_included_files) —
        Returns an array with the names of included or required files
    -   [get\_loaded\_extensions](/ref/info.html#get_loaded_extensions)
        — Returns an array with the names of all modules compiled and
        loaded
    -   [get\_magic\_quotes\_gpc](/ref/info.html#get_magic_quotes_gpc) —
        Gets the current configuration setting of magic\_quotes\_gpc
    -   [get\_magic\_quotes\_runtime](/ref/info.html#get_magic_quotes_runtime)
        — Gets the current active configuration setting of
        magic\_quotes\_runtime
    -   [get\_required\_files](/ref/info.html#get_required_files) —
        Alias of get\_included\_files
    -   [get\_resources](/ref/info.html#get_resources) — Returns active
        resources
    -   [getenv](/ref/info.html#getenv) — Gets the value of an
        environment variable
    -   [getlastmod](/ref/info.html#getlastmod) — Gets time of last page
        modification
    -   [getmygid](/ref/info.html#getmygid) — Get PHP script owner's GID
    -   [getmyinode](/ref/info.html#getmyinode) — Gets the inode of the
        current script
    -   [getmypid](/ref/info.html#getmypid) — Gets PHP's process ID
    -   [getmyuid](/ref/info.html#getmyuid) — Gets PHP script owner's
        UID
    -   [getopt](/ref/info.html#getopt) — Gets options from the command
        line argument list
    -   [getrusage](/ref/info.html#getrusage) — Gets the current
        resource usages
    -   [ini\_alter](/ref/info.html#ini_alter) — Alias of ini\_set
    -   [ini\_get\_all](/ref/info.html#ini_get_all) — Gets all
        configuration options
    -   [ini\_get](/ref/info.html#ini_get) — Gets the value of a
        configuration option
    -   [ini\_restore](/ref/info.html#ini_restore) — Restores the value
        of a configuration option
    -   [ini\_set](/ref/info.html#ini_set) — Sets the value of a
        configuration option
    -   [magic\_quotes\_runtime](/ref/info.html#magic_quotes_runtime) —
        Alias of set\_magic\_quotes\_runtime
    -   [main](/ref/info.html#main) — Dummy for main
    -   [memory\_get\_peak\_usage](/ref/info.html#memory_get_peak_usage)
        — Returns the peak of memory allocated by PHP
    -   [memory\_get\_usage](/ref/info.html#memory_get_usage) — Returns
        the amount of memory allocated to PHP
    -   [php\_ini\_loaded\_file](/ref/info.html#php_ini_loaded_file) —
        Retrieve a path to the loaded php.ini file
    -   [php\_ini\_scanned\_files](/ref/info.html#php_ini_scanned_files)
        — Return a list of .ini files parsed from the additional ini dir
    -   [php\_logo\_guid](/ref/info.html#php_logo_guid) — Gets the logo
        guid
    -   [php\_sapi\_name](/ref/info.html#php_sapi_name) — Returns the
        type of interface between web server and PHP
    -   [php\_uname](/ref/info.html#php_uname) — Returns information
        about the operating system PHP is running on
    -   [phpcredits](/ref/info.html#phpcredits) — Prints out the credits
        for PHP
    -   [phpinfo](/ref/info.html#phpinfo) — Outputs information about
        PHP's configuration
    -   [phpversion](/ref/info.html#phpversion) — Gets the current PHP
        version
    -   [putenv](/ref/info.html#putenv) — Sets the value of an
        environment variable
    -   [restore\_include\_path](/ref/info.html#restore_include_path) —
        Restores the value of the include\_path configuration option
    -   [set\_include\_path](/ref/info.html#set_include_path) — Sets the
        include\_path configuration option
    -   [set\_magic\_quotes\_runtime](/ref/info.html#set_magic_quotes_runtime)
        — Sets the current active configuration setting of
        magic\_quotes\_runtime
    -   [set\_time\_limit](/ref/info.html#set_time_limit) — Limits the
        maximum execution time
    -   [sys\_get\_temp\_dir](/ref/info.html#sys_get_temp_dir) — Returns
        directory path used for temporary files
    -   [version\_compare](/ref/info.html#version_compare) — Compares
        two "PHP-standardized" version number strings
    -   [zend\_logo\_guid](/ref/info.html#zend_logo_guid) — Gets the
        Zend guid
    -   [zend\_thread\_id](/ref/info.html#zend_thread_id) — Returns a
        unique identifier for the current thread
    -   [zend\_version](/ref/info.html#zend_version) — Gets the version
        of the current Zend engine
