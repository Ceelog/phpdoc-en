General Installation Considerations
===================================

Before starting the installation, first you need to know what do you
want to use PHP for. There are three main fields you can use PHP, as
described in the
<a href="/intro-whatcando.html" class="link">What can PHP do?</a>
section:

-   <span class="simpara">Websites and web applications (server-side
    scripting)</span>
-   <span class="simpara">Command line scripting</span>
-   <span class="simpara">Desktop (GUI) applications</span>

For the first and most common form, you need three things: PHP itself, a
web server and a web browser. You probably already have a web browser,
and depending on your operating system setup, you may also have a web
server (e.g. Apache on Linux and macOS; IIS on Windows). You may also
rent webspace at a company. This way, you don't need to set up anything
on your own, only write your PHP scripts, upload it to the server you
rent, and see the results in your browser.

In case of setting up the server and PHP on your own, you have two
choices for the method of connecting PHP to the server. For many servers
PHP has a direct module interface (also called SAPI). These servers
include Apache, Microsoft Internet Information Server, Netscape and
iPlanet servers. Many other servers have support for ISAPI, the
Microsoft module interface (OmniHTTPd for example). If PHP has no module
support for your web server, you can always use it as a CGI or FastCGI
processor. This means you set up your server to use the CGI executable
of PHP to process all PHP file requests on the server.

If you are also interested in using PHP for command line scripting (e.g.
write scripts autogenerating some images for you offline, or processing
text files depending on some arguments you pass to them), you always
need the command line executable. For more information, read the section
about
<a href="/features/commandline.html" class="link">writing command line PHP applications</a>.
In this case, you need no server and no browser.

With PHP you can also write desktop GUI applications using the PHP-GTK
extension. This is a completely different approach than writing web
pages, as you do not output any HTML, but manage windows and objects
within them. For more information about PHP-GTK, please
<a href="http://gtk.php.net/" class="link external">» visit the site dedicated to this extension</a>.
PHP-GTK is not included in the official PHP distribution.

From now on, this section deals with setting up PHP for web servers on
Unix and Windows with server module interfaces and CGI executables. You
will also find information on the command line executable in the
following sections.

PHP source code and binary distributions for Windows can be found at
<a href="https://www.php.net/downloads.php" class="link external">» https://www.php.net/downloads.php</a>.
