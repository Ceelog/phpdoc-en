Swish::\_\_construct
====================

Construct a Swish object

### Description

<span class="type">void</span> <span
class="methodname">Swish::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$index_names`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`index_names`  
The list of index files separated by spaces.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 A <span class="function">Swish::\_\_construct</span>
example**

``` php
<?php

try {
    $swish = new Swish("index1 index2");
} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

foreach ($swish->indexes as $index) {
    var_dump($index["name"]);
    var_dump($index["headers"]["Total Words"]);
}

?>
```

The above example will output something similar to:

    string(6) "index1"
    int(1888)
    string(6) "index2"
    int(2429)

Swish::getMetaList
==================

Get the list of meta entries for the index

### Description

<span class="type">array</span> <span
class="methodname">Swish::getMetaList</span> ( <span
class="methodparam"><span class="type">string</span>
`$index_name`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`index_name`  
The name of the index file.

### Return Values

Returns an array of meta entries for the given index.

### Examples

**Example \#1 Basic <span class="function">Swish::getMetaList</span>
example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    var_dump($swish->getMetaList("index.swish-e"));

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    array(1) {
      [0]=>
      array(3) {
        ["Name"]=>
        string(12) "swishdefault"
        ["Type"]=>
        int(0)
        ["ID"]=>
        int(1)
      }
    }

Swish::getPropertyList
======================

Get the list of properties for the index

### Description

<span class="type">array</span> <span
class="methodname">Swish::getPropertyList</span> ( <span
class="methodparam"><span class="type">string</span>
`$index_name`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`index_name`  
The name of the index file.

### Return Values

Returns an array of properties for the given index.

### Examples

**Example \#1 Basic <span class="function">Swish::getPropertyList</span>
example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $properties = $swish->getPropertyList("index.swish-e");
    foreach ($properties as $prop) {
        echo $prop["Name"],"\n";
    }

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    swishreccount
    swishrank
    swishfilenum
    swishdbfile
    swishdocpath
    swishtitle
    swishdocsize
    swishlastmodified

Swish::prepare
==============

Prepare a search query

### Description

<span class="type">object</span> <span
class="methodname">Swish::prepare</span> (\[ <span
class="methodparam"><span class="type">string</span> `$query`</span> \]
)

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

Prepare and return a search object, which you can later use for
unlimited number of queries.

### Parameters

`query`  
Optional query string. The query can be also set using <span
class="function">SwishSearch::execute</span> method.

### Return Values

Returns <span class="classname">SwishSearch</span> object.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span class="function">Swish::prepare</span>
example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare("search query");
    $results = $search->execute();
    echo "Found: ", $results->hits, " hits\n";

    $results = $search->execute("new search");

    echo "Found: ", $results->hits, " hits\n";
} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    Found: 2 hits
    Found: 5 hits

Swish::query
============

Execute a query and return results object

### Description

<span class="type">object</span> <span
class="methodname">Swish::query</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

A quick method to execute a search with default parameters.

### Parameters

`query`  
Query string.

### Return Values

Returns <span class="classname">SwishResults</span> object.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span class="function">Swish::query</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $results = $swish->query("test query");

    echo "Found: ", $results->hits, " hits\n";

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    Found: 1 hits

SwishResult::getMetaList
========================

Get a list of meta entries

### Description

<span class="type">array</span> <span
class="methodname">SwishResult::getMetaList</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Return Values

Returns the same array as <span
class="function">swish::getmetalist</span>, but uses the index file from
the result handle.

SwishResult::stem
=================

Stems the given word

### Description

<span class="type">array</span> <span
class="methodname">SwishResult::stem</span> ( <span
class="methodparam"><span class="type">string</span> `$word`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

Stems the word based on the fuzzy mode used during indexing. Each result
object is linked with its index, so the results are based on this index.

### Parameters

`word`  
The word to stem.

### Return Values

Returns array containing the stemmed word variants (usually just one).

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span class="function">SwishResult::stem</span>
example**

``` php
<?php

try {

    $swish = new Swish("ext/swish/tests/index.swish-e");
    $results = $swish->query("testing OR others");

    if ($result = $results->nextResult()) {
        var_dump($result->stem("testing")); //the results fully depend on the stemmer used in the index
        var_dump($result->stem("others"));
    }

} catch (SwishException $e) {
    echo "Error: ", $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    array(1) {
      [0]=>
      string(4) "test"
    }
    array(1) {
      [0]=>
      string(5) "other"
    }

SwishResults::getParsedWords
============================

Get an array of parsed words

### Description

<span class="type">array</span> <span
class="methodname">SwishResults::getParsedWords</span> ( <span
class="methodparam"><span class="type">string</span>
`$index_name`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`indexi_name`  
The name of the index used to initialize <span
class="classname">Swish</span> object.

### Return Values

An array of parsed words with stopwords removed. The list of parsed
words may be useful for highlighting search terms in the results.

### Examples

**Example \#1 Basic <span
class="function">SwishResults::getParsedWords</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $results = $swish->query("'some characters' and numbers");

    var_dump($results->getParsedWords("index.swish-e"));
    var_dump($results->indexes[0]['parsed_words']); //same result in a different way

} catch (SwishException $e) {
    echo "Error: ", $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    array(4) {
      [0]=>
      string(4) "some"
      [1]=>
      string(10) "characters"
      [2]=>
      string(3) "and"
      [3]=>
      string(7) "numbers"
    }
    array(4) {
      [0]=>
      string(4) "some"
      [1]=>
      string(10) "characters"
      [2]=>
      string(3) "and"
      [3]=>
      string(7) "numbers"
    }

SwishResults::getRemovedStopwords
=================================

Get an array of stopwords removed from the query

### Description

<span class="type">array</span> <span
class="methodname">SwishResults::getRemovedStopwords</span> ( <span
class="methodparam"><span class="type">string</span>
`$index_name`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`index_name`  
The name of the index used to initialize <span
class="classname">Swish</span> object.

### Return Values

Returns array of stopwords removed from the query.

SwishResults::nextResult
========================

Get the next search result

### Description

<span class="type">object</span> <span
class="methodname">SwishResults::nextResult</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Return Values

Returns the next <span class="classname">SwishResult</span> object in
the result set or **`FALSE`** if there are no more results available.

### Examples

**Example \#1 Basic <span
class="function">SwishResults::nextResult</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("lost");
    while($result = $results->nextResult()) {
        /* do something with the result object */
    }

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

SwishResults::seekResult
========================

Set current seek pointer to the given position

### Description

<span class="type">int</span> <span
class="methodname">SwishResults::seekResult</span> ( <span
class="methodparam"><span class="type">int</span> `$position`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`position`  
Zero-based position number. Cannot be less than zero.

### Return Values

Returns new position value on success.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span
class="function">SwishResults::seekResult</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("lost");

    var_dump($results->seekResult(0)); //this will succeed
    var_dump($results->seekResult(100)); //this will fail

} catch (SwishException $e) {
    echo "Error: ", $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    int(0)
    Error: No more results

SwishSearch::execute
====================

Execute the search and get the results

### Description

<span class="type">object</span> <span
class="methodname">SwishSearch::execute</span> (\[ <span
class="methodparam"><span class="type">string</span> `$query`</span> \]
)

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

Searches the index file(s) based on the parameters set in the search
object.

### Parameters

`query`  
The query string is an optional parameter, it can be also set using
<span class="function">Swish::prepare</span> method. The query string is
preserved between executions, so you can set it once, but execute the
search multiple times.

### Return Values

Returns <span class="classname">SwishResults</span> object.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span class="function">SwishSearch::execute</span>
example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("query");
    echo "First query found: ", $results->hits, " hits\n";

    $results = $search->execute("new OR query");
    echo "Second query found: ", $results->hits, " hits\n";

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 2 hits
    Second query found: 12 hits

SwishSearch::resetLimit
=======================

Reset the search limits

### Description

<span class="type">void</span> <span
class="methodname">SwishSearch::resetLimit</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

Reset the search limits previous set by
<a href="/ref/swish.html#SwishSearch::setLimit" class="xref"></a>.

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span
class="function">SwishSearch::resetLimit</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("time");
    echo "First query found: ", $results->hits, " hits\n";

    $search->setLimit("swishdocsize", "3000", "6000"); //limit by document size, from 3000 to 6000 bytes
    $results = $search->execute("time");
    echo "Second query found: ", $results->hits, " hits\n";

    $search->resetLimit();
    $results = $search->execute("time");
    echo "Third query found: ", $results->hits, " hits\n";

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 5 hits
    Second query found: 2 hits
    Third query found: 5 hits

SwishSearch::setLimit
=====================

Set the search limits

### Description

<span class="type">void</span> <span
class="methodname">SwishSearch::setLimit</span> ( <span
class="methodparam"><span class="type">string</span> `$property`</span>
, <span class="methodparam"><span class="type">string</span>
`$low`</span> , <span class="methodparam"><span
class="type">string</span> `$high`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`property`  
Search result property name.

`low`  
The lowest value of the property.

`high`  
The highest value of the property.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">SwishException</span> on error.

### Examples

**Example \#1 Basic <span class="function">SwishSearch::setLimit</span>
example**

``` php
<?php
try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("time");
    echo "First query found: ", $results->hits, " hits\n";

    $i = 0;
    while($result = $results->nextResult()) {
        echo "Hit #", ++$i, " - ", $result->swishdocsize, " bytes\n";
    }

    $search->setLimit("swishdocsize", "3000", "6000"); //limit by document size, from 3000 to 6000 bytes
    $results = $search->execute("time");
    echo "Second query found: ", $results->hits, " hits\n";

    $i = 0;
    while($result = $results->nextResult()) {
        echo "Hit #", ++$i, " - ", $result->swishdocsize, " bytes\n";
    }

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 5 hits
    Hit #1 - 4261 bytes
    Hit #2 - 37937 bytes
    Hit #3 - 7126 bytes
    Hit #4 - 15427 bytes
    Hit #5 - 4768 bytes
    Second query found: 2 hits
    Hit #1 - 4261 bytes
    Hit #2 - 4768 bytes

SwishSearch::setPhraseDelimiter
===============================

Set the phrase delimiter

### Description

<span class="type">void</span> <span
class="methodname">SwishSearch::setPhraseDelimiter</span> ( <span
class="methodparam"><span class="type">string</span> `$delimiter`</span>
)

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`delimiter`  
Phrase delimiter character. The default delimiter is double-quotes.

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span
class="function">SwishSearch::setPhraseDelimiter</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute('"every time"'); //looking for "every time"
    echo "First query found: ", $results->hits, " hits\n";

    $search->setPhraseDelimiter("'");
    $results = $search->execute("'every time'"); //the same query, but using different delimiter
    echo "Second query found: ", $results->hits, " hits\n";

    $search->setPhraseDelimiter('"');
    $results = $search->execute("'every time'"); //looking for "every" and "time"
    echo "Third query found: ", $results->hits, " hits\n";

    //let's look at parsed words
    var_dump($results->getParsedWords("index.swish-e"));

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 1 hits
    Second query found: 1 hits
    Third query found: 2 hits
    array(2) {
      [0]=>
      string(5) "every"
      [1]=>
      string(4) "time"
    }

SwishSearch::setSort
====================

Set the sort order

### Description

<span class="type">void</span> <span
class="methodname">SwishSearch::setSort</span> ( <span
class="methodparam"><span class="type">string</span> `$sort`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`sort`  
Sort order of the results is a string containing name of a result
property combined with sort direction ("asc" or "desc"). Examples:
"swishrank desc", "swishdocpath asc", "swishtitle asc", "swishdocsize
desc", "swishlastmodified desc" etc.

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span class="function">SwishSearch::setSort</span>
example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("time");
    echo "First query found: ", $results->hits, " hits\n";

    $i = 0;
    while($result = $results->nextResult()) {
        echo "Hit #", ++$i, " - ", $result->swishdocsize, " bytes\n";
    }

    $search->setSort("swishdocsize desc"); //sort by document size
    $results = $search->execute("time");
    echo "Second query found: ", $results->hits, " hits\n";

    $i = 0;
    while($result = $results->nextResult()) {
        echo "Hit #", ++$i, " - ", $result->swishdocsize, " bytes\n";
    }

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 5 hits
    Hit #1 - 4261 bytes
    Hit #2 - 37937 bytes
    Hit #3 - 7126 bytes
    Hit #4 - 15427 bytes
    Hit #5 - 4768 bytes
    Second query found: 5 hits
    Hit #1 - 37937 bytes
    Hit #2 - 15427 bytes
    Hit #3 - 7126 bytes
    Hit #4 - 4768 bytes
    Hit #5 - 4261 bytes

SwishSearch::setStructure
=========================

Set the structure flag in the search object

### Description

<span class="type">void</span> <span
class="methodname">SwishSearch::setStructure</span> ( <span
class="methodparam"><span class="type">int</span> `$structure`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`structure`  
The structure flag a bitmask is used to limit search to certain parts of
HTML documents (like title, meta, body etc.). Its possible values are
listed below. To combine several values use bitwise OR operator, see
example below.

-   **`Swish::IN_FILE`**

-   **`Swish::IN_TITLE`**

-   **`Swish::IN_HEAD`**

-   **`Swish::IN_BODY`**

-   **`Swish::IN_COMMENTS`**

-   **`Swish::IN_HEADER`**

-   **`Swish::IN_EMPHASIZED`**

-   **`Swish::IN_META`**

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span
class="function">SwishSearch::setStructure</span> example**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $search = $swish->prepare();

    $results = $search->execute("time");
    echo "First query found: ", $results->hits, " hits\n";

    $search->setStructure(Swish::IN_TITLE|Swish::IN_HEAD); //search in title and head
    $results = $search->execute("time");
    echo "Second query found: ", $results->hits, " hits\n";

    $search->setStructure(Swish::IN_ALL); //search in whole document, the default value
    $results = $search->execute("time");
    echo "Third query found: ", $results->hits, " hits\n";

} catch (SwishException $e) {
    echo $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    First query found: 5 hits
    Second query found: 0 hits
    Third query found: 5 hits

**Table of Contents**

-   [Swish::\_\_construct](/ref/swish.html#Swish::__construct) —
    Construct a Swish object
-   [Swish::getMetaList](/ref/swish.html#Swish::getMetaList) — Get the
    list of meta entries for the index
-   [Swish::getPropertyList](/ref/swish.html#Swish::getPropertyList) —
    Get the list of properties for the index
-   [Swish::prepare](/ref/swish.html#Swish::prepare) — Prepare a search
    query
-   [Swish::query](/ref/swish.html#Swish::query) — Execute a query and
    return results object
-   [SwishResult::getMetaList](/ref/swish.html#SwishResult::getMetaList)
    — Get a list of meta entries
-   [SwishResult::stem](/ref/swish.html#SwishResult::stem) — Stems the
    given word
-   [SwishResults::getParsedWords](/ref/swish.html#SwishResults::getParsedWords)
    — Get an array of parsed words
-   [SwishResults::getRemovedStopwords](/ref/swish.html#SwishResults::getRemovedStopwords)
    — Get an array of stopwords removed from the query
-   [SwishResults::nextResult](/ref/swish.html#SwishResults::nextResult)
    — Get the next search result
-   [SwishResults::seekResult](/ref/swish.html#SwishResults::seekResult)
    — Set current seek pointer to the given position
-   [SwishSearch::execute](/ref/swish.html#SwishSearch::execute) —
    Execute the search and get the results
-   [SwishSearch::resetLimit](/ref/swish.html#SwishSearch::resetLimit) —
    Reset the search limits
-   [SwishSearch::setLimit](/ref/swish.html#SwishSearch::setLimit) — Set
    the search limits
-   [SwishSearch::setPhraseDelimiter](/ref/swish.html#SwishSearch::setPhraseDelimiter)
    — Set the phrase delimiter
-   [SwishSearch::setSort](/ref/swish.html#SwishSearch::setSort) — Set
    the sort order
-   [SwishSearch::setStructure](/ref/swish.html#SwishSearch::setStructure)
    — Set the structure flag in the search object
