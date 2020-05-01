New Functions
-------------

In PHP 5 there are some new functions. Here is the list of them:

<a href="/ref/array.html" class="link">Arrays</a>:

-   <span class="simpara"> <span
    class="function">array\_combine</span> - Creates an array by using
    one array for keys and another for its values </span>
-   <span class="simpara"> <span
    class="function">array\_diff\_uassoc</span> - Computes the
    difference of arrays with additional index check which is performed
    by a user supplied callback function </span>
-   <span class="simpara"> <span class="function">array\_udiff</span> -
    Computes the difference of arrays by using a callback function for
    data comparison </span>
-   <span class="simpara"> <span
    class="function">array\_udiff\_assoc</span> - Computes the
    difference of arrays with additional index check. The data is
    compared by using a callback function </span>
-   <span class="simpara"> <span
    class="function">array\_udiff\_uassoc</span> - Computes the
    difference of arrays with additional index check. The data is
    compared by using a callback function. The index check is done by a
    callback function also </span>
-   <span class="simpara"> <span
    class="function">array\_walk\_recursive</span> - Apply a user
    function recursively to every member of an array </span>
-   <span class="simpara"> <span
    class="function">array\_uintersect\_assoc</span> - Computes the
    intersection of arrays with additional index check. The data is
    compared by using a callback function </span>
-   <span class="simpara"> <span
    class="function">array\_uintersect\_uassoc</span> - Computes the
    intersection of arrays with additional index check. Both the data
    and the indexes are compared by using separate callback functions
    </span>
-   <span class="simpara"> <span
    class="function">array\_uintersect</span> - Computes the
    intersection of arrays. The data is compared by using a callback
    function </span>

<a href="/book/ibase.html#Firebird/InterBase%20Functions" class="link">InterBase</a>:

-   <span class="simpara"> <span
    class="function">ibase\_affected\_rows</span> - Return the number of
    rows that were affected by the previous query </span>
-   <span class="simpara"> <span class="function">ibase\_backup</span> -
    Initiates a backup task in the service manager and returns
    immediately </span>
-   <span class="simpara"> <span
    class="function">ibase\_commit\_ret</span> - Commit a transaction
    without closing it </span>
-   <span class="simpara"> <span
    class="function">ibase\_db\_info</span> - Request statistics about a
    database </span>
-   <span class="simpara"> <span
    class="function">ibase\_drop\_db</span> - Drops a database </span>
-   <span class="simpara"> <span
    class="function">ibase\_errcode</span> - Return an error code
    </span>
-   <span class="simpara"> <span
    class="function">ibase\_free\_event\_handler</span> - Cancels a
    registered event handler </span>
-   <span class="simpara"> <span
    class="function">ibase\_gen\_id</span> - Increments the named
    generator and returns its new value </span>
-   <span class="simpara"> <span
    class="function">ibase\_maintain\_db</span> - Execute a maintenance
    command on the database server </span>
-   <span class="simpara"> <span
    class="function">ibase\_name\_result</span> - Assigns a name to a
    result set </span>
-   <span class="simpara"> <span
    class="function">ibase\_num\_params</span> - Return the number of
    parameters in a prepared query </span>
-   <span class="simpara"> <span
    class="function">ibase\_param\_info</span> - Return information
    about a parameter in a prepared query </span>
-   <span class="simpara"> <span
    class="function">ibase\_restore</span> - Initiates a restore task in
    the service manager and returns immediately </span>
-   <span class="simpara"> <span
    class="function">ibase\_rollback\_ret</span> - Rollback transaction
    and retain the transaction context </span>
-   <span class="simpara"> <span
    class="function">ibase\_server\_info</span> - Request statistics
    about a database server </span>
-   <span class="simpara"> <span
    class="function">ibase\_service\_attach</span> - Connect to the
    service manager </span>
-   <span class="simpara"> <span
    class="function">ibase\_service\_detach</span> - Disconnect from the
    service manager </span>
-   <span class="simpara"> <span
    class="function">ibase\_set\_event\_handler</span> - Register a
    callback function to be called when events are posted </span>
-   <span class="simpara"> <span
    class="function">ibase\_wait\_event</span> - Wait for an event to be
    posted by the database </span>

<a href="/ref/iconv.html" class="link">iconv</a>:

-   <span class="simpara"> <span
    class="function">iconv\_mime\_decode</span> - Decodes a MIME header
    field </span>
-   <span class="simpara"> <span
    class="function">iconv\_mime\_decode\_headers</span> - Decodes
    multiple MIME header fields at once </span>
-   <span class="simpara"> <span
    class="function">iconv\_mime\_encode</span> - Composes a MIME header
    field </span>
-   <span class="simpara"> <span class="function">iconv\_strlen</span> -
    Returns the character count of string </span>
-   <span class="simpara"> <span class="function">iconv\_strpos</span> -
    Finds position of first occurrence of a needle within a haystack
    </span>
-   <span class="simpara"> <span
    class="function">iconv\_strrpos</span> - Finds the last occurrence
    of a needle within a haystack </span>
-   <span class="simpara"> <span class="function">iconv\_substr</span> -
    Cut out part of a string </span>

<a href="/ref/stream.html" class="link">Streams</a>:

-   <span class="simpara"> <span
    class="function">stream\_copy\_to\_stream</span> - Copies data from
    one stream to another </span>
-   <span class="simpara"> <span
    class="function">stream\_get\_line</span> - Gets line from stream
    resource up to a given delimiter </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_accept</span> - Accept a connection
    on a socket created by <span
    class="function">stream\_socket\_server</span> </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_client</span> - Open Internet or
    Unix domain socket connection </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_get\_name</span> - Retrieve the
    name of the local or remote sockets </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_recvfrom</span> - Receives data
    from a socket, connected or not </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_sendto</span> - Sends a message to
    a socket, whether it is connected or not </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_server</span> - Create an Internet
    or Unix domain server socket </span>

<a href="/ref/datetime.html" class="link">Date and time related</a>:

-   <span class="simpara"> <span class="function">idate</span> - Format
    a local time/date as integer </span>
-   <span class="simpara"> <span class="function">date\_sunset</span> -
    Time of sunset for a given day and location </span>
-   <span class="simpara"> <span class="function">date\_sunrise</span> -
    Time of sunrise for a given day and location </span>
-   <span class="simpara"> <span
    class="function">time\_nanosleep</span> - Delay for a number of
    seconds and nanoseconds </span>

<a href="/ref/strings.html" class="link">Strings</a>:

-   <span class="simpara"> <span class="function">str\_split</span> -
    Convert a string to an array </span>
-   <span class="simpara"> <span class="function">strpbrk</span> -
    Search a string for any of a set of characters </span>
-   <span class="simpara"> <span
    class="function">substr\_compare</span> - Binary safe optionally
    case insensitive comparison of two strings from an offset, up to
    length characters </span>

Other:

-   <span class="simpara"> <span
    class="function">convert\_uudecode</span> - decode a uuencoded
    string </span>
-   <span class="simpara"> <span
    class="function">convert\_uuencode</span> - uuencode a string
    </span>
-   <span class="simpara"> <span
    class="function">curl\_copy\_handle</span> - Copy a cURL handle
    along with all of its preferences </span>
-   <span class="simpara"> <span
    class="function">dba\_key\_split</span> - Splits a key in string
    representation into array representation </span>
-   <span class="simpara"> <span
    class="function">dbase\_get\_header\_info</span> - Get the header
    info of a dBase database </span>
-   <span class="simpara"> <span
    class="function">dbx\_fetch\_row</span> - Fetches rows from a
    query-result that had the **`DBX_RESULT_UNBUFFERED`** flag set
    </span>
-   <span class="simpara"> <span
    class="function">fbsql\_set\_password</span> - Change the password
    for a given user </span>
-   <span class="simpara"> <span
    class="function">file\_put\_contents</span> - Write a string to a
    file </span>
-   <span class="simpara"> <span class="function">ftp\_alloc</span> -
    Allocates space for a file to be uploaded </span>
-   <span class="simpara"> <span
    class="function">get\_declared\_interfaces</span> - Returns an array
    of all declared interfaces </span>
-   <span class="simpara"> <span class="function">get\_headers</span> -
    Fetches all the headers sent by the server in response to a HTTP
    request </span>
-   <span class="simpara"> <span class="function">headers\_list</span> -
    Returns a list of response headers sent (or ready to send) </span>
-   <span class="simpara"> <span
    class="function">http\_build\_query</span> - Generate URL-encoded
    query string </span>
-   <span class="simpara"> <span
    class="function">image\_type\_to\_extension</span> - Get file
    extension for image-type returned by <span
    class="function">getimagesize</span>, <span
    class="function">exif\_read\_data</span>, <span
    class="function">exif\_thumbnail</span>, <span
    class="function">exif\_imagetype</span> </span>
-   <span class="simpara"> <span class="function">imagefilter</span> -
    Applies a filter to an image using custom arguments </span>
-   <span class="simpara"> <span class="function">imap\_getacl</span> -
    Gets the ACL for a given mailbox </span>
-   <span class="simpara"> <span
    class="function">ldap\_sasl\_bind</span> - Bind to LDAP directory
    using SASL </span>
-   <span class="simpara"> <span
    class="function">mb\_list\_encodings</span> - Returns an array of
    all supported encodings </span>
-   <span class="simpara"> <span
    class="function">pcntl\_getpriority</span> - Get the priority of any
    process </span>
-   <span class="simpara"> <span class="function">pcntl\_wait</span> -
    Waits on or returns the status of a forked child as defined by the
    *waitpid()* system call </span>
-   <span class="simpara"> <span class="function">pg\_version</span> -
    Returns an array with client, protocol and server version (when
    available) </span>
-   <span class="simpara"> <span
    class="function">php\_check\_syntax</span> - Check the syntax of the
    specified file </span>
-   <span class="simpara"> <span
    class="function">php\_strip\_whitespace</span> - Return source with
    stripped comments and whitespace </span>
-   <span class="simpara"> <span class="function">proc\_nice</span> -
    Change the priority of the current process </span>
-   <span class="simpara"> <span
    class="function">pspell\_config\_data\_dir</span> - Change location
    of language data files </span>
-   <span class="simpara"> <span
    class="function">pspell\_config\_dict\_dir</span> - Change location
    of the main word list </span>
-   <span class="simpara"> <span class="function">setrawcookie</span> -
    Send a cookie without URL-encoding the value </span>
-   <span class="simpara"> <span class="function">scandir</span> - List
    files and directories inside the specified path </span>
-   <span class="simpara"> <span
    class="function">snmp\_read\_mib</span> - Reads and parses a MIB
    file into the active MIB tree </span>
-   <span class="simpara"> <span
    class="function">sqlite\_fetch\_column\_types</span> - Return an
    array of column types from a particular table </span>

> **Note**:
>
> The <a href="/ref/tidy.html" class="link">Tidy</a> extension has also
> changed its API completely.
