New Functions
-------------

### PHP Core

-   <span class="simpara"> <span class="function">array\_column</span>
    </span>
-   <span class="simpara"> <span class="function">boolval</span> </span>
-   <span class="simpara"> <span
    class="function">json\_last\_error\_msg</span> </span>
-   <span class="simpara"> <span
    class="function">password\_get\_info</span> </span>
-   <span class="simpara"> <span class="function">password\_hash</span>
    </span>
-   <span class="simpara"> <span
    class="function">password\_needs\_rehash</span> </span>
-   <span class="simpara"> <span
    class="function">password\_verify</span> </span>

### <a href="/book/hash.html" class="link">Hash</a>

-   <span class="simpara"> <span class="function">hash\_pbkdf2</span>
    </span>

### <a href="/book/openssl.html" class="link">OpenSSL</a>

-   <span class="simpara"> <span class="function">openssl\_pbkdf2</span>
    </span>

### <a href="/book/curl.html" class="link">cURL</a>

-   <span class="simpara"> <span class="function">curl\_escape</span>
    </span>
-   <span class="simpara"> <span
    class="function">curl\_file\_create</span> </span>
-   <span class="simpara"> <span
    class="function">curl\_multi\_setopt</span> </span>
-   <span class="simpara"> <span
    class="function">curl\_multi\_strerror</span> </span>
-   <span class="simpara"> <span class="function">curl\_pause</span>
    </span>
-   <span class="simpara"> <span class="function">curl\_reset</span>
    </span>
-   <span class="simpara"> <span
    class="function">curl\_share\_close</span> </span>
-   <span class="simpara"> <span
    class="function">curl\_share\_init</span> </span>
-   <span class="simpara"> <span
    class="function">curl\_share\_setopt</span> </span>
-   <span class="simpara"> <span class="function">curl\_strerror</span>
    </span>
-   <span class="simpara"> <span class="function">curl\_unescape</span>
    </span>

### <a href="/book/image.html" class="link">GD</a>

-   <span class="simpara"> <span
    class="function">imageaffinematrixconcat</span> </span>
-   <span class="simpara"> <span
    class="function">imageaffinematrixget</span> </span>
-   <span class="simpara"> <span class="function">imagecrop</span>
    </span>
-   <span class="simpara"> <span class="function">imagecropauto</span>
    </span>
-   <span class="simpara"> <span class="function">imageflip</span>
    </span>
-   <span class="simpara"> <span
    class="function">imagepalettetotruecolor</span> </span>
-   <span class="simpara"> <span class="function">imagescale</span>
    </span>

### <a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a>

-   <span class="simpara"> <span
    class="function">mysqli\_begin\_transaction</span> </span>
-   <span class="simpara"> <span
    class="function">mysqli\_release\_savepoint</span> </span>
-   <span class="simpara"> <span
    class="function">mysqli\_savepoint</span> </span>

### <a href="/book/pgsql.html" class="link">PostgreSQL</a>

-   <span class="simpara"> <span
    class="function">pg\_escape\_literal</span> </span>
-   <span class="simpara"> <span
    class="function">pg\_escape\_identifier</span> </span>

### <a href="/book/sockets.html" class="link">Sockets</a>

-   <span class="simpara"> <span class="function">socket\_sendmsg</span>
    </span>
-   <span class="simpara"> <span class="function">socket\_recvmsg</span>
    </span>
-   <span class="simpara"> <span
    class="function">socket\_cmsg\_space</span> </span>

### <a href="/features/commandline.html" class="link">CLI</a>

-   <span class="simpara"> <span
    class="function">cli\_get\_process\_title</span> </span>
-   <span class="simpara"> <span
    class="function">cli\_set\_process\_title</span> </span>

### <a href="/book/intl.html" class="link">Intl</a>

-   <span class="simpara"> <span
    class="function">datefmt\_format\_object</span> </span>
-   <span class="simpara"> <span
    class="function">datefmt\_get\_calendar\_object</span> </span>
-   <span class="simpara"> <span
    class="function">datefmt\_get\_timezone</span> </span>
-   <span class="simpara"> <span
    class="function">datefmt\_set\_timezone</span> </span>
-   <span class="simpara"> <span
    class="function">datefmt\_get\_calendar\_object</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_create\_instance</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_keyword\_values\_for\_locale</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_now</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_available\_locales</span> </span>
-   <span class="simpara"> <span class="function">intlcal\_get</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_time</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_time</span> </span>
-   <span class="simpara"> <span class="function">intlcal\_add</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_time\_zone</span> </span>
-   <span class="simpara"> <span class="function">intlcal\_after</span>
    </span>
-   <span class="simpara"> <span class="function">intlcal\_before</span>
    </span>
-   <span class="simpara"> <span class="function">intlcal\_set</span>
    </span>
-   <span class="simpara"> <span class="function">intlcal\_roll</span>
    </span>
-   <span class="simpara"> <span class="function">intlcal\_clear</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_field\_difference</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_actual\_maximum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_actual\_minimum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_day\_of\_week\_type</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_first\_day\_of\_week</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_greatest\_minimum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_least\_maximum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_locale</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_maximum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_minimal\_days\_in\_first\_week</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_minimum</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_time\_zone</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_type</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_weekend\_transition</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_in\_daylight\_time</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_is\_equivalent\_to</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_is\_lenient</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_is\_set</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_is\_weekend</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_first\_day\_of\_week</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_lenient</span> </span>
-   <span class="simpara"> <span class="function">intlcal\_equals</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_repeated\_wall\_time\_option</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_skipped\_wall\_time\_option</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_repeated\_wall\_time\_option</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_set\_skipped\_wall\_time\_option</span>
    </span>
-   <span class="simpara"> <span
    class="function">intlcal\_from\_date\_time</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_to\_date\_time</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_error\_code</span> </span>
-   <span class="simpara"> <span
    class="function">intlcal\_get\_error\_message</span> </span>
-   <span class="simpara"> <span
    class="function">intlgregcal\_create\_instance</span> </span>
-   <span class="simpara"> <span
    class="function">intlgregcal\_set\_gregorian\_change</span> </span>
-   <span class="simpara"> <span
    class="function">intlgregcal\_get\_gregorian\_change</span> </span>
-   <span class="simpara"> <span
    class="function">intlgregcal\_is\_leap\_year</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_create\_time\_zone</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_create\_default</span> </span>
-   <span class="simpara"> <span class="function">intltz\_get\_id</span>
    </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_gmt</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_unknown</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_create\_enumeration</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_count\_equivalent\_ids</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_create\_time\_zone\_id\_enumeration</span>
    </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_canonical\_id</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_region</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_tz\_data\_version</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_equivalent\_id</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_use\_daylight\_time</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_offset</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_raw\_offset</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_has\_same\_rules</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_display\_name</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_dst\_savings</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_from\_date\_time\_zone</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_to\_date\_time\_zone</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_error\_code</span> </span>
-   <span class="simpara"> <span
    class="function">intltz\_get\_error\_message</span> </span>

### <a href="/book/spl.html" class="link">SPL</a>

-   <span class="simpara"> <span
    class="methodname">SplFixedArray::\_\_wakeup</span> </span>
