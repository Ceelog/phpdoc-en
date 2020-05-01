php-config
----------

php-config is a simple shell script for obtaining information about the
installed PHP configuration.

When compiling extensions, if you have multiple PHP versions installed,
you may specify for which installation you'd like to build by using the
*--with-php-config* option during configuration, specifying the path of
the respective php-config script.

The list of command line options provided by the php-config script can
be queried anytime by running php-config with the **-h** switch:

    Usage: /usr/local/bin/php-config [OPTION]
    Options:
      --prefix            [...]
      --includes          [...]
      --ldflags           [...]
      --libs              [...]
      --extension-dir     [...]
      --include-dir       [...]
      --php-binary        [...]
      --php-sapis         [...]
      --configure-options [...]
      --version           [...]
      --vernum            [...]

| Option              | Description                                                             |
|---------------------|-------------------------------------------------------------------------|
| --prefix            | Directory prefix where PHP is installed, e.g. /usr/local                |
| --includes          | List of -I options with all include files                               |
| --ldflags           | LD Flags which PHP was compiled with                                    |
| --libs              | Extra libraries which PHP was compiled with                             |
| --extension-dir     | Directory where extensions are searched by default                      |
| --include-dir       | Directory prefix where header files are installed by default            |
| --php-binary        | Full path to php CLI or CGI binary                                      |
| --php-sapis         | Show all SAPI modules available                                         |
| --configure-options | Configure options to recreate configuration of current PHP installation |
| --version           | PHP version                                                             |
| --vernum            | PHP version as integer                                                  |
