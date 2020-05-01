The Seaslog is an effective,fast,stable log extension for PHP.

SeasLog requires PHP 5.2.0 or greater. Earlier versions may not work.

The log journal，which is usually the operate record of the system，
software and the application record. Through the analysis of the log，it
can facilitate users to understand the operation of the system，
software and the application situation. If your application log is rich
enough, it can also analyze the previous use’s operation behavior,type,
regional distribution or other more information. The application log
also points the multiple levels at the same time, you can easily get the
application analysis of health status, timely find problems and quick
positioning, and solve the problem, remedy the loss.

The error\_log, syslog function which built in PHP is powerful and
excellent performance, but due to various defects (error\_log have no
error level, no fixed format, syslog regardless of module, and mix with
system log ), reducing a lot of flexibility , and can't meet the
application requirements.

The good news is that there are a number of third-party log class
library established to make up for the defects, such as log4php, plog,
monolog (of course, there are many applications in the project
development of the log class).

So is there a log of libraries meet the following requirements：

-   Modules, classification
-   Simple configuration(preferably without configuration)
-   Clear log format and easy understanding
-   Simple application and well performance

Seaslog just meet these demands.

What is provided at present:

-   In the PHP project, record the log specification and repidly.
-   Configure the default log directory and module
-   Specified log directory and capture current configuration
-   Preliminary analysis of the early warning framework
-   Efficient log buffer and convenient buffer debug
-   Follow the PSR-3 log interface specification
-   Automatically record error information
-   Automatically record abnormal information
-   Support Connect the TCP port, send with RFC5424
-   Support Connect the UDP port, send with RFC5424
-   Support RequestId differentiated requests
-   Support for log template customizations

Read More
<a href="https://seasx.github.io/SeasLog/" class="link external">» SeasLog Document</a>
at Github.
