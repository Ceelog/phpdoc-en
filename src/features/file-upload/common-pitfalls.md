Common Pitfalls
---------------

The *MAX\_FILE\_SIZE* item cannot specify a file size greater than the
file size that has been set in the
<a href="/ini/core.html#ini.upload-max-filesize" class="link">upload_max_filesize</a>
in the `php.ini` file. The default is 2 megabytes.

If a memory limit is enabled, a larger
<a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>
may be needed. Make sure you set
<a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>
large enough.

If <a href="/info/setup.html#" class="link">max_execution_time</a> is
set too small, script execution may be exceeded by the value. Make sure
you set *max\_execution\_time* large enough.

> **Note**: <span class="simpara">
> <a href="/info/setup.html#" class="link">max_execution_time</a> only
> affects the execution time of the script itself. Any time spent on
> activity that happens outside the execution of the script such as
> system calls using <span class="function">system</span>, the <span
> class="function">sleep</span> function, database queries, time taken
> by the file upload process, etc. is not included when determining the
> maximum time that the script has been running. </span>

**Warning**

<a href="/info/setup.html#" class="link">max_input_time</a> sets the
maximum time, in seconds, the script is allowed to receive input; this
includes file uploads. For large or multiple files, or users on slower
connections, the default of *60 seconds* may be exceeded.

If
<a href="/ini/core.html#ini.post-max-size" class="link">post_max_size</a>
is set too small, large files cannot be uploaded. Make sure you set
*post\_max\_size* large enough.

As of PHP 5.2.12, the
<a href="/ini/core.html#ini.max-file-uploads" class="link">max_file_uploads</a>
configuration setting controls the maximum number of files that can
uploaded in one request. If more files are uploaded than the limit, then
`$_FILES` will stop processing files once the limit is reached. For
example, if
<a href="/ini/core.html#ini.max-file-uploads" class="link">max_file_uploads</a>
is set to *10*, then `$_FILES` will never contain more than 10 items.

Not validating which file you operate on may mean that users can access
sensitive information in other directories.

Please note that the <span class="productname">CERN httpd</span> seems
to strip off everything starting at the first whitespace in the
content-type mime header it gets from the client. As long as this is the
case, <span class="productname">CERN httpd</span> will not support the
file upload feature.

Due to the large amount of directory listing styles we cannot guarantee
that files with exotic names (like containing spaces) are handled
properly.

A developer may not mix normal *input* fields and file upload fields in
the same form variable (by using an *input* name like *foo\[\]*).
