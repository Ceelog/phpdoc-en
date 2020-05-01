HTTP Input and Output
=====================

HTTP input/output character encoding conversion may convert binary data
also. Users are supposed to control character encoding conversion if
binary data is used for HTTP input/output.

> **Note**:
>
> If *enctype* for HTML form is set to *multipart/form-data* and
> *mbstring.encoding\_translation* is set to On in `php.ini` the POST'ed
> variables and the names of uploaded files will be converted to the
> internal character encoding as well. However, the conversion isn't
> applied to the query keys.

-   <span class="simpara"> HTTP Input </span>

    There is no way to control HTTP input character conversion from a
    PHP script. To disable HTTP input character conversion, it has to be
    done in `php.ini`.

    **Example \#1 Disable HTTP input conversion in `php.ini`**

    ``` php.ini
    ;; Disable HTTP Input conversion
    mbstring.http_input = pass
    ;; Disable HTTP Input conversion
    mbstring.encoding_translation = Off
    ```

    When using PHP as an Apache module, it is possible to override those
    settings in each Virtual Host directive in `httpd.conf` or per
    directory with `.htaccess`. Refer to the
    <a href="/configuration.html" class="link">Configuration</a> section
    and Apache Manual for details.

-   <span class="simpara"> HTTP Output </span>

    There are several ways to enable output character encoding
    conversion. One is using `php.ini`, another is using <span
    class="function">ob\_start</span> with <span
    class="function">mb\_output\_handler</span> as the *ob\_start*
    callback function.

**Example \#2 `php.ini` setting example**

    ;; Enable output character encoding conversion for all PHP pages

    ;; Enable Output Buffering
    output_buffering    = On

    ;; Set mb_output_handler to enable output conversion
    output_handler      = mb_output_handler

**Example \#3 Script example**

``` php
<?php

// Enable output character encoding conversion only for this page

// Set HTTP output character encoding to SJIS
mb_http_output('SJIS');

// Start buffering and specify "mb_output_handler" as
// callback function
ob_start('mb_output_handler');

?>
```
