Create a file named `hello.php` and put it in your web server's root
directory (`DOCUMENT_ROOT`) with the following content:

**Example \#1 Our first PHP script: `hello.php`**

``` php
<html>
 <head>
  <title>PHP Test</title>
 </head>
 <body>
 <?php echo '<p>Hello World</p>'; ?> 
 </body>
</html>
```

Use your browser to access the file with your web server's URL, ending
with the */hello.php* file reference. When developing locally this URL
will be something like *http://localhost/hello.php* or
*http://127.0.0.1/hello.php* but this depends on the web server's
configuration. If everything is configured correctly, this file will be
parsed by PHP and the following output will be sent to your browser:

    <html>
     <head>
      <title>PHP Test</title>
     </head>
     <body>
     <p>Hello World</p>
     </body>
    </html>

This program is extremely simple and you really did not need to use PHP
to create a page like this. All it does is display: *Hello World* using
the PHP <span class="function">echo</span> statement. Note that the file
*does not need to be executable* or special in any way. The server finds
out that this file needs to be interpreted by PHP because you used the
".php" extension, which the server is configured to pass on to PHP.
Think of this as a normal HTML file which happens to have a set of
special tags available to you that do a lot of interesting things.

If you tried this example and it did not output anything, it prompted
for download, or you see the whole file as text, chances are that the
server you are on does not have PHP enabled, or is not configured
properly. Ask your administrator to enable it for you using the
<a href="/install.html" class="link">Installation</a> chapter of the
manual. If you are developing locally, also read the installation
chapter to make sure everything is configured properly. Make sure that
you access the file via http with the server providing you the output.
If you just call up the file from your file system, then it will not be
parsed by PHP. If the problems persist anyway, do not hesitate to use
one of the many
<a href="https://www.php.net/support.php" class="link external">» PHP support</a>
options.

The point of the example is to show the special PHP tag format. In this
example we used *\<?php* to indicate the start of a PHP tag. Then we put
the PHP statement and left PHP mode by adding the closing tag, *?\>*.
You may jump in and out of PHP mode in an HTML file like this anywhere
you want. For more details, read the manual section on the
<a href="/language/basic-syntax.html" class="link">basic PHP syntax</a>.

> **Note**: <span class="info">**A Note on Line Feeds**  
> </span>
>
> Line feeds have little meaning in HTML, however it is still a good
> idea to make your HTML look nice and clean by putting line feeds in. A
> linefeed that follows immediately after a closing *?\>* will be
> removed by PHP. This can be extremely useful when you are putting in
> many blocks of PHP or include files containing PHP that aren't
> supposed to output anything. At the same time it can be a bit
> confusing. You can put a space after the closing *?\>* to force a
> space and a line feed to be output, or you can put an explicit line
> feed in the last echo/print from within your PHP block.

> **Note**: <span class="info">**A Note on Text Editors**  
> </span>
>
> There are many text editors and Integrated Development Environments
> (IDEs) that you can use to create, edit and manage PHP files. A
> partial list of these tools is maintained at
> <a href="http://en.wikipedia.org/wiki/List_of_PHP_editors" class="link external">» PHP Editors List</a>.
> If you wish to recommend an editor, please visit the above page and
> ask the page maintainer to add the editor to the list. Having an
> editor with syntax highlighting can be helpful.

> **Note**: <span class="info">**A Note on Word Processors**  
> </span>
>
> Word processors such as StarOffice Writer, Microsoft Word and Abiword
> are not optimal for editing PHP files. If you wish to use one for this
> test script, you must ensure that you save the file as *plain text* or
> PHP will not be able to read and execute the script.

> **Note**: <span class="info">**A Note on Windows Notepad**  
> </span>
>
> If you are writing your PHP scripts using Windows Notepad, you will
> need to ensure that your files are saved with the `.php` extension.
> (Notepad adds a `.txt` extension to files automatically unless you
> take one of the following steps to prevent it.) When you save the file
> and are prompted to provide a name for the file, place the filename in
> quotes (i.e. "`hello.php`"). Alternatively, you can click on the 'Text
> Documents' drop-down menu in the 'Save' dialog box and change the
> setting to "All Files". You can then enter your filename without
> quotes.

Now that you have successfully created a working PHP script, it is time
to create the most famous PHP script! Make a call to the <span
class="function">phpinfo</span> function and you will see a lot of
useful information about your system and setup such as available
<a href="/language/variables/predefined.html" class="link">predefined variables</a>,
loaded PHP modules, and
<a href="/configuration.html" class="link">configuration</a> settings.
Take some time and review this important information.

**Example \#2 Get system information from PHP**

``` php
<?php phpinfo(); ?>
```
