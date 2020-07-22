Built-in web server
-------------------

**Warning**

This web server was designed to aid application development. It may also
be useful for testing purposes or for application demonstrations that
are run in controlled environments. It is not intended to be a
full-featured web server. It should not be used on a public network.

As of PHP 5.4.0, the CLI SAPI provides a built-in web server.

The web server runs only one single-threaded process, so PHP
applications will stall if a request is blocked.

URI requests are served from the current working directory where PHP was
started, unless the -t option is used to specify an explicit document
root. If a URI request does not specify a file, then either index.php or
index.html in the given directory are returned. If neither file exists,
the lookup for index.php and index.html will be continued in the parent
directory and so on until one is found or the document root has been
reached. If an index.php or index.html is found, it is returned and
$\_SERVER\['PATH\_INFO'\] is set to the trailing part of the URI.
Otherwise a 404 response code is returned.

If a PHP file is given on the command line when the web server is
started it is treated as a "router" script. The script is run at the
start of each HTTP request. If this script returns **`FALSE`**, then the
requested resource is returned as-is. Otherwise the script's output is
returned to the browser.

Standard MIME types are returned for files with extensions: .3gp, .apk,
.avi, .bmp, .css, .csv, .doc, .docx, .flac, .gif, .gz, .gzip, .htm,
.html, .ics, .jpe, .jpeg, .jpg, .js, .kml, .kmz, .m4a, .mov, .mp3, .mp4,
.mpeg, .mpg, .odp, .ods, .odt, .oga, .ogg, .ogv, .pdf, .pdf, .png, .pps,
.pptx, .qt, .svg, .swf, .tar, .text, .tif, .txt, .wav, .webm, .wmv,
.xls, .xlsx, .xml, .xsl, .xsd, and .zip.

| Version | Description                                                                                                                                                                                                                     |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.5.12  | .xml, .xsl, and .xsd                                                                                                                                                                                                            |
| 5.5.7   | .3gp, .apk, .avi, .bmp, .csv, .doc, .docx, .flac, .gz, .gzip, .ics, .kml, .kmz, .m4a, .mp3, .mp4, .mpg, .mpeg, .mov, .odp, .ods, .odt, .oga, .pdf, .pptx, .pps, .qt, .swf, .tar, .text, .tif, .wav, .wmv, .xls, .xlsx, and .zip |
| 5.5.5   | .pdf                                                                                                                                                                                                                            |
| 5.4.11  | .ogg, .ogv, and .webm                                                                                                                                                                                                           |
| 5.4.4   | .htm and .svg                                                                                                                                                                                                                   |

| Version | Description                                                                                                                                                                                                                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | You can configure the built-in webserver to fork multiple workers in order to test code that requires multiple concurrent requests to the built-in webserver. Set the `PHP_CLI_SERVER_WORKERS` environment variable to the number of desired workers before starting the server. This is not supported on Windows. |

**Example \#1 Starting the web server**

``` shell
$ cd ~/public_html
$ php -S localhost:8000
```

The terminal will show:

    PHP 5.4.0 Development Server started at Thu Jul 21 10:43:28 2011
    Listening on localhost:8000
    Document root is /home/me/public_html
    Press Ctrl-C to quit

After URI requests for http://localhost:8000/ and
http://localhost:8000/myscript.html the terminal will show something
similar to:

    PHP 5.4.0 Development Server started at Thu Jul 21 10:43:28 2011
    Listening on localhost:8000
    Document root is /home/me/public_html
    Press Ctrl-C to quit.
    [Thu Jul 21 10:48:48 2011] ::1:39144 GET /favicon.ico - Request read
    [Thu Jul 21 10:48:50 2011] ::1:39146 GET / - Request read
    [Thu Jul 21 10:48:50 2011] ::1:39147 GET /favicon.ico - Request read
    [Thu Jul 21 10:48:52 2011] ::1:39148 GET /myscript.html - Request read
    [Thu Jul 21 10:48:52 2011] ::1:39149 GET /favicon.ico - Request read

Note that prior to PHP 7.4.0, symlinked statical resources have not been
accessible on Windows, unless the router script would handle these.

**Example \#2 Starting with a specific document root directory**

``` shell
$ cd ~/public_html
$ php -S localhost:8000 -t foo/
```

The terminal will show:

    PHP 5.4.0 Development Server started at Thu Jul 21 10:50:26 2011
    Listening on localhost:8000
    Document root is /home/me/public_html/foo
    Press Ctrl-C to quit

**Example \#3 Using a Router Script**

In this example, requests for images will display them, but requests for
HTML files will display "Welcome to PHP":

``` php
<?php
// router.php
if (preg_match('/\.(?:png|jpg|jpeg|gif)$/', $_SERVER["REQUEST_URI"])) {
    return false;    // serve the requested resource as-is.
} else { 
    echo "<p>Welcome to PHP</p>";
}
?>
```

``` shell
$ php -S localhost:8000 router.php
```

**Example \#4 Checking for CLI Web Server Use**

To reuse a framework router script during development with the CLI web
server and later also with a production web server:

``` php
<?php
// router.php
if (php_sapi_name() == 'cli-server') {
    /* route static assets and return false */
}
/* go on with normal index.php operations */
?>
```

``` shell
$ php -S localhost:8000 router.php
```

**Example \#5 Handling Unsupported File Types**

If you need to serve a static resource whose MIME type is not handled by
the CLI web server, use:

``` php
<?php
// router.php
$path = pathinfo($_SERVER["SCRIPT_FILENAME"]);
if ($path["extension"] == "el") {
    header("Content-Type: text/x-script.elisp");
    readfile($_SERVER["SCRIPT_FILENAME"]);
}
else {
    return FALSE;
}
?>
```

``` shell
$ php -S localhost:8000 router.php
```

**Example \#6 Accessing the CLI Web Server From Remote Machines**

You can make the web server accessible on port 8000 to any interface
with:

``` shell
$ php -S 0.0.0.0:8000
```
