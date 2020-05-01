Introduction
============

PHP is a powerful language and the interpreter, whether included in a
web server as a module or executed as a separate CGI binary, is able to
access files, execute commands and open network connections on the
server. These properties make anything run on a web server insecure by
default. PHP is designed specifically to be a more secure language for
writing CGI programs than Perl or C, and with correct selection of
compile-time and runtime configuration options, and proper coding
practices, it can give you exactly the combination of freedom and
security you need.

As there are many different ways of utilizing PHP, there are many
configuration options controlling its behaviour. A large selection of
options guarantees you can use PHP for a lot of purposes, but it also
means there are combinations of these options and server configurations
that result in an insecure setup.

The configuration flexibility of PHP is equally rivalled by the code
flexibility. PHP can be used to build complete server applications, with
all the power of a shell user, or it can be used for simple server-side
includes with little risk in a tightly controlled environment. How you
build that environment, and how secure it is, is largely up to the PHP
developer.

This chapter starts with some general security advice, explains the
different configuration option combinations and the situations they can
be safely used, and describes different considerations in coding for
different levels of security.
