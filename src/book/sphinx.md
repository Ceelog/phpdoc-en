Sphinx Client
=============

**Table of Contents**

-   [Introduction](/intro/sphinx.html)
-   [Installing/Configuring](/sphinx/setup.html)
    -   [Requirements](/sphinx/setup.html#Requirements)
    -   [Installation](/sphinx/setup.html#Installation)
    -   [Runtime
        Configuration](/sphinx/setup.html#Runtime%20Configuration)
    -   [Resource Types](/sphinx/setup.html#Resource%20Types)
-   [Predefined Constants](/sphinx/constants.html)
-   [Examples](/sphinx/examples.html)
-   [SphinxClient](/class/sphinxclient.html) — The SphinxClient class
    -   [SphinxClient::addQuery](/class/sphinxclient.html#SphinxClient::addQuery)
        — Add query to multi-query batch
    -   [SphinxClient::buildExcerpts](/class/sphinxclient.html#SphinxClient::buildExcerpts)
        — Build text snippets
    -   [SphinxClient::buildKeywords](/class/sphinxclient.html#SphinxClient::buildKeywords)
        — Extract keywords from query
    -   [SphinxClient::close](/class/sphinxclient.html#SphinxClient::close)
        — Closes previously opened persistent connection
    -   [SphinxClient::\_\_construct](/class/sphinxclient.html#SphinxClient::__construct)
        — Create a new SphinxClient object
    -   [SphinxClient::escapeString](/class/sphinxclient.html#SphinxClient::escapeString)
        — Escape special characters
    -   [SphinxClient::getLastError](/class/sphinxclient.html#SphinxClient::getLastError)
        — Get the last error message
    -   [SphinxClient::getLastWarning](/class/sphinxclient.html#SphinxClient::getLastWarning)
        — Get the last warning
    -   [SphinxClient::open](/class/sphinxclient.html#SphinxClient::open)
        — Opens persistent connection to the server
    -   [SphinxClient::query](/class/sphinxclient.html#SphinxClient::query)
        — Execute search query
    -   [SphinxClient::resetFilters](/class/sphinxclient.html#SphinxClient::resetFilters)
        — Clear all filters
    -   [SphinxClient::resetGroupBy](/class/sphinxclient.html#SphinxClient::resetGroupBy)
        — Clear all group-by settings
    -   [SphinxClient::runQueries](/class/sphinxclient.html#SphinxClient::runQueries)
        — Run a batch of search queries
    -   [SphinxClient::setArrayResult](/class/sphinxclient.html#SphinxClient::setArrayResult)
        — Change the format of result set array
    -   [SphinxClient::setConnectTimeout](/class/sphinxclient.html#SphinxClient::setConnectTimeout)
        — Set connection timeout
    -   [SphinxClient::setFieldWeights](/class/sphinxclient.html#SphinxClient::setFieldWeights)
        — Set field weights
    -   [SphinxClient::setFilter](/class/sphinxclient.html#SphinxClient::setFilter)
        — Add new integer values set filter
    -   [SphinxClient::setFilterFloatRange](/class/sphinxclient.html#SphinxClient::setFilterFloatRange)
        — Add new float range filter
    -   [SphinxClient::setFilterRange](/class/sphinxclient.html#SphinxClient::setFilterRange)
        — Add new integer range filter
    -   [SphinxClient::setGeoAnchor](/class/sphinxclient.html#SphinxClient::setGeoAnchor)
        — Set anchor point for a geosphere distance calculations
    -   [SphinxClient::setGroupBy](/class/sphinxclient.html#SphinxClient::setGroupBy)
        — Set grouping attribute
    -   [SphinxClient::setGroupDistinct](/class/sphinxclient.html#SphinxClient::setGroupDistinct)
        — Set attribute name for per-group distinct values count
        calculations
    -   [SphinxClient::setIDRange](/class/sphinxclient.html#SphinxClient::setIDRange)
        — Set a range of accepted document IDs
    -   [SphinxClient::setIndexWeights](/class/sphinxclient.html#SphinxClient::setIndexWeights)
        — Set per-index weights
    -   [SphinxClient::setLimits](/class/sphinxclient.html#SphinxClient::setLimits)
        — Set offset and limit of the result set
    -   [SphinxClient::setMatchMode](/class/sphinxclient.html#SphinxClient::setMatchMode)
        — Set full-text query matching mode
    -   [SphinxClient::setMaxQueryTime](/class/sphinxclient.html#SphinxClient::setMaxQueryTime)
        — Set maximum query time
    -   [SphinxClient::setOverride](/class/sphinxclient.html#SphinxClient::setOverride)
        — Sets temporary per-document attribute value overrides
    -   [SphinxClient::setRankingMode](/class/sphinxclient.html#SphinxClient::setRankingMode)
        — Set ranking mode
    -   [SphinxClient::setRetries](/class/sphinxclient.html#SphinxClient::setRetries)
        — Set retry count and delay
    -   [SphinxClient::setSelect](/class/sphinxclient.html#SphinxClient::setSelect)
        — Set select clause
    -   [SphinxClient::setServer](/class/sphinxclient.html#SphinxClient::setServer)
        — Set searchd host and port
    -   [SphinxClient::setSortMode](/class/sphinxclient.html#SphinxClient::setSortMode)
        — Set matches sorting mode
    -   [SphinxClient::status](/class/sphinxclient.html#SphinxClient::status)
        — Queries searchd status
    -   [SphinxClient::updateAttributes](/class/sphinxclient.html#SphinxClient::updateAttributes)
        — Update document attributes

Introduction
------------

The SphinxClient class provides object-oriented interface to Sphinx.

Class synopsis
--------------

**SphinxClient**

<span class="ooclass"> class **SphinxClient** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">addQuery</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> \[, <span
class="methodparam"><span class="type">string</span> `$index`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$comment`<span
class="initializer"> = ""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">buildExcerpts</span> ( <span
class="methodparam"><span class="type">array</span> `$docs`</span> ,
<span class="methodparam"><span class="type">string</span>
`$index`</span> , <span class="methodparam"><span
class="type">string</span> `$words`</span> \[, <span
class="methodparam"><span class="type">array</span> `$opts`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">buildKeywords</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> ,
<span class="methodparam"><span class="type">string</span>
`$index`</span> , <span class="methodparam"><span
class="type">bool</span> `$hits`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">escapeString</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLastError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLastWarning</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">open</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">query</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> \[, <span
class="methodparam"><span class="type">string</span> `$index`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$comment`<span
class="initializer"> = ""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">resetFilters</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">resetGroupBy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">runQueries</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setArrayResult</span> ( <span
class="methodparam"><span class="type">bool</span> `$array_result`<span
class="initializer"> = **`FALSE`**</span></span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setConnectTimeout</span> ( <span
class="methodparam"><span class="type">float</span> `$timeout`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFieldWeights</span> ( <span
class="methodparam"><span class="type">array</span> `$weights`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFilter</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">array</span>
`$values`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$exclude`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFilterFloatRange</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">float</span>
`$min`</span> , <span class="methodparam"><span
class="type">float</span> `$max`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$exclude`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFilterRange</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$min`</span>
, <span class="methodparam"><span class="type">int</span> `$max`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$exclude`<span class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setGeoAnchor</span> ( <span
class="methodparam"><span class="type">string</span> `$attrlat`</span> ,
<span class="methodparam"><span class="type">string</span>
`$attrlong`</span> , <span class="methodparam"><span
class="type">float</span> `$latitude`</span> , <span
class="methodparam"><span class="type">float</span> `$longitude`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setGroupBy</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$func`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$groupsort`<span class="initializer"> = "@group desc"</span></span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setGroupDistinct</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIDRange</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setIndexWeights</span> ( <span
class="methodparam"><span class="type">array</span> `$weights`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setLimits</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> ,
<span class="methodparam"><span class="type">int</span> `$limit`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$max_matches`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$cutoff`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMatchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMaxQueryTime</span> ( <span
class="methodparam"><span class="type">int</span> `$qtime`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setOverride</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$type`</span>
, <span class="methodparam"><span class="type">array</span>
`$values`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setRankingMode</span> ( <span
class="methodparam"><span class="type">int</span> `$ranker`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setRetries</span> ( <span
class="methodparam"><span class="type">int</span> `$count`</span> \[,
<span class="methodparam"><span class="type">int</span> `$delay`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSelect</span> ( <span
class="methodparam"><span class="type">string</span> `$clause`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setServer</span> ( <span
class="methodparam"><span class="type">string</span> `$server`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSortMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$sortby`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">status</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">updateAttributes</span> ( <span
class="methodparam"><span class="type">string</span> `$index`</span> ,
<span class="methodparam"><span class="type">array</span>
`$attributes`</span> , <span class="methodparam"><span
class="type">array</span> `$values`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$mva`<span
class="initializer"> = **`FALSE`**</span></span> \] )

}

SphinxClient::addQuery
======================

Add query to multi-query batch

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SphinxClient::addQuery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> \[,
<span class="methodparam"><span class="type">string</span> `$index`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$comment`<span
class="initializer"> = ""</span></span> \]\] )

Adds query with the current settings to multi-query batch. This method
doesn't affect current settings (sorting, filtering, grouping etc.) in
any way.

### Parameters

`query`  
Query string.

`index`  
An index name (or names).

`comment`  

### Return Values

Returns an index in an array of results that will be returned by
<a href="/class/sphinxclient.html#SphinxClient::runQueries" class="xref"></a>
call or false on error.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::runQueries" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::query" class="xref"></a>

SphinxClient::buildExcerpts
===========================

Build text snippets

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SphinxClient::buildExcerpts</span> ( <span
class="methodparam"><span class="type">array</span> `$docs`</span> ,
<span class="methodparam"><span class="type">string</span>
`$index`</span> , <span class="methodparam"><span
class="type">string</span> `$words`</span> \[, <span
class="methodparam"><span class="type">array</span> `$opts`</span> \] )

Connects to searchd, requests it to generate excerpts (snippets) from
the given documents, and returns the results.

### Parameters

`docs`  
Array of strings with documents' contents.

`index`  
Index name.

`words`  
Keywords to highlight.

`opts`  
Associative array of additional highlighting options (see below).

| Option             | Description                                                                                                           |
|--------------------|-----------------------------------------------------------------------------------------------------------------------|
| "before\_match"    | A string to insert before a keyword match. Default is "\<b\>".                                                        |
| "after\_match"     | A string to insert after a keyword match. Default is "\</b\>".                                                        |
| "chunk\_separator" | A string to insert between snippet chunks (passages). Default is " ... ".                                             |
| "limit"            | Maximum snippet size, in symbols (codepoints). Integer, default is 256.                                               |
| "around"           | How much words to pick around each matching keywords block. Integer, default is 5.                                    |
| "exact\_phrase"    | Whether to highlight exact query phrase matches only instead of individual keywords. Boolean, default is **`FALSE`**. |
| "single\_passage"  | Whether to extract single best passage only. Boolean, default is **`FALSE`**.                                         |

### Return Values

Returns array of snippets on success or **`FALSE`** on failure.

SphinxClient::buildKeywords
===========================

Extract keywords from query

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SphinxClient::buildKeywords</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> ,
<span class="methodparam"><span class="type">string</span>
`$index`</span> , <span class="methodparam"><span
class="type">bool</span> `$hits`</span> )

Extracts keywords from `query` using tokenizer settings for the given
`index`, optionally with per-keyword occurrence statistics.

### Parameters

`query`  
A query to extract keywords from.

`index`  
An index to get tokenizing settings and keyword occurrence statistics
from.

`hits`  
A boolean flag to enable/disable keyword statistics generation.

### Return Values

Returns an array of associative arrays with per-keyword information.

SphinxClient::close
===================

Closes previously opened persistent connection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::close</span> ( <span
class="methodparam">void</span> )

Closes previously opened persistent connection.

### Parameters

This function has no parameters.

### Changelog

| PECL/sphinx Version | Description                                                                             |
|---------------------|-----------------------------------------------------------------------------------------|
| 1.0.3               | Added SphinxClient::close(), available only if compiled with libsphinxclient \>= 0.9.9. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::open" class="xref"></a>

SphinxClient::\_\_construct
===========================

Create a new SphinxClient object

### Description

<span class="modifier">public</span> <span
class="methodname">SphinxClient::\_\_construct</span> ( <span
class="methodparam">void</span> )

Creates a new <span class="classname">SphinxClient</span> object.

### Parameters

This function has no parameters.

SphinxClient::escapeString
==========================

Escape special characters

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SphinxClient::escapeString</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> )

Escapes characters that are treated as special operators by the query
language parser.

### Parameters

`string`  
String to escape.

### Return Values

Returns escaped string.

SphinxClient::getLastError
==========================

Get the last error message

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SphinxClient::getLastError</span> ( <span
class="methodparam">void</span> )

Returns string with the last error message. If there were no errors
during the previous API call, empty string is returned. This method
doesn't reset the error message, so you can safely call it several
times.

### Parameters

This function has no parameters.

### Return Values

Returns the last error message or an empty string if there were no
errors.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::getLastWarning" class="xref"></a>

SphinxClient::getLastWarning
============================

Get the last warning

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SphinxClient::getLastWarning</span> ( <span
class="methodparam">void</span> )

Returns last warning message. If there were no warnings during the
previous API call, empty string is returned. This method doesn't reset
the warning, so you can safely call it several times.

### Parameters

This function has no parameters.

### Return Values

Returns the last warning message or an empty string if there were no
warnings.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::getLastError" class="xref"></a>

SphinxClient::open
==================

Opens persistent connection to the server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::open</span> ( <span
class="methodparam">void</span> )

Opens persistent connection to the server.

### Parameters

This function has no parameters.

### Changelog

| PECL/sphinx Version | Description                                                                            |
|---------------------|----------------------------------------------------------------------------------------|
| 1.0.3               | Added SphinxClient::open(), available only if compiled with libsphinxclient \>= 0.9.9. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::close" class="xref"></a>

SphinxClient::query
===================

Execute search query

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SphinxClient::query</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> \[,
<span class="methodparam"><span class="type">string</span> `$index`<span
class="initializer"> = "\*"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$comment`<span
class="initializer"> = ""</span></span> \]\] )

Connects to searchd server, runs the given search query with the current
settings, obtains and returns the result set.

### Parameters

`query`  
Query string.

`index`  
An index name (or names).

`comment`  

### Return Values

On success, <span class="function">SphinxClient::query</span> returns a
list of found matches and additional per-query statistics. The result
set is a hash utilize other structures instead of hash) with the
following keys and values:

| Key            | Value description                                                                         |
|----------------|-------------------------------------------------------------------------------------------|
| "matches"      | An array with found document IDs as keys and their weight and attributes values as values |
| "total"        | Total number of matches found and retrieved (depends on your settings)                    |
| "total\_found" | Total number of found documents matching the query                                        |
| "words"        | An array with words (case-folded and stemmed) as keys and per-word statistics as values   |
| "error"        | Query error message reported by searchd                                                   |
| "warning"      | Query warning reported by searchd                                                         |

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::runQueries" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::addQuery" class="xref"></a>

SphinxClient::resetFilters
==========================

Clear all filters

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SphinxClient::resetFilters</span> ( <span
class="methodparam">void</span> )

Clears all currently set filters. This call is normally required when
using multi-queries. You might want to set different filters for
different queries in the batch. To do that, you should call <span
class="function">SphinxClient::resetFilters</span> and add new filters
using the respective calls.

### Return Values

No value is returned.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::resetGroupBy" class="xref"></a>

SphinxClient::resetGroupBy
==========================

Clear all group-by settings

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SphinxClient::resetGroupBy</span> ( <span
class="methodparam">void</span> )

Clears all currently group-by settings, and disables group-by. This call
is normally required only when using multi-queries.

### Return Values

No value is returned.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::resetGroupBy" class="xref"></a>

SphinxClient::runQueries
========================

Run a batch of search queries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SphinxClient::runQueries</span> ( <span
class="methodparam">void</span> )

Connects to searchd, runs a batch of all queries added using
<a href="/class/sphinxclient.html#SphinxClient::addQuery" class="xref"></a>,
obtains and returns the result sets.

### Return Values

Returns **`FALSE`** on failure and array of result sets on success.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::addQuery" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::query" class="xref"></a>

SphinxClient::setArrayResult
============================

Change the format of result set array

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setArrayResult</span> ( <span
class="methodparam"><span class="type">bool</span> `$array_result`<span
class="initializer"> = **`FALSE`**</span></span> )

Controls the format of search results set arrays (whether matches should
be returned as an array or a hash).

### Parameters

`array_result`  
If `array_result` is **`FALSE`**, matches are returned as a hash with
document IDs as keys, and other information (weight, attributes) as
values. If `array_result` is **`TRUE`**, matches are returned as a plain
array with complete per-match information including document IDs.

### Return Values

Always returns **`TRUE`**.

SphinxClient::setConnectTimeout
===============================

Set connection timeout

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setConnectTimeout</span> ( <span
class="methodparam"><span class="type">float</span> `$timeout`</span> )

Sets connection timeout (in seconds) for searchd connection.

### Parameters

`timeout`  
Timeout in seconds.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setMaxQueryTime" class="xref"></a>

SphinxClient::setFieldWeights
=============================

Set field weights

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setFieldWeights</span> ( <span
class="methodparam"><span class="type">array</span> `$weights`</span> )

Binds per-field weights by name.

Match ranking can be affected by per-field weights. See
<a href="http://sphinxsearch.com/" class="link external">» Sphinx documentation</a>
for an explanation on how phrase proximity ranking is affected. This
call lets you specify non-default weights for full-text fields.

The weights must be positive 32-bit integers, so be careful not to hit
32-bit integer maximum. The final weight is a 32-bit integer too.
Default weight value is 1. Unknown field names are silently ignored.

### Parameters

`weights`  
Associative array of field names and field weights.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setIndexWeights" class="xref"></a>

SphinxClient::setFilter
=======================

Add new integer values set filter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setFilter</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">array</span>
`$values`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$exclude`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Adds new integer values set filter to the existing list of filters.

### Parameters

`attribute`  
An attribute name.

`values`  
Plain array of integer values.

`exclude`  
If set to **`TRUE`**, matching documents are excluded from the result
set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setFilterFloatRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setFilterRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::resetFilters" class="xref"></a>

SphinxClient::setFilterFloatRange
=================================

Add new float range filter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setFilterFloatRange</span> (
<span class="methodparam"><span class="type">string</span>
`$attribute`</span> , <span class="methodparam"><span
class="type">float</span> `$min`</span> , <span
class="methodparam"><span class="type">float</span> `$max`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$exclude`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Adds new float range filter to the existing list of filters. Only those
documents which have `attribute` value stored in the index between `min`
and `max` (including values that are exactly equal to `min` or `max`)
will be matched (or rejected, if `exclude` is **`TRUE`**).

### Parameters

`attribute`  
An attribute name.

`min`  
Minimum value.

`max`  
Maximum value.

`exclude`  
If set to **`TRUE`**, matching documents are excluded from the result
set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setFilterRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setFilter" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::resetFilters" class="xref"></a>

SphinxClient::setFilterRange
============================

Add new integer range filter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setFilterRange</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$min`</span>
, <span class="methodparam"><span class="type">int</span> `$max`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$exclude`<span class="initializer"> = **`FALSE`**</span></span> \] )

Adds new integer range filter to the existing list of filters. Only
those documents which have `attribute` value stored in the index between
`min` and `max` (including values that are exactly equal to `min` or
`max`) will be matched (or rejected, if `exclude` is **`TRUE`**).

### Parameters

`attribute`  
An attribute name.

`min`  
Minimum value.

`max`  
Maximum value.

`exclude`  
If set to **`TRUE`**, matching documents are excluded from the result
set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setFilterFloatRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setFilter" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::resetFilters" class="xref"></a>

SphinxClient::setGeoAnchor
==========================

Set anchor point for a geosphere distance calculations

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setGeoAnchor</span> ( <span
class="methodparam"><span class="type">string</span> `$attrlat`</span> ,
<span class="methodparam"><span class="type">string</span>
`$attrlong`</span> , <span class="methodparam"><span
class="type">float</span> `$latitude`</span> , <span
class="methodparam"><span class="type">float</span> `$longitude`</span>
)

Sets anchor point for a geosphere distance (geodistance) calculations
and enables them.

Once an anchor point is set, you can use magic "@geodist" attribute name
in your filters and/or sorting expressions.

### Parameters

`attrlat`  
Name of a latitude attribute.

`attrlong`  
Name of a longitude attribute.

`latitude`  
Anchor latitude in radians.

`longitude`  
Anchor longitude in radians.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setFilterFloatRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setFilterRange" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setFilter" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::resetFilters" class="xref"></a>

SphinxClient::setGroupBy
========================

Set grouping attribute

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setGroupBy</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$func`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$groupsort`<span class="initializer"> = "@group desc"</span></span> \]
)

Sets grouping attribute, function, and group sorting mode, and enables
grouping.

Grouping feature is very similar to GROUP BY clause in SQL. Results
produced by this function call are going to be the same as produced by
the following pseudo code: **SELECT ... GROUP BY $func($attribute) ORDER
BY $groupsort**.

### Parameters

`attribute`  
A string containing group-by attribute name.

`func`  
Constant, which sets a function applied to the attribute value in order
to compute group-by key.

`groupsort`  
An optional clause controlling how the groups are sorted.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::resetGroupBy" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setSortMode" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setGroupDistinct" class="xref"></a>

SphinxClient::setGroupDistinct
==============================

Set attribute name for per-group distinct values count calculations

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setGroupDistinct</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
)

Sets attribute name for per-group distinct values count calculations.
Only available for grouping queries. For each group, all values of
`attribute` will be stored, then the amount of distinct values will be
calculated and returned to the client. This feature is similar to
COUNT(DISTINCT) clause in SQL.

### Parameters

`attribute`  
A string containing group-by attribute name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setSortMode" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setGroupBy" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::resetGroupBy" class="xref"></a>

SphinxClient::setIDRange
========================

Set a range of accepted document IDs

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setIDRange</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

Sets an accepted range of document IDs. Default range is from 0 to 0,
i.e. no limit. Only those records that have document ID between `min`
and `max` (including IDs exactly equal to `min` or `max`) will be
matched.

### Parameters

`min`  
Minimum ID value.

`max`  
Maximum ID value.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setIndexWeights
=============================

Set per-index weights

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setIndexWeights</span> ( <span
class="methodparam"><span class="type">array</span> `$weights`</span> )

Sets per-index weights and enables weighted summing of match weights
across different indexes.

### Parameters

`weights`  
An associative array mapping string index names to integer weights.
Default is empty array, i.e. weighting summing is disabled.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setLimits
=======================

Set offset and limit of the result set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setLimits</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> ,
<span class="methodparam"><span class="type">int</span> `$limit`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$max_matches`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$cutoff`<span
class="initializer"> = 0</span></span> \]\] )

Sets `offset` into server-side result set and amount of matches to
return to client starting from that offset (`limit`). Can additionally
control maximum server-side result set size for current query
(`max_matches`) and the threshold amount of matches to stop searching at
(`cutoff`).

### Parameters

`offset`  
Result set offset.

`limit`  
Amount of matches to return.

`max_matches`  
Controls how much matches searchd will keep in RAM while searching.

`cutoff`  
Used for advanced performance control. It tells searchd to forcibly stop
search query once `cutoff` matches have been found and processed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setMatchMode
==========================

Set full-text query matching mode

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setMatchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Sets full-text query matching mode. `mode` is one of the constants
listed below.

| Constant              | Description                                                                     |
|-----------------------|---------------------------------------------------------------------------------|
| SPH\_MATCH\_ALL       | Match all query words (default mode).                                           |
| SPH\_MATCH\_ANY       | Match any of query words.                                                       |
| SPH\_MATCH\_PHRASE    | Match query as a phrase, requiring perfect match.                               |
| SPH\_MATCH\_BOOLEAN   | Match query as a boolean expression.                                            |
| SPH\_MATCH\_EXTENDED  | Match query as an expression in Sphinx internal query language.                 |
| SPH\_MATCH\_FULLSCAN  | Enables fullscan.                                                               |
| SPH\_MATCH\_EXTENDED2 | The same as **`SPH_MATCH_EXTENDED`** plus ranking and quorum searching support. |

### Parameters

`mode`  
Matching mode.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setRankingMode" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setSortMode" class="xref"></a>

SphinxClient::setMaxQueryTime
=============================

Set maximum query time

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setMaxQueryTime</span> ( <span
class="methodparam"><span class="type">int</span> `$qtime`</span> )

Sets maximum search query time.

### Parameters

`qtime`  
Maximum query time, in milliseconds. It must be a non-negative integer.
Default value is 0, i.e. no limit.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setOverride
=========================

Sets temporary per-document attribute value overrides

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setOverride</span> ( <span
class="methodparam"><span class="type">string</span> `$attribute`</span>
, <span class="methodparam"><span class="type">int</span> `$type`</span>
, <span class="methodparam"><span class="type">array</span>
`$values`</span> )

Sets temporary (per-query) per-document attribute value overrides.
Override feature lets you "temporary" update attribute values for some
documents within a single query, leaving all other queries unaffected.
This might be useful for personalized data

### Parameters

`attribute`  
An attribute name.

`type`  
An attribute type. Only supports scalar attributes.

`values`  
Array of attribute values that maps document IDs to overridden attribute
values.

### Changelog

| PECL/sphinx Version | Description                                                                                   |
|---------------------|-----------------------------------------------------------------------------------------------|
| 1.0.3               | Added SphinxClient::setOverride(), available only if compiled with libsphinxclient \>= 0.9.9. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setRankingMode
============================

Set ranking mode

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setRankingMode</span> ( <span
class="methodparam"><span class="type">int</span> `$ranker`</span> )

Sets ranking mode. Only available in **`SPH_MATCH_EXTENDED2`** matching
mode.

| Constant                   | Description                                                                                                                                                                                            |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SPH\_RANK\_PROXIMITY\_BM25 | Default ranking mode which uses both proximity and BM25 ranking.                                                                                                                                       |
| SPH\_RANK\_BM25            | Statistical ranking mode which uses BM25 ranking only (similar to most of other full-text engines). This mode is faster, but may result in worse quality on queries which contain more than 1 keyword. |
| SPH\_RANK\_NONE            | Disables ranking. This mode is the fastest. It is essentially equivalent to boolean searching, a weight of 1 is assigned to all matches.                                                               |

### Parameters

`ranker`  
Ranking mode.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setMatchMode" class="xref"></a>

SphinxClient::setRetries
========================

Set retry count and delay

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setRetries</span> ( <span
class="methodparam"><span class="type">int</span> `$count`</span> \[,
<span class="methodparam"><span class="type">int</span> `$delay`<span
class="initializer"> = 0</span></span> \] )

Sets distributed retry count and delay.

On temporary failures searchd will attempt up to `count` retries per
agent. `delay` is the delay between the retries, in milliseconds.
Retries are disabled by default. Note that this call will not make the
API itself retry on temporary failure; it only tells searchd to do so.

### Parameters

`count`  
Number of retries.

<!-- -->

`delay`  
Delay between retries, in milliseconds.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setSelect
=======================

Set select clause

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setSelect</span> ( <span
class="methodparam"><span class="type">string</span> `$clause`</span> )

Sets the select clause, listing specific attributes to fetch, and
expressions to compute and fetch.

### Parameters

`clause`  
SQL-like clause.

### Changelog

| PECL/sphinx Version | Description                                                                                 |
|---------------------|---------------------------------------------------------------------------------------------|
| 1.0.1               | Added SphinxClient::setSelect(), available only if compiled with libsphinxclient \>= 0.9.9. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setServer
=======================

Set searchd host and port

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setServer</span> ( <span
class="methodparam"><span class="type">string</span> `$server`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> )

Sets searchd host name and TCP port. All subsequent requests will use
the new host and port settings. Default host and port are 'localhost'
and 3312, respectively.

### Parameters

`server`  
IP or hostname.

`port`  
Port number.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

SphinxClient::setSortMode
=========================

Set matches sorting mode

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SphinxClient::setSortMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$sortby`</span> \] )

Sets matches sorting mode. See available modes below.

| Constant                  | Description                                                                                                      |
|---------------------------|------------------------------------------------------------------------------------------------------------------|
| SPH\_SORT\_RELEVANCE      | Sort by relevance in descending order (best matches first).                                                      |
| SPH\_SORT\_ATTR\_DESC     | Sort by an attribute in descending order (bigger attribute values first).                                        |
| SPH\_SORT\_ATTR\_ASC      | Sort by an attribute in ascending order (smaller attribute values first).                                        |
| SPH\_SORT\_TIME\_SEGMENTS | Sort by time segments (last hour/day/week/month) in descending order, and then by relevance in descending order. |
| SPH\_SORT\_EXTENDED       | Sort by SQL-like combination of columns in ASC/DESC order.                                                       |
| SPH\_SORT\_EXPR           | Sort by an arithmetic expression.                                                                                |

### Parameters

`mode`  
Sorting mode.

`sortby`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/class/sphinxclient.html#SphinxClient::setMatchMode" class="xref"></a>
-   <a href="/class/sphinxclient.html#SphinxClient::setSortMode" class="xref"></a>

SphinxClient::status
====================

Queries searchd status

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SphinxClient::status</span> ( <span
class="methodparam">void</span> )

Queries searchd status, and returns an array of status variable name and
value pairs.

### Parameters

This function has no parameters.

### Changelog

| PECL/sphinx Version | Description                                                                              |
|---------------------|------------------------------------------------------------------------------------------|
| 1.0.3               | Added SphinxClient::status(), available only if compiled with libsphinxclient \>= 0.9.9. |

### Return Values

Returns an associative array of search server statistics or **`FALSE`**
on failure.

SphinxClient::updateAttributes
==============================

Update document attributes

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SphinxClient::updateAttributes</span> ( <span
class="methodparam"><span class="type">string</span> `$index`</span> ,
<span class="methodparam"><span class="type">array</span>
`$attributes`</span> , <span class="methodparam"><span
class="type">array</span> `$values`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$mva`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Instantly updates given attribute values in given documents.

### Parameters

`index`  
Name of the index (or indexes) to be updated.

`attributes`  
Array of attribute names, listing attributes that are updated.

`values`  
Associative array containing document IDs as keys and array of attribute
values as values.

### Return Values

Returns number of actually updated documents (0 or more) on success, or
**`FALSE`** on failure.
