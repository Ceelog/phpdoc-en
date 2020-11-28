Command line options
--------------------

The list of command line options provided by the PHP binary can be
queried at any time by running PHP with the **-h** switch:

    Usage: php [options] [-f] <file> [--] [args...]
       php [options] -r <code> [--] [args...]
       php [options] [-B <begin_code>] -R <code> [-E <end_code>] [--] [args...]
       php [options] [-B <begin_code>] -F <file> [-E <end_code>] [--] [args...]
       php [options] -- [args...]
       php [options] -a

      -a               Run interactively
      -c <path>|<file> Look for php.ini file in this directory
      -n               No php.ini file will be used
      -d foo[=bar]     Define INI entry foo with value 'bar'
      -e               Generate extended information for debugger/profiler
      -f <file>        Parse and execute <file>.
      -h               This help
      -i               PHP information
      -l               Syntax check only (lint)
      -m               Show compiled in modules
      -r <code>        Run PHP <code> without using script tags <?..?>
      -B <begin_code>  Run PHP <begin_code> before processing input lines
      -R <code>        Run PHP <code> for every input line
      -F <file>        Parse and execute <file> for every input line
      -E <end_code>    Run PHP <end_code> after processing all input lines
      -H               Hide any passed arguments from external tools.
      -S <addr>:<port> Run with built-in web server.
      -t <docroot>     Specify document root <docroot> for built-in web server.
      -s               Output HTML syntax highlighted source.
      -v               Version number
      -w               Output source with stripped comments and whitespace.
      -z <file>        Load Zend extension <file>.

      args...          Arguments passed to script. Use -- args when first argument
                       starts with - or script is read from stdin

      --ini            Show configuration file names

      --rf <name>      Show information about function <name>.
      --rc <name>      Show information about class <name>.
      --re <name>      Show information about extension <name>.
      --rz <name>      Show information about Zend extension <name>.
      --ri <name>      Show configuration for extension <name>.

<table>
<caption><strong>Command line options</strong></caption>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Long Option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>-a</td>
<td>--interactive</td>
<td><p>Run PHP interactively. For more information, see the <a href="/features/commandline/interactive.html" class="link">Interactive shell</a> section.</p></td>
</tr>
<tr class="even">
<td>-b</td>
<td>--bindpath</td>
<td><p>Bind Path for external FASTCGI Server mode (CGI only).</p></td>
</tr>
<tr class="odd">
<td>-C</td>
<td>--no-chdir</td>
<td><p>Do not chdir to the script's directory (CGI only).</p></td>
</tr>
<tr class="even">
<td>-q</td>
<td>--no-header</td>
<td><p>Quiet-mode. Suppress HTTP header output (CGI only).</p></td>
</tr>
<tr class="odd">
<td>-T</td>
<td>--timing</td>
<td><p>Measure execution time of script repeated <var class="varname">count</var> times (CGI only).</p></td>
</tr>
<tr class="even">
<td>-c</td>
<td>--php-ini</td>
<td><p>Specifies either a directory in which to look for <var class="filename">php.ini</var>, or a custom <em>INI</em> file (which does not need to be named <var class="filename">php.ini</var>), e.g.:</p>
<div class="informalexample">
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -c /custom/directory/ my_script.php

$ php -c /custom/directory/custom-file.ini my_script.php</code></pre>
</div>
</div>
</div>
<p>If this option is not specified, <var class="filename">php.ini</var> is searched for in the <a href="/configuration/file.html" class="link">default locations</a>.</p></td>
</tr>
<tr class="odd">
<td>-n</td>
<td>--no-php-ini</td>
<td><p>Ignore <var class="filename">php.ini</var> completely.</p></td>
</tr>
<tr class="even">
<td>-d</td>
<td>--define</td>
<td><p>Set a custom value for any of the configuration directives allowed in <var class="filename">php.ini</var>. The syntax is:</p>
<div class="example-contents screen">
<div class="cdata">
<pre><code> -d configuration_directive[=value]
 </code></pre>
</div>
</div>
<div id="example-415" class="example">
<div class="example-contents screen">
<div class="cdata">
<pre><code># Omitting the value part will set the given configuration directive to &quot;1&quot;
$ php -d max_execution_time
        -r &#39;$foo = ini_get(&quot;max_execution_time&quot;); var_dump($foo);&#39;
string(1) &quot;1&quot;

# Passing an empty value part will set the configuration directive to &quot;&quot;
php -d max_execution_time=
        -r &#39;$foo = ini_get(&quot;max_execution_time&quot;); var_dump($foo);&#39;
string(0) &quot;&quot;

# The configuration directive will be set to anything passed after the &#39;=&#39; character
$  php -d max_execution_time=20
        -r &#39;$foo = ini_get(&quot;max_execution_time&quot;); var_dump($foo);&#39;
string(2) &quot;20&quot;
$  php
        -d max_execution_time=doesntmakesense
        -r &#39;$foo = ini_get(&quot;max_execution_time&quot;); var_dump($foo);&#39;
string(15) &quot;doesntmakesense&quot;</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td>-e</td>
<td>--profile-info</td>
<td><p>Activate the extended information mode, to be used by a debugger/profiler.</p></td>
</tr>
<tr class="even">
<td>-f</td>
<td>--file</td>
<td><p>Parse and execute the specified file. The <strong>-f</strong> is optional and may be omitted - providing just the filename to execute is sufficient.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>To pass arguments to a script, the first argument must be <em>--</em>, otherwise PHP will interpret them as PHP options.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td>-h and -?</td>
<td>--help and --usage</td>
<td>Output a list of command line options with one line descriptions of what they do.</td>
</tr>
<tr class="even">
<td>-i</td>
<td>--info</td>
<td>Calls <span class="function">phpinfo</span>, and prints out the results. If PHP is not working correctly, it is advisable to use the command <strong>php -i</strong> and see whether any error messages are printed out before or in place of the information tables. Beware that when using the CGI mode the output is in HTML and therefore very large.</td>
</tr>
<tr class="odd">
<td>-l</td>
<td>--syntax-check</td>
<td><p>Provides a convenient way to perform only a syntax check on the given PHP code. On success, the text <em>No syntax errors detected in &lt;filename&gt;</em> is written to standard output and the shell return code is <em>0</em>. On failure, the text <em>Errors parsing &lt;filename&gt;</em> in addition to the internal parser error message is written to standard output and the shell return code is set to <em>-1</em>.</p>
<p>This option won't find fatal errors (like undefined functions). Use the <strong>-f</strong> to test for fatal errors too.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>This option does not work together with the <strong>-r</strong> option.</p>
</blockquote></td>
</tr>
<tr class="even">
<td>-m</td>
<td>--modules</td>
<td><div id="example-416" class="example">
<p><strong>Example #1 Printing built in (and loaded) PHP and Zend modules</strong></p>
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -m
[PHP Modules]
xml
tokenizer
standard
session
posix
pcre
overload
mysql
mbstring
ctype

[Zend Modules]</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td>-r</td>
<td>--run</td>
<td><p>Allows execution of PHP included directly on the command line. The PHP start and end tags (<em>&lt;?php</em> and <em>?&gt;</em>) are <em>not needed</em> and will cause a parse error if present.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>Care must be taken when using this form of PHP not to collide with command line variable substitution done by the shell.</p>
<div id="example-417" class="example">
<p><strong>Example #2 Getting a syntax error when using double quotes</strong></p>
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -r &quot;$foo = get_defined_constants();&quot;
PHP Parse error:  syntax error, unexpected &#39;=&#39; in Command line code on line 1

Parse error: syntax error, unexpected &#39;=&#39; in Command line code on line 1</code></pre>
</div>
</div>
</div>
<p>The problem here is that sh/bash performs variable substitution even when using double quotes <em>"</em>. Since the variable <var class="varname">$foo</var> is unlikely to be defined, it expands to nothing which results in the code passed to PHP for execution actually reading:</p>
<div class="informalexample">
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -r &quot; = get_defined_constants();&quot;</code></pre>
</div>
</div>
</div>
<p>The correct way would be to use single quotes <em>'</em>. Variables in single-quoted strings are not expanded by sh/bash.</p>
<div id="example-418" class="example">
<p><strong>Example #3 Using single quotes to prevent the shell's variable substitution</strong></p>
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -r &#39;$foo = get_defined_constants(); var_dump($foo);&#39;
array(370) {
  [&quot;E_ERROR&quot;]=&gt;
  int(1)
  [&quot;E_WARNING&quot;]=&gt;
  int(2)
  [&quot;E_PARSE&quot;]=&gt;
  int(4)
  [&quot;E_NOTICE&quot;]=&gt;
  int(8)
  [&quot;E_CORE_ERROR&quot;]=&gt;
  [...]</code></pre>
</div>
</div>
</div>
<p>If using a shell other than sh/bash, further issues might be experienced - if appropriate, a bug report should be opened at <a href="https://bugs.php.net/" class="link external">» https://bugs.php.net/</a>. It is still easy to run into trouble when trying to use variables (shell or PHP) in command-line code, or using backslashes for escaping, so take great care when doing so. You have been warned!</p>
</blockquote>
<blockquote>
<p><strong>Note</strong>:</p>
<p><strong>-r</strong> is available in the CLI SAPI, but not in the <em>CGI</em> SAPI.</p>
</blockquote>
<blockquote>
<p><strong>Note</strong>:</p>
<p>This option is only intended for very basic code, so some configuration directives (such as <a href="/ini/core.html#ini.auto-prepend-file" class="link">auto_prepend_file</a> and <a href="/ini/core.html#ini.auto-append-file" class="link">auto_append_file</a>) are ignored in this mode.</p>
</blockquote></td>
</tr>
<tr class="even">
<td>-B</td>
<td>--process-begin</td>
<td><p>PHP code to execute before processing stdin. Added in PHP 5.</p></td>
</tr>
<tr class="odd">
<td>-R</td>
<td>--process-code</td>
<td><p>PHP code to execute for every input line. Added in PHP 5.</p>
<p>There are two special variables available in this mode: <var class="varname">$argn</var> and <var class="varname">$argi</var>. <var class="varname">$argn</var> will contain the line PHP is processing at that moment, while <var class="varname">$argi</var> will contain the line number.</p></td>
</tr>
<tr class="even">
<td>-F</td>
<td>--process-file</td>
<td><p>PHP file to execute for every input line. Added in PHP 5.</p></td>
</tr>
<tr class="odd">
<td>-E</td>
<td>--process-end</td>
<td><p>PHP code to execute after processing the input. Added in PHP 5.</p>
<div id="example-419" class="example">
<p><strong>Example #4 Using the <strong>-B</strong>, <strong>-R</strong> and <strong>-E</strong> options to count the number of lines of a project.</strong></p>
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ find my_proj | php -B &#39;$l=0;&#39; -R &#39;$l += count(@file($argn));&#39; -E &#39;echo &quot;Total Lines: $l\n&quot;;&#39;
Total Lines: 37328</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="even">
<td>-S</td>
<td>--server</td>
<td><p>Starts <a href="/features/commandline/webserver.html" class="link">built-in web server</a>. Available as of PHP 5.4.0.</p></td>
</tr>
<tr class="odd">
<td>-t</td>
<td>--docroot</td>
<td>Specifies document root for <a href="/features/commandline/webserver.html" class="link">built-in web server</a>. Available as of PHP 5.4.0.</td>
</tr>
<tr class="even">
<td>-s</td>
<td>--syntax-highlight and --syntax-highlighting</td>
<td><p>Display colour syntax highlighted source.</p>
<p>This option uses the internal mechanism to parse the file and writes an HTML highlighted version of it to standard output. Note that all it does is generate a block of <em>&lt;code&gt; [...] &lt;/code&gt;</em> HTML tags, no HTML headers.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>This option does not work together with the <strong>-r</strong> option.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td>-v</td>
<td>--version</td>
<td><div id="example-420" class="example">
<p><strong>Example #5 Using <strong>-v</strong> to get the SAPI name and the version of PHP and Zend</strong></p>
<div class="example-contents screen">
<div class="cdata">
<pre><code>$ php -v
PHP 5.3.1 (cli) (built: Dec 11 2009 19:55:07)
Copyright (c) 1997-2009 The PHP Group
Zend Engine v2.3.0, Copyright (c) 1998-2009 Zend Technologies</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="even">
<td>-w</td>
<td>--strip</td>
<td><p>Display source with comments and whitespace stripped.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>This option does not work together with the <strong>-r</strong> option.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td>-z</td>
<td>--zend-extension</td>
<td><p>Load Zend extension. If only a filename is given, PHP tries to load this extension from the current default library path on your system (usually <var class="filename">/etc/ld.so.conf</var> on Linux systems, for example). Passing a filename with an absolute path will not use the system's library search path. A relative filename including directory information will tell PHP to try loading the extension relative to the current directory.</p></td>
</tr>
<tr class="even">
<td> </td>
<td>--ini</td>
<td><p>Show configuration file names and scanned directories. Available as of PHP 5.2.3.</p>
<div id="example-421" class="example">
<p><strong>Example #6 <em>--ini</em> example</strong></p>
<div class="example-contents">
<div class="shellcode">
<pre class="shell"><code>$ php --ini
Configuration File (php.ini) Path: /usr/dev/php/5.2/lib
Loaded Configuration File:         /usr/dev/php/5.2/lib/php.ini
Scan for additional .ini files in: (none)
Additional .ini files parsed:      (none)</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td>--rf</td>
<td>--rfunction</td>
<td><p>Show information about the given function or class method (e.g. number and name of the parameters). Available as of PHP 5.1.2.</p>
<p>This option is only available if PHP was compiled with <a href="/book/reflection.html" class="link">Reflection</a> support.</p>
<div id="example-422" class="example">
<p><strong>Example #7 basic <em>--rf</em> usage</strong></p>
<div class="example-contents">
<div class="shellcode">
<pre class="shell"><code>$ php --rf var_dump
Function [ &lt;internal&gt; public function var_dump ] {

  - Parameters [2] {
    Parameter #0 [ &lt;required&gt; $var ]
    Parameter #1 [ &lt;optional&gt; $... ]
  }
}</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="even">
<td>--rc</td>
<td>--rclass</td>
<td><p>Show information about the given class (list of constants, properties and methods). Available as of PHP 5.1.2.</p>
<p>This option is only available if PHP was compiled with <a href="/book/reflection.html" class="link">Reflection</a> support.</p>
<div id="example-423" class="example">
<p><strong>Example #8 <em>--rc</em> example</strong></p>
<div class="example-contents">
<div class="shellcode">
<pre class="shell"><code>$ php --rc Directory
Class [ &lt;internal:standard&gt; class Directory ] {

  - Constants [0] {
  }

  - Static properties [0] {
  }

  - Static methods [0] {
  }

  - Properties [0] {
  }

  - Methods [3] {
    Method [ &lt;internal&gt; public method close ] {
    }

    Method [ &lt;internal&gt; public method rewind ] {
    }

    Method [ &lt;internal&gt; public method read ] {
    }
  }
}</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td>--re</td>
<td>--rextension</td>
<td><p>Show information about the given extension (list of <var class="filename">php.ini</var> options, defined functions, constants and classes). Available as of PHP 5.1.2.</p>
<p>This option is only available if PHP was compiled with <a href="/book/reflection.html" class="link">Reflection</a> support.</p>
<div id="example-424" class="example">
<p><strong>Example #9 <em>--re</em> example</strong></p>
<div class="example-contents">
<div class="shellcode">
<pre class="shell"><code>$ php --re json
Extension [ &lt;persistent&gt; extension #19 json version 1.2.1 ] {

  - Functions {
    Function [ &lt;internal&gt; function json_encode ] {
    }
    Function [ &lt;internal&gt; function json_decode ] {
    }
  }
}</code></pre>
</div>
</div>
</div></td>
</tr>
<tr class="even">
<td>--rz</td>
<td>--rzendextension</td>
<td><p>Show the configuration information for the given Zend extension (the same information that is returned by <span class="function">phpinfo</span>). Available as of PHP 5.4.0.</p></td>
</tr>
<tr class="odd">
<td>--ri</td>
<td>--rextinfo</td>
<td><p>Show the configuration information for the given extension (the same information that is returned by <span class="function">phpinfo</span>). Available as of PHP 5.2.2. The core configuration information is available using "main" as extension name.</p>
<div id="example-425" class="example">
<p><strong>Example #10 <em>--ri</em> example</strong></p>
<div class="example-contents">
<div class="shellcode">
<pre class="shell"><code>$ php --ri date

date

date/time support =&gt; enabled
&quot;Olson&quot; Timezone Database Version =&gt; 2009.20
Timezone Database =&gt; internal
Default timezone =&gt; Europe/Oslo

Directive =&gt; Local Value =&gt; Master Value
date.timezone =&gt; Europe/Oslo =&gt; Europe/Oslo
date.default_latitude =&gt; 59.930972 =&gt; 59.930972
date.default_longitude =&gt; 10.776699 =&gt; 10.776699
date.sunset_zenith =&gt; 90.583333 =&gt; 90.583333
date.sunrise_zenith =&gt; 90.583333 =&gt; 90.583333</code></pre>
</div>
</div>
</div></td>
</tr>
</tbody>
</table>

> **Note**:
>
> Options *-rBRFEH*, *--ini* and *--r\[fcezi\]* are available only in
> CLI.
