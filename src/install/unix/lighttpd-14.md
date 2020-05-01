Lighttpd 1.4 on Unix systems
----------------------------

This section contains notes and hints specific to Lighttpd 1.4 installs
of PHP on Unix systems.

Please use the
<a href="http://trac.lighttpd.net/trac/" class="link external">» Lighttpd trac</a>
to learn how to install Lighttpd properly before continuing.

Fastcgi is the preferred SAPI to connect PHP and Lighttpd. Fastcgi is
automagically enabled in php-cgi in PHP 5.3, but for older versions
configure PHP with --enable-fastcgi. To confirm that PHP has fastcgi
enabled, *php -v* should contain *PHP 5.2.5 (cgi-fcgi)* Before PHP
5.2.3, fastcgi was enabled on the php binary (there was no php-cgi).

### Letting Lighttpd spawn php processes

To configure Lighttpd to connect to php and spawn fastcgi processes,
edit lighttpd.conf. Sockets are preferred to connect to fastcgi
processes on the local system.

**Example \#1 Partial lighttpd.conf**

    server.modules += ( "mod_fastcgi" )

    fastcgi.server = ( ".php" =>
      ((
        "socket" => "/tmp/php.socket",
        "bin-path" => "/usr/local/bin/php-cgi",
        "bin-environment" => (
          "PHP_FCGI_CHILDREN" => "16",
          "PHP_FCGI_MAX_REQUESTS" => "10000"
        ),
        "min-procs" => 1,
        "max-procs" => 1,
        "idle-timeout" => 20
      ))
    )

The bin-path directive allows lighttpd to spawn fastcgi processes
dynamically. PHP will spawn children according to the
PHP\_FCGI\_CHILDREN environment variable. The "bin-environment"
directive sets the environment for the spawned processes. PHP will kill
a child process after the number of requests specified by
PHP\_FCGI\_MAX\_REQUESTS is reached. The directives "min-procs" and
"max-procs" should generally be avoided with PHP. PHP manages its own
children and opcode caches like APC will only share among children
managed by PHP. If "min-procs" is set to something greater than 1, the
total number of php responders will be multiplied PHP\_FCGI\_CHILDREN (2
min-procs \* 16 children gives 32 responders).

### Spawning with spawn-fcgi

Lighttpd provides a program called spawn-fcgi to make the process of
spawning fastcgi processes easier.

### Spawning php-cgi

It is possible to spawn processes without spawn-fcgi, though a bit of
heavy-lifting is required. Setting the PHP\_FCGI\_CHILDREN environment
var controls how many children PHP will spawn to handle incoming
requests. Setting PHP\_FCGI\_MAX\_REQUESTS will determine how long (in
requests) each child will live. Here's a simple bash script to help
spawn php responders.

**Example \#2 Spawning FastCGI Responders**

    #!/bin/sh

    # Location of the php-cgi binary
    PHP=/usr/local/bin/php-cgi

    # PID File location
    PHP_PID=/tmp/php.pid

    # Binding to an address
    #FCGI_BIND_ADDRESS=10.0.1.1:10000
    # Binding to a domain socket
    FCGI_BIND_ADDRESS=/tmp/php.sock

    PHP_FCGI_CHILDREN=16
    PHP_FCGI_MAX_REQUESTS=10000

    env -i PHP_FCGI_CHILDREN=$PHP_FCGI_CHILDREN \
           PHP_FCGI_MAX_REQUESTS=$PHP_FCGI_MAX_REQUESTS \
           $PHP -b $FCGI_BIND_ADDRESS &

    echo $! > "$PHP_PID"

### Connecting to remote FCGI instances

Fastcgi instances can be spawned on multiple remote machines in order to
scale applications.

**Example \#3 Connecting to remote php-fastcgi instances**

    fastcgi.server = ( ".php" =>
       (( "host" => "10.0.0.2", "port" => 1030 ),
        ( "host" => "10.0.0.3", "port" => 1030 ))
    )
