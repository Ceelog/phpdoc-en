Connection handling
===================

Internally in PHP a connection status is maintained. There are 4
possible states:

-   <span class="simpara">0 - NORMAL</span>
-   <span class="simpara">1 - ABORTED</span>
-   <span class="simpara">2 - TIMEOUT</span>
-   <span class="simpara">3 - ABORTED and TIMEOUT</span>

When a PHP script is running normally, the NORMAL state is active. If
the remote client disconnects, the ABORTED state flag is turned on. A
remote client disconnect is usually caused by users hitting their STOP
button. If the PHP-imposed time limit (see <span
class="function">set\_time\_limit</span>) is hit, the TIMEOUT state flag
is turned on.

You can decide whether or not you want a client disconnect to cause your
script to be aborted. Sometimes it is handy to always have your scripts
run to completion even if there is no remote browser receiving the
output. The default behaviour is however for your script to be aborted
when the remote client disconnects. This behaviour can be set via the
ignore\_user\_abort `php.ini` directive as well as through the
corresponding *php\_value ignore\_user\_abort* Apache `httpd.conf`
directive or with the <span class="function">ignore\_user\_abort</span>
function. If you do not tell PHP to ignore a user abort and the user
aborts, your script will terminate. The one exception is if you have
registered a shutdown function using <span
class="function">register\_shutdown\_function</span>. With a shutdown
function, when the remote user hits his STOP button, the next time your
script tries to output something PHP will detect that the connection has
been aborted and the shutdown function is called. This shutdown function
will also get called at the end of your script terminating normally, so
to do something different in case of a client disconnect you can use the
<span class="function">connection\_aborted</span> function. This
function will return **`true`** if the connection was aborted.

Your script can also be terminated by the built-in script timer. The
default timeout is 30 seconds. It can be changed using the
**max\_execution\_time** `php.ini` directive or the corresponding
*php\_value max\_execution\_time* Apache `httpd.conf` directive as well
as with the <span class="function">set\_time\_limit</span> function.
When the timer expires the script will be aborted and as with the above
client disconnect case, if a shutdown function has been registered it
will be called. Within this shutdown function you can check to see if a
timeout caused the shutdown function to be called by calling the <span
class="function">connection\_status</span> function. This function will
return 2 if a timeout caused the shutdown function to be called.

One thing to note is that both the ABORTED and the TIMEOUT states can be
active at the same time. This is possible if you tell PHP to ignore user
aborts. PHP will still note the fact that a user may have broken the
connection, but the script will keep running. If it then hits the time
limit it will be aborted and your shutdown function, if any, will be
called. At this point you will find that <span
class="function">connection\_status</span> returns 3.
