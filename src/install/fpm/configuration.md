Configuration
-------------

FPM uses `php.ini` syntax for its configuration file - `php-fpm.conf`,
and pool configuration files.

### List of global `php-fpm.conf` directives

`pid` <span class="type">string</span>  
Path to PID file. Default value: none.

`error_log` <span class="type">string</span>  
Path to error log file. Default value:
*\#INSTALL\_PREFIX\#/log/php-fpm.log*. If it's set to "syslog", log is
sent to syslogd instead of being written in a local file.

`log_level` <span class="type">string</span>  
Error log level. Possible values: alert, error, warning, notice, debug.
Default value: notice.

`log_limit` <span class="type">int</span>  
Log limit for the logged lines which allows to log messages longer than
1024 characters without wrapping. Default value: 1024. Available as of
PHP 7.3.0.

`log_buffering` <span class="type">bool</span>  
Experimental logging without extra buffering. Default value: yes.
Available as of PHP 7.3.0.

`syslog.facility` <span class="type">string</span>  
used to specify what type of program is logging the message. Default
value: daemon.

`syslog.ident` <span class="type">string</span>  
Prepended to every message. If you have multiple FPM instances running
on the same server, you can change the default value which must suit
common needs. Default value: php-fpm.

`emergency_restart_threshold` <span class="type">int</span>  
If this number of child processes exit with SIGSEGV or SIGBUS within the
time interval set by *emergency\_restart\_interval*, then FPM will
restart. A value of 0 means 'Off'. Default value: 0 (Off).

`emergency_restart_interval` <span class="type">mixed</span>  
Interval of time used by *emergency\_restart\_interval* to determine
when a graceful restart will be initiated. This can be useful to work
around accidental corruptions in an accelerator's shared memory.
Available Units: s(econds), m(inutes), h(ours), or d(ays). Default Unit:
seconds. Default value: 0 (Off).

`process_control_timeout` <span class="type">mixed</span>  
Time limit for child processes to wait for a reaction on signals from
master. Available units: s(econds), m(inutes), h(ours), or d(ays)
Default Unit: seconds. Default value: 0.

`process.max` <span class="type">int</span>  
The maximum number of processes FPM will fork. This has been design to
control the global number of processes when using dynamic PM within a
lot of pools. Use it with caution. Default value: 0.

`process.priority` <span class="type">int</span>  
Specify the nice(2) priority to apply to the master process (only if
set). The value can vary from -19 (highest priority) to 20 (lower
priority). Default value: not set.

`daemonize` <span class="type">bool</span>  
Send FPM to background. Set to 'no' to keep FPM in foreground for
debugging. Default value: yes.

`rlimit_files` <span class="type">int</span>  
Set open file descriptor rlimit for the master process. Default value:
Set open file descriptor rlimit for the master process.

`rlimit_core` <span class="type">int</span>  
Set max core size rlimit for the master process. Default value: 0.

`events.mechanism` <span class="type">string</span>  
Specify the event mechanism FPM will use. The following is available:
select, pool, epoll, kqueue (\*BSD), port (Solaris). Default value: not
set (auto detection).

`systemd_interval` <span class="type">int</span>  
When FPM is build with systemd integration, specify the interval, in
second, between health report notification to systemd. Set to 0 to
disable. Default value: 10.

### List of pool directives

With FPM you can run several pools of processes with different setting.
These are settings that can be tweaked per pool.

`listen` <span class="type">string</span>  
The address on which to accept FastCGI requests. Valid syntaxes are:
'ip.add.re.ss:port', 'port', '/path/to/unix/socket'. This option is
mandatory for each pool.

`listen.backlog` <span class="type">int</span>  
Set listen(2) backlog. A value of '-1' means unlimited. Default value:
-1.

`listen.allowed_clients` <span class="type">string</span>  
List of IPv4 addresses of FastCGI clients which are allowed to connect.
Equivalent to the FCGI\_WEB\_SERVER\_ADDRS environment variable in the
original PHP FastCGI (5.2.2+). Makes sense only with a tcp listening
socket. Each address must be separated by a comma. If this value is left
blank, connections will be accepted from any ip address. Default value:
any. IPv6 addresses are allowed since PHP 5.5.20 and 5.6.4.

`listen.owner` <span class="type">string</span>  
Set permissions for unix socket, if one is used. In Linux, read/write
permissions must be set in order to allow connections from a web server.
Many BSD-derived systems allow connections regardless of permissions.
Default values: user and group are set as the running user, mode is set
to 0660.

`listen.group` <span class="type">string</span>  
See *listen.owner*.

`listen.mode` <span class="type">string</span>  
See *listen.owner*.

`listen.acl_users` <span class="type">string</span>  
When POSIX Access Control Lists are supported you can set them using
this option. When set, *listen.owner* and *listen.group* are ignored.
Value is a comma separated list of user names. Since PHP 5.6.5.

`listen.acl_groups` <span class="type">string</span>  
See *listen.acl\_users*. Value is a comma separated list of group names.
Since PHP 5.6.5.

`user` <span class="type">string</span>  
Unix user of FPM processes. This option is mandatory.

`group` <span class="type">string</span>  
Unix group of FPM processes. If not set, the default user's group is
used.

`pm` <span class="type">string</span>  
Choose how the process manager will control the number of child
processes. Possible values: *static*, *ondemand*, *dynamic*. This option
is mandatory.

*static* - the number of child processes is fixed (*pm.max\_children*).

*ondemand* - the processes spawn on demand (when requested, as opposed
to dynamic, where *pm.start\_servers* are started when the service is
started.

*dynamic* - the number of child processes is set dynamically based on
the following directives: *pm.max\_children*, *pm.start\_servers*,
*pm.min\_spare\_servers*, *pm.max\_spare\_servers*.

`pm.max_children` <span class="type">int</span>  
The number of child processes to be created when *pm* is set to *static*
and the maximum number of child processes to be created when *pm* is set
to *dynamic*. This option is mandatory.

This option sets the limit on the number of simultaneous requests that
will be served. Equivalent to the ApacheMaxClients directive with
mpm\_prefork and to the `PHP_FCGI_CHILDREN` environment variable in the
original PHP FastCGI.

`pm.start_servers` <span class="type">int</span>  
The number of child processes created on startup. Used only when *pm* is
set to *dynamic*. Default Value: min\_spare\_servers +
(max\_spare\_servers - min\_spare\_servers) / 2.

`pm.min_spare_servers` <span class="type">int</span>  
The desired minimum number of idle server processes. Used only when *pm*
is set to *dynamic*. Also mandatory in this case.

`pm.max_spare_servers` <span class="type">int</span>  
The desired maximum number of idle server processes. Used only when *pm*
is set to *dynamic*. Also mandatory in this case.

`pm.process_idle_timeout` <span class="type">mixed</span>  
The number of seconds after which an idle process will be killed. Used
only when *pm* is set to *ondemand*. Available units:
s(econds)(default), m(inutes), h(ours), or d(ays). Default value: 10s.

`pm.max_requests` <span class="type">int</span>  
The number of requests each child process should execute before
respawning. This can be useful to work around memory leaks in 3rd party
libraries. For endless request processing specify '0'. Equivalent to
`PHP_FCGI_MAX_REQUESTS`. Default value: 0.

`pm.status_path` <span class="type">string</span>  
The URI to view the FPM status page. If this value is not set, no URI
will be recognized as a status page. Default value: none.

`ping.path` <span class="type">string</span>  
The ping URI to call the monitoring page of FPM. If this value is not
set, no URI will be recognized as a ping page. This could be used to
test from outside that FPM is alive and responding. Please note that the
value must start with a leading slash (/).

`ping.response` <span class="type">string</span>  
This directive may be used to customize the response to a ping request.
The response is formatted as text/plain with a 200 response code.
Default value: pong.

`process.priority` <span class="type">int</span>  
Specify the nice(2) priority to apply to the worker process (only if
set). The value can vary from -19 (highest priority) to 20 (lower
priority). Default value: not set.

`process.dumpable` <span class="type">bool</span>  
Set the process dumpable flag (PR\_SET\_DUMPABLE prctl) even if the
process user or group is different than the master process user. It
allows to create process core dump and ptrace the process for the pool
user. Default Value: no. Since PHP 7.0.29, 7.1.17 and 7.2.5.

`prefix` <span class="type">string</span>  
Specify prefix for path evaluation

`request_terminate_timeout` <span class="type">mixed</span>  
The timeout for serving a single request after which the worker process
will be killed. This option should be used when the
'max\_execution\_time' ini option does not stop script execution for
some reason. A value of '0' means 'Off'. Available units:
s(econds)(default), m(inutes), h(ours), or d(ays). Default value: 0.

`request_slowlog_timeout` <span class="type">mixed</span>  
The timeout for serving a single request after which a PHP backtrace
will be dumped to the 'slowlog' file. A value of '0' means 'Off'.
Available units: s(econds)(default), m(inutes), h(ours), or d(ays).
Default value: 0.

`slowlog` <span class="type">string</span>  
The log file for slow requests. Default value:
*\#INSTALL\_PREFIX\#/log/php-fpm.log.slow*.

`rlimit_files` <span class="type">int</span>  
Set open file descriptor rlimit for child processes in this pool.
Default value: system defined value.

`rlimit_core` <span class="type">int</span>  
Set max core size rlimit for child processes in this pool. Possible
Values: 'unlimited' or an integer greater or equal to 0. Default value:
system defined value.

`chroot` <span class="type">string</span>  
Chroot to this directory at the start. This value must be defined as an
absolute path. When this value is not set, chroot is not used.

`chdir` <span class="type">string</span>  
Chdir to this directory at the start. This value must be an absolute
path. Default value: current directory or / when chroot.

`catch_workers_output` <span class="type">bool</span>  
Redirect worker stdout and stderr into main error log. If not set,
stdout and stderr will be redirected to /dev/null according to FastCGI
specs. Default value: no.

`decorate_workers_output` <span class="type">bool</span>  
Enable the output decoration for workers output when
<a href="/install/fpm/configuration.html#catch-workers-output" class="link">catch_workers_output</a>
is enabled. Default value: yes. Available as of PHP 7.3.0.

`clear_env` <span class="type">bool</span>  
Clear environment in FPM workers. Prevents arbitrary environment
variables from reaching FPM worker processes by clearing the environment
in workers before env vars specified in this pool configuration are
added. Since PHP 5.4.27, 5.5.11, and 5.6.0. Default value: Yes.

`security.limit_extensions` <span class="type">string</span>  
Limits the extensions of the main script FPM will allow to parse. This
can prevent configuration mistakes on the web server side. You should
only limit FPM to .php extensions to prevent malicious users to use
other extensions to execute php code. Default value: .php .phar

`access.log` <span class="type">string</span>  
The access log file. Default value: not set

`access.format` <span class="type">string</span>  
The access log format. Default value: "%R - %u %t \\"%m %r\\" %s"

It's possible to pass additional environment variables and update PHP
settings of a certain pool. To do this, you need to add the following
options to the pool configuration file.

**Example \#1 Passing environment variables and PHP settings to a pool**

``` ini
env[HOSTNAME] = $HOSTNAME
env[PATH] = /usr/local/bin:/usr/bin:/bin
env[TMP] = /tmp
env[TMPDIR] = /tmp
env[TEMP] = /tmp

php_admin_value[sendmail_path] = /usr/sbin/sendmail -t -i -f www@my.domain.com
php_flag[display_errors] = off
php_admin_value[error_log] = /var/log/fpm-php.www.log
php_admin_flag[log_errors] = on
php_admin_value[memory_limit] = 32M
```

PHP settings passed with *php\_value* or *php\_flag* will overwrite
their previous value. Please note that defining
<a href="/ini/core.html#ini.disable-functions" class="link">disable_functions</a>
or
<a href="/ini/core.html#ini.disable-classes" class="link">disable_classes</a>
will not overwrite previously defined `php.ini` values, but will append
the new value instead.

Settings defined with *php\_admin\_value* and *php\_admin\_flag* cannot
be overridden with <span class="function">ini\_set</span>.

As of 5.3.3, PHP settings are also possible to be set in webserver.

**Example \#2 set PHP settings in nginx.conf**

``` ini
set $php_value "pcre.backtrack_limit=424242";
set $php_value "$php_value \n pcre.recursion_limit=99999";
fastcgi_param  PHP_VALUE $php_value;

fastcgi_param  PHP_ADMIN_VALUE "open_basedir=/var/www/htdocs";
```

**Caution**

Because these settings are passed to php-fpm as fastcgi headers, php-fpm
should not be bound to a worldwide accessible address. Otherwise, anyone
could alter the PHP configuration options. See also
<a href="/install/fpm/configuration.html#listen-allowed-clients" class="link">listen.allowed_clients</a>.
