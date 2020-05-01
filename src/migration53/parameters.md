New Parameters
--------------

Several functions were given new, optional parameters in PHP 5.3:

PHP Core:

-   <span class="simpara"> <span
    class="function">clearstatcache</span> - Added
    `clear_realpath_cache` and `filename`. </span>
-   <span class="simpara"> <span class="function">copy</span> - Added a
    stream context parameter, `context`. </span>
-   <span class="simpara"> <span class="function">fgetcsv</span> - Added
    `escape`. </span>
-   <span class="simpara"> <span class="function">ini\_get\_all</span> -
    Added `details`. </span>
-   <span class="simpara"> <span class="function">nl2br</span> - Added
    `is_xhtml`. </span>
-   <span class="simpara"> <span
    class="function">parse\_ini\_file</span> - Added `scanner_mode`.
    </span>
-   <span class="simpara"> <span class="function">round</span> - Added
    `mode`. </span>
-   <span class="simpara"> <span
    class="function">stream\_context\_create</span> - Added `params`.
    </span>
-   <span class="simpara"> <span class="function">strstr</span> and
    <span class="function">stristr</span> - Added `before_needle`.
    </span>

<a href="/book/json.html" class="link">json</a>:

-   <span class="simpara"> <span class="function">json\_encode</span> -
    Added `options`. </span>
-   <span class="simpara"> <span class="function">json\_decode</span> -
    Added `depth`. </span>

<a href="/book/stream.html" class="link">Streams</a>:

-   <span class="simpara"> <span class="function">stream\_select</span>,
    <span class="function">stream\_set\_blocking</span>, <span
    class="function">stream\_set\_timeout</span>, and <span
    class="function">stream\_set\_write\_buffer</span> now work with
    user-space stream wrappers. </span>

<a href="/book/sybase.html" class="link">sybase_ct</a>:

-   <span class="simpara"> <span
    class="function">sybase\_connect</span> - Added `new`. </span>

New method parameters in PHP 5.3.0:

PHP Core:

-   <span class="simpara"> <span
    class="methodname">Exception::\_\_construct</span> - Added
    `previous`. </span>
