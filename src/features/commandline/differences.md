Differences to other SAPIs
--------------------------

Remarkable differences of the CLI SAPI compared to other SAPIs:

-   Unlike the CGI SAPI, no headers are written to the output.

    Though the CGI SAPI provides a way to suppress HTTP headers, there's
    no equivalent switch to enable them in the CLI SAPI.

    CLI is started up in quiet mode by default, though the **-q** and
    **--no-header** switches are kept for compatibility so that it is
    possible to use older CGI scripts.

    It does not change the working directory to that of the script.
    (**-C** and **--no-chdir** switches kept for compatibility)

    Plain text error messages (no HTML formatting).

-   There are certain `php.ini` directives which are overridden by the
    CLI SAPI because they do not make sense in shell environments:

    <table>
    <caption><strong>Overridden <var class="filename">php.ini</var> directives</strong></caption>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Directive</th>
    <th>CLI SAPI default value</th>
    <th>Comment</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><a href="/errorfunc/setup.html#" class="link">html_errors</a></td>
    <td><strong><code>FALSE</code></strong></td>
    <td>Defaults to <strong><code>FALSE</code></strong>, as it can be quite hard to read error messages in the shell environment when they are cluttered up with uninterpreted HTML tags.</td>
    </tr>
    <tr class="even">
    <td><a href="/outcontrol/setup.html#" class="link">implicit_flush</a></td>
    <td><strong><code>TRUE</code></strong></td>
    <td>In a shell environment, it is usually desirable for output, such as from <span class="function">print</span>, <span class="function">echo</span> and friends, to be displayed immediately, and not held in a buffer. Nonetheless, it is still possible to use <a href="/ref/outcontrol.html" class="link">output buffering</a> to defer or manipulate standard output.</td>
    </tr>
    <tr class="odd">
    <td><a href="/info/setup.html#" class="link">max_execution_time</a></td>
    <td>0 (unlimited)</td>
    <td>PHP in a shell environment tends to be used for a much more diverse range of purposes than typical Web-based scripts, and as these can be very long-running, the maximum execution time is set to unlimited.</td>
    </tr>
    <tr class="even">
    <td><a href="/ini/core.html#ini.register-argc-argv" class="link">register_argc_argv</a></td>
    <td><strong><code>TRUE</code></strong></td>
    <td><p>Setting this to <strong><code>TRUE</code></strong> means that scripts executed via the CLI SAPI always have access to <em>argc</em> (number of arguments passed to the application) and <em>argv</em> (array of the actual arguments).</p>
    <p>The PHP variables <var class="varname">$argc</var> and <var class="varname">$argv</var> are automatically set to the appropriate values when using the CLI SAPI. These values can also be found in the <var class="varname">$_SERVER</var> array, for example: <var class="varname">$_SERVER['argv']</var>.</p></td>
    </tr>
    <tr class="odd">
    <td><a href="/outcontrol/setup.html#" class="link">output_buffering</a></td>
    <td><strong><code>FALSE</code></strong></td>
    <td><p>Although the <var class="filename">php.ini</var> setting is hardcoded to <strong><code>FALSE</code></strong>, the <a href="/book/outcontrol.html" class="link">Output buffering</a> functions are available.</p></td>
    </tr>
    <tr class="even">
    <td><a href="/info/setup.html#" class="link">max_input_time</a></td>
    <td><strong><code>FALSE</code></strong></td>
    <td><p>The PHP CLI does not support GET, POST or file uploads.</p></td>
    </tr>
    </tbody>
    </table>

    > **Note**:
    >
    > These directives cannot be initialized with another value from the
    > configuration file `php.ini` or a custom one (if specified). This
    > limitation is because the values are applied after all
    > configuration files have been parsed. However, their values can be
    > changed during runtime (although this is not sensible for all of
    > them, such as
    > <a href="/ini/core.html#ini.register-argc-argv" class="link">register_argc_argv</a>).

    > **Note**:
    >
    > It is recommended to set
    > <a href="/misc/setup.html#" class="link">ignore_user_abort</a> for
    > command line scripts. See <span
    > class="function">ignore\_user\_abort</span> for more information.

-   To ease working in the shell environment, a number of constants are
    defined for
    <a href="/features/commandline/io-streams.html" class="link">I/O streams</a>
    .

-   The CLI SAPI does *not* change the current directory to the
    directory of the executed script.

    **Example \#1 Example showing the difference to the CGI SAPI:**

    ``` php
    <?php
    // Our simple test application named test.php
    echo getcwd(), "\n";
    ?>
    ```

    When using the CGI version, the output is:

        $ pwd
        /tmp

        $ php -q another_directory/test.php
        /tmp/another_directory

    This clearly shows that PHP changes its current directory to the one
    of the executed script.

    Using the CLI SAPI yields:

        $ pwd
        /tmp

        $ php -f another_directory/test.php
        /tmp

    This allows greater flexibility when writing shell tools in PHP.

    > **Note**:
    >
    > The CGI SAPI supports this CLI SAPI behaviour by means of the
    > **-C** switch when run from the command line.
