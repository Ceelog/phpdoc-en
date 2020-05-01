Using remote files
==================

As long as **allow\_url\_fopen** is enabled in `php.ini`, you can use
HTTP and FTP URLs with most of the functions that take a filename as a
parameter. In addition, URLs can be used with the <span
class="function">include</span>, <span
class="function">include\_once</span>, <span
class="function">require</span> and <span
class="function">require\_once</span> statements (since PHP 5.2.0,
**allow\_url\_include** must be enabled for these). See
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for more information about the protocols supported by PHP.

For example, you can use this to open a file on a remote web server,
parse the output for the data you want, and then use that data in a
database query, or simply to output it in a style matching the rest of
your website.

**Example \#1 Getting the title of a remote page**

``` php
<?php
$file = fopen ("http://www.example.com/", "r");
if (!$file) {
    echo "<p>Unable to open remote file.\n";
    exit;
}
while (!feof ($file)) {
    $line = fgets ($file, 1024);
    /* This only works if the title and its tags are on one line */
    if (preg_match ("@\<title\>(.*)\</title\>@i", $line, $out)) {
        $title = $out[1];
        break;
    }
}
fclose($file);
?>
```

You can also write to files on an FTP server (provided that you have
connected as a user with the correct access rights). You can only create
new files using this method; if you try to overwrite a file that already
exists, the <span class="function">fopen</span> call will fail.

To connect as a user other than 'anonymous', you need to specify the
username (and possibly password) within the URL, such as
'*ftp://user:password@ftp.example.com/path/to/file*'. (You can use the
same sort of syntax to access files via HTTP when they require Basic
authentication.)

**Example \#2 Storing data on a remote server**

``` php
<?php
$file = fopen ("ftp://ftp.example.com/incoming/outputfile", "w");
if (!$file) {
    echo "<p>Unable to open remote file for writing.\n";
    exit;
}
/* Write the data here. */
fwrite ($file, $_SERVER['HTTP_USER_AGENT'] . "\n");
fclose ($file);
?>
```

> **Note**:
>
> You might get the idea from the example above that you can use this
> technique to write to a remote log file. Unfortunately that would not
> work because the <span class="function">fopen</span> call will fail if
> the remote file already exists. To do distributed logging like that,
> you should take a look at <span class="function">syslog</span>.
