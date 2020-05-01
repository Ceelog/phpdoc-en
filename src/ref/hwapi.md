Integration with Apache
-----------------------

The integration with Apache and possible other servers has been
described in the
<a href="/hwapi/apache-integration.html" class="link">separate chapter</a>.

Classes
-------

The API provided by the HW\_API extension is fully object oriented. It
is very similar to the C++ interface of the Hyperwave SDK. It consist of
the following classes.

-   <span class="simpara"> <span class="classname">HW\_API</span>
    </span>
-   <span class="simpara"> <span
    class="classname">HW\_API\_Object</span> </span>
-   <span class="simpara"> <span
    class="classname">HW\_API\_Attribute</span> </span>
-   <span class="simpara"> <span class="classname">HW\_API\_Error</span>
    </span>
-   <span class="simpara"> <span
    class="classname">HW\_API\_Content</span> </span>
-   <span class="simpara"> <span
    class="classname">HW\_API\_Reason</span> </span>

Some basic classes like <span class="classname">HW\_API\_String</span>,
<span class="classname">HW\_API\_String\_Array</span>, etc., which exist
in the Hyperwave SDK have not been implemented since PHP has powerful
replacements for them.

Each class has certain method, whose names are identical to its
counterparts in the Hyperwave SDK. Passing arguments to this function
differs from all the other PHP extensions but is close to the C++ API of
the HW SDK. Instead of passing several parameters they are all put into
an associated array and passed as one parameter. The names of the keys
are identical to those documented in the HW SDK. The common parameters
are listed below. If other parameters are required they will be
documented if needed.

-   <span class="simpara"> <span
    class="classname">objectIdentifier</span> The name or id of an
    object, e.g. "rootcollection", "0x873A8768 0x00000002". </span>
-   <span class="simpara"> <span
    class="classname">parentIdentifier</span> The name or id of an
    object which is considered to be a parent. </span>
-   <span class="simpara"> <span class="classname">object</span> An
    instance of class HW\_API\_Object. </span>
-   <span class="simpara"> <span class="classname">parameters</span> An
    instance of class HW\_API\_Object. </span>
-   <span class="simpara"> <span class="classname">version</span> The
    version of an object. </span>
-   <span class="simpara"> <span class="classname">mode</span> An
    integer value determine the way an operation is executed. </span>
-   <span class="simpara"> <span
    class="classname">attributeSelector</span> Any array of strings,
    each containing a name of an attribute. This is used if you retrieve
    the object record and want to include certain attributes. </span>
-   <span class="simpara"> <span class="classname">objectQuery</span> A
    query to select certain object out of a list of objects. This is
    used to reduce the number of objects which was delivered by a
    function like <span class="function">hw\_api::children</span> or
    <span class="function">hw\_api::find</span>. </span>

> **Note**:
>
> Methods returning <span class="type">boolean</span> can return
> **`TRUE`**, **`FALSE`** or <span
> class="classname">HW\_API\_Error</span> object.

hw\_api::checkin
================

Checks in an object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::checkin</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function checks in an object or a whole hierarchy of objects. The
parameters array contains the required element 'objectIdentifier' and
the optional element 'version', 'comment', 'mode' and 'objectQuery'.
'version' sets the version of the object. It consists of the major and
minor version separated by a period. If the version is not set, the
minor version is incremented. 'mode' can be one of the following values:

HW\_API\_CHECKIN\_NORMAL  
<span class="simpara"> Checks in and commits the object. The object must
be a document. </span>

HW\_API\_CHECKIN\_RECURSIVE  
<span class="simpara"> If the object to check in is a collection, all
children will be checked in recursively if they are documents. Trying to
check in a collection would result in an error. </span>

HW\_API\_CHECKIN\_FORCE\_VERSION\_CONTROL  
<span class="simpara"> Checks in an object even if it is not under
version control. </span>

HW\_API\_CHECKIN\_REVERT\_IF\_NOT\_CHANGED  
<span class="simpara"> Check if the new version is different from the
last version. Unless this is the case the object will be checked in.
</span>

HW\_API\_CHECKIN\_KEEP\_TIME\_MODIFIED  
<span class="simpara"> Keeps the time modified from the most recent
object. </span>

HW\_API\_CHECKIN\_NO\_AUTO\_COMMIT  
<span class="simpara"> The object is not automatically committed on
check-in. </span>

### Parameters

`parameter`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api::checkout" class="xref"></a>

hw\_api::checkout
=================

Checks out an object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::checkout</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function checks out an object or a whole hierarchy of objects.

### Parameters

`parameter`  
The parameters array contains the required element 'objectIdentifier'
and the optional element 'version', 'mode' and 'objectQuery'. 'mode' can
be one of the following values:

**`HW_API_CHECKIN_NORMAL`**  
<span class="simpara"> Checks out an object. The object must be a
document. </span>

**`HW_API_CHECKIN_RECURSIVE`**  
<span class="simpara"> If the object to check out is a collection, all
children will be checked out recursively if they are documents. Trying
to check out a collection would result in an error. </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api::checkin" class="xref"></a>

hw\_api::children
=================

Returns children of an object

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::children</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves the children of a collection or the attributes of a document.
The children can be further filtered by specifying an object query.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectIdentifier'
and the optional elements 'attributeSelector' and 'objectQuery'.

### Return Values

The return value is an array of objects of type <span
class="classname">HW\_API\_Object</span> or <span
class="classname">HW\_API\_Error</span>.

### See Also

-   <a href="/ref/hwapi.html#hw_api::parents" class="xref"></a>

hw\_api::content
================

Returns content of an object

### Description

<span class="type">HW\_API\_Content</span> <span
class="methodname">hw\_api::content</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function returns the content of a document as an object of type
<span class="classname">hw\_api\_content</span>.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectidentifier'
and the optional element 'mode'. The mode can be one of the constants
**`HW_API_CONTENT_ALLLINKS`**, **`HW_API_CONTENT_REACHABLELINKS`** or
**`HW_API_CONTENT_PLAIN`**.

**`HW_API_CONTENT_ALLLINKS`** means to insert all anchors even if the
destination is not reachable.

**`HW_API_CONTENT_REACHABLELINKS`** tells this method to insert only
reachable links and **`HW_API_CONTENT_PLAIN`** will lead to document
without any links.

### Return Values

Returns an instance of <span class="classname">hw\_api\_content</span>.

hw\_api::copy
=============

Copies physically

### Description

<span class="type">hw\_api\_content</span> <span
class="methodname">hw\_api::copy</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function will make a physical copy including the content if it
exists and returns the new object or an error object.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectIdentifier'
and 'destinationParentIdentifier'. The optional parameter is
'attributeSelector'\`

### Return Values

Returns the copied object.

### See Also

-   <a href="/ref/hwapi.html#hw_api::move" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::link" class="xref"></a>

hw\_api::dbstat
===============

Returns statistics about database server

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::dbstat</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns statistics about database server.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dcstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::hwstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::ftstat" class="xref"></a>

hw\_api::dcstat
===============

Returns statistics about document cache server

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::dcstat</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns statistics about document cache server.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dbstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::hwstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::ftstat" class="xref"></a>

hw\_api::dstanchors
===================

Returns a list of all destination anchors

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::dstanchors</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves all destination anchors of an object.

### Parameters

`parameter`  
The parameter array contains the required element 'objectIdentifier' and
the optional elements 'attributeSelector' and 'objectQuery'.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::srcanchors" class="xref"></a>

hw\_api::dstofsrcanchor
=======================

Returns destination of a source anchor

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::dstofsrcanchor</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves the destination object pointed by the specified source
anchors. The destination object can either be a destination anchor or a
whole document.

### Parameters

`parameter`  
The parameters array contains the required element 'objectIdentifier'
and the optional element 'attributeSelector'.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::srcanchors" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::dstanchors" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::objectbyanchor" class="xref"></a>

hw\_api::find
=============

Search for objects

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::find</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This functions searches for objects either by executing a key or/and
full text query. The found objects can further be filtered by an
optional object query. They are sorted by their importance. The second
search operation is relatively slow and its result can be limited to a
certain number of hits. This allows to perform an incremental search,
each returning just a subset of all found documents, starting at a given
index.

### Parameters

`parameter`  
The parameter array contains the 'keyquery' or/and 'fulltextquery'
depending on who you would like to search. Optional parameters are
'objectquery', 'scope', 'languages' and 'attributeselector'. In case of
an incremental search the optional parameters 'startIndex',
'numberOfObjectsToGet' and 'exactMatchUnit' can be passed.

### Return Values

hw\_api::ftstat
===============

Returns statistics about fulltext server

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::ftstat</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns statistics about fulltext server.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dcstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::dbstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::hwstat" class="xref"></a>

hw\_api::hwstat
===============

Returns statistics about Hyperwave server

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::hwstat</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns statistics about Hyperwave server.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dcstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::dbstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::ftstat" class="xref"></a>

hw\_api::identify
=================

Log into Hyperwave Server

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::identify</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Logs into the Hyperwave Server.

### Parameters

`parameter`  
The parameter array must contain the elements 'username' and 'password'.

### Return Values

Returns an object of type<span class="classname">HW\_API\_Error</span>
if identification failed or **`TRUE`** if it was successful.

hw\_api::info
=============

Returns information about server configuration

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::info</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns information about server configuration.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dcstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::dbstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::ftstat" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::hwstat" class="xref"></a>

hw\_api::insert
===============

Inserts a new object

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::insert</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Insert a new object. The object type can be user, group, document or
anchor. Depending on the type other object attributes has to be set.

### Parameters

`parameter`  
The parameter array contains the required elements 'object' and
'content' (if the object is a document) and the optional parameters
'parameters', 'mode' and 'attributeSelector'. The 'object' must contain
all attributes of the object. 'parameters' is an object as well holding
further attributes like the destination (attribute key is 'Parent').
'content' is the content of the document. 'mode' can be a combination of
the following flags:

**`HW_API_INSERT_NORMAL`**  
<span class="simpara"> The object in inserted into the server. </span>

**`HW_API_INSERT_FORCE_VERSION_CONTROL`**  
<span class="simpara"> </span>

**`HW_API_INSERT_AUTOMATIC_CHECKOUT`**  
<span class="simpara"> </span>

**`HW_API_INSERT_PLAIN`**  
<span class="simpara"> </span>

**`HW_API_INSERT_KEEP_TIME_MODIFIED`**  
<span class="simpara"> </span>

**`HW_API_INSERT_DELAY_INDEXING`**  
<span class="simpara"> </span>

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::replace" class="xref"></a>

hw\_api::insertanchor
=====================

Inserts a new object of type anchor

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::insertanchor</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function is a shortcut for <span
class="function">hwapi\_insert</span>. It inserts an object of type
anchor and sets some of the attributes required for an anchor.

### Parameters

`parameter`  
The parameter array contains the required elements 'object' and
'documentIdentifier' and the optional elements 'destinationIdentifier',
'parameter', 'hint' and 'attributeSelector'. The 'documentIdentifier'
specifies the document where the anchor shall be inserted. The target of
the anchor is set in 'destinationIdentifier' if it already exists. If
the target does not exists the element 'hint' has to be set to the name
of object which is supposed to be inserted later. Once it is inserted
the anchor target is resolved automatically.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::insert" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertdocument" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertcollection" class="xref"></a>

hw\_api::insertcollection
=========================

Inserts a new object of type collection

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::insertcollection</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function is a shortcut for <span
class="function">hwapi\_insert</span>. It inserts an object of type
collection and sets some of the attributes required for a collection.

### Parameters

`parameter`  
The parameter array contains the required elements 'object' and
'parentIdentifier' and the optional elements 'parameter' and
'attributeSelector'. See <span class="function">hwapi\_insert</span> for
the meaning of each element.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::insert" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertdocument" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertanchor" class="xref"></a>

hw\_api::insertdocument
=======================

Inserts a new object of type document

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::insertdocument</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function is a shortcut for <span
class="function">hwapi\_insert</span>. It inserts an object with content
and sets some of the attributes required for a document.

### Parameters

`parameter`  
The parameter array contains the required elements 'object',
'parentIdentifier' and 'content' and the optional elements 'mode',
'parameter' and 'attributeSelector'.

See <span class="function">hwapi\_insert</span> for the meaning of each
element.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::insert" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertcollection" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::insertanchor" class="xref"></a>

hw\_api::link
=============

Creates a link to an object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::link</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Creates a link to an object. Accessing this link is like accessing the
object to links points to.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectIdentifier'
and 'destinationParentIdentifier'. 'destinationParentIdentifier' is the
target collection.

### Return Values

The function returns **`TRUE`** on success or an error object.

### See Also

-   <a href="/ref/hwapi.html#hw_api::copy" class="xref"></a>

hw\_api::lock
=============

Locks an object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::lock</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Locks an object for exclusive editing by the user calling this function.
The object can be only unlocked by this user or the system user.

### Parameters

`parameter`  
The parameter array contains the required element 'objectIdentifier' and
the optional parameters 'mode' and 'objectquery'.

'mode' determines how an object is locked. **`HW_API_LOCK_NORMAL`**
means, an object is locked until it is unlocked.
**`HW_API_LOCK_RECURSIVE`** is only valid for collection and locks all
objects within the collection and possible subcollections.
**`HW_API_LOCK_SESSION`** means, an object is locked only as long as the
session is valid.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api::unlock" class="xref"></a>

hw\_api::move
=============

Moves object between collections

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::move</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Moves object between collections.

### Parameters

`parameter`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">hw\_objrec2array</span>

hw\_api::object
===============

Retrieve attribute information

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::object</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function retrieves the attribute information of an object of any
version. It will not return the document content.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectIdentifier'
and the optional elements 'attributeSelector' and 'version'.

### Return Values

The returned object is an instance of class <span
class="classname">HW\_API\_Object</span> on success or <span
class="classname">HW\_API\_Error</span> if an error occurred.

### Examples

This simple example retrieves an object and checks for errors.

**Example \#1 Retrieve an object**

``` php
<?php
function handle_error($error)
{
  $reason = $error->reason(0);
  echo "Type: <b>";
  switch ($reason->type()) {
    case 0:
      echo "Error";
      break;
    case 1:
      echo "Warning";
      break;
    case 2:
      echo "Message";
      break;
  }
  echo "</b><br />\n";
  echo "Description: " . $reason->description("en") . "<br />\n";
}

function list_attr($obj)
{
  echo "<table>\n";
  $count = $obj->count();
  for ($i=0; $i<$count; $i++) {
    $attr = $obj->attribute($i);
    printf("<tr><td align=\"right\" bgcolor=\"#c0c0c0\"><b>%s</b></td><td bgcolor=\"#F0F0F0\">%s</td></tr>\n",
             $attr->key(), $attr->value());
  }
  echo "</table>\n";
}

$hwapi = hwapi_hgcsp($g_config[HOSTNAME]);
$parms = array("objectIdentifier"=>"rootcollection", "attributeSelector"=>array("Title", "Name", "DocumentType"));
$root = $hwapi->object($parms);
if (get_class($root) == "HW_API_Error") {
  handle_error($root);
  exit;
}
list_attr($root);
?>
```

### See Also

-   <a href="/ref/hwapi.html#hw_api::content" class="xref"></a>

hw\_api::objectbyanchor
=======================

Returns the object an anchor belongs to

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::objectbyanchor</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

This function retrieves an object the specified anchor belongs to.

### Parameters

`parameter`  
The parameter array contains the required element 'objectIdentifier' and
the optional element 'attributeSelector'.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dstofsrcanchor" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::srcanchors" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::dstanchors" class="xref"></a>

hw\_api::parents
================

Returns parents of an object

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::parents</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves the parents of an object. The parents can be further filtered
by specifying an object query.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectidentifier'
and the optional elements 'attributeselector' and 'objectquery'.

### Return Values

The return value is an array of objects of type <span
class="classname">HW\_API\_Object</span> or <span
class="classname">HW\_API\_Error</span>.

### See Also

-   <a href="/ref/hwapi.html#hw_api::children" class="xref"></a>

hw\_api::remove
===============

Delete an object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::remove</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Removes an object from the specified parent. Collections will be removed
recursively.

### Parameters

`parameter`  
You can pass an optional object query to remove only those objects which
match the query. An object will be deleted physically if it is the last
instance.

The parameter array contains the required elements 'objectidentifier'
and 'parentidentifier'. If you want to remove a user or group
'parentidentifier' can be skipped.

The optional parameter 'mode' determines how the deletion is performed.
In normal mode the object will not be removed physically until all
instances are removed. In physical mode all instances of the object will
be deleted immediately. In removelinks mode all references to and from
the objects will be deleted as well. In nonrecursive the deletion is not
performed recursive. Removing a collection which is not empty will cause
an error.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api::move" class="xref"></a>

hw\_api::replace
================

Replaces an object

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::replace</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Replaces the attributes and the content of an object.

### Parameters

`parameter`  
The parameter array contains the required elements 'objectIdentifier'
and 'object' and the optional parameters 'content', 'parameters', 'mode'
and 'attributeSelector'. 'objectIdentifier' contains the object to be
replaced. 'object' contains the new object. 'content' contains the new
content. 'parameters' contain extra information for HTML documents.
HTML\_Language is the letter abbreviation of the language of the title.
HTML\_Base sets the base attribute of the HTML document.

'mode' can be a combination of the following flags:

**`HW_API_REPLACE_NORMAL`**  
<span class="simpara"> The object on the server is replace with the
object passed. </span>

**`HW_API_REPLACE_FORCE_VERSION_CONTROL`**  
<span class="simpara"> </span>

**`HW_API_REPLACE_AUTOMATIC_CHECKOUT`**  
<span class="simpara"> </span>

**`HW_API_REPLACE_AUTOMATIC_CHECKIN`**  
<span class="simpara"> </span>

**`HW_API_REPLACE_PLAIN`**  
<span class="simpara"> </span>

**`HW_API_REPLACE_REVERT_IF_NOT_CHANGED`**  
<span class="simpara"> </span>

**`HW_API_REPLACE_KEEP_TIME_MODIFIED`**  
<span class="simpara"> </span>

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::insert" class="xref"></a>

hw\_api::setcommittedversion
============================

Commits version other than last version

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::setcommittedversion</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Commits a version of a document. The committed version is the one which
is visible to users with read access. By default the last version is the
committed version.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::checkin" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api::checkout" class="xref"></a>

hw\_api::srcanchors
===================

Returns a list of all source anchors

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::srcanchors</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves all source anchors of an object.

### Parameters

`parameter`  
The parameter array contains the required element 'objectIdentifier' and
the optional elements 'attributeSelector' and 'objectQuery'.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dstanchors" class="xref"></a>

hw\_api::srcsofdst
==================

Returns source of a destination object

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::srcsofdst</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Retrieves all the source anchors pointing to the specified destination.
The destination object can either be a destination anchor or a whole
document.

### Parameters

`parameter`  
The parameters array contains the required element 'objectIdentifier'
and the optional element 'attributeSelector' and 'objectQuery'. The
function returns an array of objects or an error.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::dstofsrcanchor" class="xref"></a>

hw\_api::unlock
===============

Unlocks a locked object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api::unlock</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Unlocks a locked object. Only the user who has locked the object and the
system user may unlock an object.

### Parameters

`parameter`  
The parameter array contains the required element 'objectIdentifier' and
the optional parameters 'mode' and 'objectquery'. The meaning of 'mode'
is the same as in function <span class="function">hwapi\_lock</span>.

### Return Values

Returns **`TRUE`** on success or an object of class HW\_API\_Error.

### See Also

-   <a href="/ref/hwapi.html#hw_api::lock" class="xref"></a>

hw\_api::user
=============

Returns the own user object

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hw\_api::user</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns the own user object.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::userlist" class="xref"></a>

hw\_api::userlist
=================

Returns a list of all logged in users

### Description

<span class="type">array</span> <span
class="methodname">hw\_api::userlist</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns a list of all logged in users.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::user" class="xref"></a>

hw\_api\_attribute::key
=======================

Returns key of the attribute

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_attribute::key</span> ( <span
class="methodparam">void</span> )

Returns the name of the attribute.

### Return Values

Returns the name of the attribute as a string.

### See Also

-   <a href="/ref/hwapi.html#hw_api_attribute::value" class="xref"></a>

hw\_api\_attribute::langdepvalue
================================

Returns value for a given language

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_attribute::langdepvalue</span> ( <span
class="methodparam"><span class="type">string</span> `$language`</span>
)

Returns the value in the given language of the attribute.

### Parameters

`language`  

### Return Values

Returns the value of the attribute as a string.

### See Also

-   <a href="/ref/hwapi.html#hw_api_attribute::value" class="xref"></a>

hw\_api\_attribute::value
=========================

Returns value of the attribute

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_attribute::value</span> ( <span
class="methodparam">void</span> )

Gets the value of the attribute.

### Return Values

Returns the value, as a string.

### See Also

-   <a href="/ref/hwapi.html#hw_api_attribute::key" class="xref"></a>
-   <a href="/ref/hwapi.html#hw_api_attribute::values" class="xref"></a>

hw\_api\_attribute::values
==========================

Returns all values of the attribute

### Description

<span class="type">array</span> <span
class="methodname">hw\_api\_attribute::values</span> ( <span
class="methodparam">void</span> )

Gets all values of the attribute.

### Return Values

Returns an array of attribute values.

### See Also

-   <a href="/ref/hwapi.html#hw_api_attribute::value" class="xref"></a>

hw\_api\_content::mimetype
==========================

Returns mimetype

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_content::mimetype</span> ( <span
class="methodparam">void</span> )

Returns the mimetype of the content.

### Return Values

Returns the mimetype as a string.

hw\_api\_content::read
======================

Read content

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_content::read</span> ( <span
class="methodparam"><span class="type">string</span> `$buffer`</span> ,
<span class="methodparam"><span class="type">int</span> `$len`</span> )

Reads `len` bytes from the content into the given buffer.

### Parameters

`buffer`  

`len`  
Number of bytes to read.

### Return Values

hw\_api\_error::count
=====================

Returns number of reasons

### Description

<span class="type">int</span> <span
class="methodname">hw\_api\_error::count</span> ( <span
class="methodparam">void</span> )

Returns the number of error reasons.

### Return Values

Returns the number of errors, as an integer.

### See Also

-   <a href="/ref/hwapi.html#hw_api_error::reason" class="xref"></a>

hw\_api\_error::reason
======================

Returns reason of error

### Description

<span class="type">HW\_API\_Reason</span> <span
class="methodname">hw\_api\_error::reason</span> ( <span
class="methodparam">void</span> )

Returns the first error reason.

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api_error::count" class="xref"></a>

hw\_api\_object::assign
=======================

Clones object

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api\_object::assign</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Clones the attributes of an object.

### Parameters

`parameter`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

hw\_api\_object::attreditable
=============================

Checks whether an attribute is editable

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api\_object::attreditable</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Checks whether an attribute is editable.

### Parameters

`parameter`  

### Return Values

Returns **`TRUE`** if the attribute is editable, **`FALSE`** otherwise.

hw\_api\_object::count
======================

Returns number of attributes

### Description

<span class="type">int</span> <span
class="methodname">hw\_api\_object::count</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns the number of attributes.

### Parameters

`parameter`  

### Return Values

Returns the number as an integer.

hw\_api\_object::insert
=======================

Inserts new attribute

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api\_object::insert</span> ( <span
class="methodparam"><span class="type">HW\_API\_Attribute</span>
`$attribute`</span> )

Adds an attribute to the object.

### Parameters

`attribute`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api_object::remove" class="xref"></a>

hw\_api\_object::remove
=======================

Removes attribute

### Description

<span class="type">bool</span> <span
class="methodname">hw\_api\_object::remove</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Removes the attribute with the given name.

### Parameters

`name`  
The attribute name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <a href="/ref/hwapi.html#hw_api_object::insert" class="xref"></a>

hw\_api\_object::title
======================

Returns the title attribute

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_object::title</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Returns the title attribute.

### Parameters

`parameter`  

### Return Values

Returns the title as a string.

hw\_api\_object::value
======================

Returns value of attribute

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_object::value</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Returns value of an attribute.

### Parameters

`name`  
The attribute name.

### Return Values

Returns the value of the attribute with the given name or **`FALSE`** if
an error occurred.

hw\_api\_reason::description
============================

Returns description of reason

### Description

<span class="type">string</span> <span
class="methodname">hw\_api\_reason::description</span> ( <span
class="methodparam">void</span> )

Returns the description of a reason

### Return Values

Returns the description, as a string.

hw\_api\_reason::type
=====================

Returns type of reason

### Description

<span class="type">HW\_API\_Reason</span> <span
class="methodname">hw\_api\_reason::type</span> ( <span
class="methodparam">void</span> )

Returns the type of a reason.

### Return Values

Returns an instance of <span class="classname">HW\_API\_Reason</span>.

hwapi\_attribute\_new
=====================

Creates instance of class hw\_api\_attribute

### Description

<span class="type">HW\_API\_Attribute</span> <span
class="methodname">hwapi\_attribute\_new</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \]\] )

Creates a new instance of hw\_api\_attribute with the given name and
value.

### Parameters

`name`  
The attribute name.

`value`  
The attribute value.

### Return Values

Returns an instance of <span
class="classname">hw\_api\_attribute</span>.

hwapi\_content\_new
===================

Create new instance of class hw\_api\_content

### Description

<span class="type">HW\_API\_Content</span> <span
class="methodname">hwapi\_content\_new</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span> ,
<span class="methodparam"><span class="type">string</span>
`$mimetype`</span> )

Creates a new content object from the string `content`.

### Parameters

`content`  

`mimetype`  
The mimetype for the contents.

### Return Values

hwapi\_hgcsp
============

Returns object of class hw\_api

### Description

<span class="type">HW\_API</span> <span
class="methodname">hwapi\_hgcsp</span> ( <span class="methodparam"><span
class="type">string</span> `$hostname`</span> \[, <span
class="methodparam"><span class="type">int</span> `$port`</span> \] )

Opens a connection to the Hyperwave server on host `hostname`. The
protocol used is HGCSP.

### Parameters

`hostname`  
The host name.

`port`  
If you do not pass a port number, 418 is used.

### Return Values

Returns an instance of <span class="classname">HW\_API</span>.

hwapi\_object\_new
==================

Creates a new instance of class hwapi\_object\_new

### Description

<span class="type">hw\_api\_object</span> <span
class="methodname">hwapi\_object\_new</span> ( <span
class="methodparam"><span class="type">array</span> `$parameter`</span>
)

Creates a new instance of the class <span
class="classname">hw\_api\_object</span>.

### Parameters

`parameter`  

### Return Values

### See Also

-   <a href="/ref/hwapi.html#hw_api::lock" class="xref"></a>

**Table of Contents**

-   [hw\_api::checkin](/ref/hwapi.html#hw_api::checkin) — Checks in an
    object
-   [hw\_api::checkout](/ref/hwapi.html#hw_api::checkout) — Checks out
    an object
-   [hw\_api::children](/ref/hwapi.html#hw_api::children) — Returns
    children of an object
-   [hw\_api::content](/ref/hwapi.html#hw_api::content) — Returns
    content of an object
-   [hw\_api::copy](/ref/hwapi.html#hw_api::copy) — Copies physically
-   [hw\_api::dbstat](/ref/hwapi.html#hw_api::dbstat) — Returns
    statistics about database server
-   [hw\_api::dcstat](/ref/hwapi.html#hw_api::dcstat) — Returns
    statistics about document cache server
-   [hw\_api::dstanchors](/ref/hwapi.html#hw_api::dstanchors) — Returns
    a list of all destination anchors
-   [hw\_api::dstofsrcanchor](/ref/hwapi.html#hw_api::dstofsrcanchor) —
    Returns destination of a source anchor
-   [hw\_api::find](/ref/hwapi.html#hw_api::find) — Search for objects
-   [hw\_api::ftstat](/ref/hwapi.html#hw_api::ftstat) — Returns
    statistics about fulltext server
-   [hw\_api::hwstat](/ref/hwapi.html#hw_api::hwstat) — Returns
    statistics about Hyperwave server
-   [hw\_api::identify](/ref/hwapi.html#hw_api::identify) — Log into
    Hyperwave Server
-   [hw\_api::info](/ref/hwapi.html#hw_api::info) — Returns information
    about server configuration
-   [hw\_api::insert](/ref/hwapi.html#hw_api::insert) — Inserts a new
    object
-   [hw\_api::insertanchor](/ref/hwapi.html#hw_api::insertanchor) —
    Inserts a new object of type anchor
-   [hw\_api::insertcollection](/ref/hwapi.html#hw_api::insertcollection)
    — Inserts a new object of type collection
-   [hw\_api::insertdocument](/ref/hwapi.html#hw_api::insertdocument) —
    Inserts a new object of type document
-   [hw\_api::link](/ref/hwapi.html#hw_api::link) — Creates a link to an
    object
-   [hw\_api::lock](/ref/hwapi.html#hw_api::lock) — Locks an object
-   [hw\_api::move](/ref/hwapi.html#hw_api::move) — Moves object between
    collections
-   [hw\_api::object](/ref/hwapi.html#hw_api::object) — Retrieve
    attribute information
-   [hw\_api::objectbyanchor](/ref/hwapi.html#hw_api::objectbyanchor) —
    Returns the object an anchor belongs to
-   [hw\_api::parents](/ref/hwapi.html#hw_api::parents) — Returns
    parents of an object
-   [hw\_api::remove](/ref/hwapi.html#hw_api::remove) — Delete an object
-   [hw\_api::replace](/ref/hwapi.html#hw_api::replace) — Replaces an
    object
-   [hw\_api::setcommittedversion](/ref/hwapi.html#hw_api::setcommittedversion)
    — Commits version other than last version
-   [hw\_api::srcanchors](/ref/hwapi.html#hw_api::srcanchors) — Returns
    a list of all source anchors
-   [hw\_api::srcsofdst](/ref/hwapi.html#hw_api::srcsofdst) — Returns
    source of a destination object
-   [hw\_api::unlock](/ref/hwapi.html#hw_api::unlock) — Unlocks a locked
    object
-   [hw\_api::user](/ref/hwapi.html#hw_api::user) — Returns the own user
    object
-   [hw\_api::userlist](/ref/hwapi.html#hw_api::userlist) — Returns a
    list of all logged in users
-   [hw\_api\_attribute::key](/ref/hwapi.html#hw_api_attribute::key) —
    Returns key of the attribute
-   [hw\_api\_attribute::langdepvalue](/ref/hwapi.html#hw_api_attribute::langdepvalue)
    — Returns value for a given language
-   [hw\_api\_attribute::value](/ref/hwapi.html#hw_api_attribute::value)
    — Returns value of the attribute
-   [hw\_api\_attribute::values](/ref/hwapi.html#hw_api_attribute::values)
    — Returns all values of the attribute
-   [hw\_api\_content::mimetype](/ref/hwapi.html#hw_api_content::mimetype)
    — Returns mimetype
-   [hw\_api\_content::read](/ref/hwapi.html#hw_api_content::read) —
    Read content
-   [hw\_api\_error::count](/ref/hwapi.html#hw_api_error::count) —
    Returns number of reasons
-   [hw\_api\_error::reason](/ref/hwapi.html#hw_api_error::reason) —
    Returns reason of error
-   [hw\_api\_object::assign](/ref/hwapi.html#hw_api_object::assign) —
    Clones object
-   [hw\_api\_object::attreditable](/ref/hwapi.html#hw_api_object::attreditable)
    — Checks whether an attribute is editable
-   [hw\_api\_object::count](/ref/hwapi.html#hw_api_object::count) —
    Returns number of attributes
-   [hw\_api\_object::insert](/ref/hwapi.html#hw_api_object::insert) —
    Inserts new attribute
-   [hw\_api\_object::remove](/ref/hwapi.html#hw_api_object::remove) —
    Removes attribute
-   [hw\_api\_object::title](/ref/hwapi.html#hw_api_object::title) —
    Returns the title attribute
-   [hw\_api\_object::value](/ref/hwapi.html#hw_api_object::value) —
    Returns value of attribute
-   [hw\_api\_reason::description](/ref/hwapi.html#hw_api_reason::description)
    — Returns description of reason
-   [hw\_api\_reason::type](/ref/hwapi.html#hw_api_reason::type) —
    Returns type of reason
-   [hwapi\_attribute\_new](/ref/hwapi.html#hwapi_attribute_new) —
    Creates instance of class hw\_api\_attribute
-   [hwapi\_content\_new](/ref/hwapi.html#hwapi_content_new) — Create
    new instance of class hw\_api\_content
-   [hwapi\_hgcsp](/ref/hwapi.html#hwapi_hgcsp) — Returns object of
    class hw\_api
-   [hwapi\_object\_new](/ref/hwapi.html#hwapi_object_new) — Creates a
    new instance of class hwapi\_object\_new
