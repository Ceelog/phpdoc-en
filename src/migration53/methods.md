New Methods
-----------

Several new methods were introduced in 5.3.0:

<a href="/book/datetime.html" class="link">Date/Time</a>:

-   <span class="simpara"> <span class="function">DateTime::add</span> -
    Adds an amount of days, months, years, hours, minutes and seconds to
    a <span class="classname">DateTime</span> object. </span>
-   <span class="simpara"> <span
    class="function">DateTime::createFromFormat</span> - Returns a new
    <span class="classname">DateTime</span> object formatted according
    to the given format. </span>
-   <span class="simpara"> <span
    class="function">DateTime::diff</span> - Returns the difference
    between two <span class="classname">DateTime</span> objects. </span>
-   <span class="simpara"> <span
    class="function">DateTime::getLastErrors</span> - Returns the
    warnings and errors from the last date/time operation. </span>
-   <span class="simpara"> <span class="function">DateTime::sub</span> -
    Subtracts an amount of days, months, years, hours, minutes and
    seconds from a <span class="classname">DateTime</span> object.
    </span>

<span class="classname">Exception</span>:

-   <span class="simpara"> <span
    class="function">Exception::getPrevious</span> - Retrieves the
    previous exception. </span>

<a href="/book/dom.html" class="link">DOM</a>:

-   <span class="simpara"> <span
    class="function">DOMNode::getLineNo</span> - Get the line number of
    a parsed node. </span>

<a href="/book/pdo.html#Firebird%20(PDO)" class="link">PDO_FIREBIRD</a>:

-   <span class="simpara"> <span
    class="function">PDO::setAttribute</span> - Sets an attribute.
    </span>

<a href="/book/reflection.html" class="link">Reflection</a>:

-   <span class="simpara"> <span
    class="methodname">ReflectionClass::getNamespaceName</span> -
    Returns the name of namespace where this class is defined. </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionClass::getShortName</span> - Returns
    the short name of this class (without namespace part). </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionClass::inNamespace</span> - Returns
    whether this class is defined in a namespace. </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionFunction::getNamespaceName</span> -
    Returns the name of namespace where this function is defined.
    </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionFunction::getShortName</span> - Returns
    the short name of the function (without namespace part). </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionFunction::inNamespace</span> - Returns
    whether this function is defined in a namespace. </span>
-   <span class="simpara"> <span
    class="methodname">ReflectionProperty::setAccessible</span> - Sets
    whether non-public properties can be requested. </span>

<a href="/book/spl.html" class="link">SPL</a>:

-   <span class="simpara"> <span
    class="function">SplObjectStorage::addAll</span> - Add all elements
    from another SplObjectStorage object. </span>
-   <span class="simpara"> <span
    class="function">SplObjectStorage::removeAll</span> - Remove all
    elements from another SplObjectStorage object. </span>

<a href="/book/xsl.html" class="link">XSL</a>:

-   <span class="simpara"> <span
    class="function">XSLTProcessor::setProfiling</span> - Sets the
    profiling output file. </span>
