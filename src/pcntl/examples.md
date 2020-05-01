Examples
========

**Table of Contents**

-   [Basic usage](/pcntl/examples.html#Basic%20usage)

Basic usage
-----------

This example forks off a daemon process with a signal handler.

**Example \#1 Process Control Example**

``` php
<?php
declare(ticks=1);

$pid = pcntl_fork();
if ($pid == -1) {
     die("could not fork"); 
} else if ($pid) {
     exit(); // we are the parent 
} else {
     // we are the child
}

// detach from the controlling terminal
if (posix_setsid() == -1) {
    die("could not detach from terminal");
}

// setup signal handlers
pcntl_signal(SIGTERM, "sig_handler");
pcntl_signal(SIGHUP, "sig_handler");

// loop forever performing tasks
while (1) {

    // do something interesting here

}

function sig_handler($signo) 
{

     switch ($signo) {
         case SIGTERM:
             // handle shutdown tasks
             exit;
             break;
         case SIGHUP:
             // handle restart tasks
             break;
         default:
             // handle all other signals
     }

}

?>
```
