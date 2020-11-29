snmp\_get\_quick\_print
=======================

Fetches the current value of the UCD library's quick\_print setting

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_get\_quick\_print</span> ( <span
class="methodparam">void</span> )

Returns the current value stored in the UCD Library for quick\_print.
quick\_print is off by default.

### Return Values

Returns **`TRUE`** if quick\_print is on, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">snmp\_get\_quick\_print</span>
example**

``` php
<?php
$quickprint = snmp_get_quick_print();
?>
```

### See Also

-   <span class="function">snmp\_set\_quick\_print</span> for a full
    description of what quick\_print does.

snmp\_get\_valueretrieval
=========================

Return the method how the SNMP values will be returned

### Description

<span class="type">int</span> <span
class="methodname">snmp\_get\_valueretrieval</span> ( <span
class="methodparam">void</span> )

### Return Values

OR-ed combitantion of constants ( **`SNMP_VALUE_LIBRARY`** or
**`SNMP_VALUE_PLAIN`** ) with possible SNMP\_VALUE\_OBJECT set.

### Examples

**Example \#1 Using snmp\_get\_valueretrieval**

``` php
<?php
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 if (snmp_get_valueretrieval() & SNMP_VALUE_OBJECT) {
   echo $ret->value;
 } else {
   echo $ret;
 }
?>
```

### See Also

-   <span class="function">snmp\_set\_valueretrieval</span>
-   <a href="/snmp/constants.html" class="xref">Predefined Constants</a>

snmp\_read\_mib
===============

Reads and parses a MIB file into the active MIB tree

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_read\_mib</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

This function is used to load additional, e.g. vendor specific, MIBs so
that human readable OIDs like VENDOR-MIB::foo.1 instead of error prone
numeric OIDs can be used.

The order in which the MIBs are loaded does matter as the underlying
Net-SNMP libary will print warnings if referenced objects cannot be
resolved.

### Parameters

`filename`  
The filename of the MIB.

### Examples

**Example \#1 Using <span class="function">snmp\_read\_mib</span>**

``` php
<?php
 print_r( snmprealwalk('localhost', 'public', '.1.3.6.1.2.1.2.3.4.5') );
 
 snmp_read_mib('./FOO-BAR-MIB.txt');
 print_r( snmprealwalk('localhost', 'public', 'FOO-BAR-MIB::someTable' );
?>
```

The above example is made up but the results would look like:

         
    Array
    (
        [iso.3.6.1.2.1.2.3.4.5.0] => Gauge32: 6
    )
    Array
    (
        [FOO-BAR-MIB::someTable.0] => Gauge32: 6
    )

snmp\_set\_enum\_print
======================

Return all values that are enums with their enum value instead of the
raw integer

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_set\_enum\_print</span> ( <span
class="methodparam"><span class="type">int</span> `$enum_print`</span> )

This function toggles if snmpwalk/snmpget etc. should automatically
lookup enum values in the MIB and return them together with their human
readable string.

### Parameters

`enum_print`  
As the value is interpreted as boolean by the Net-SNMP library, it can
only be "0" or "1".

### Examples

**Example \#1 Using <span
class="function">snmp\_set\_enum\_print</span>**

``` php
<?php
 snmp_set_enum_print(0);
 echo snmpget('localhost', 'public', 'IF-MIB::ifOperStatus.3') . "\n";
 snmp_set_enum_print(1);
 echo snmpget('localhost', 'public', 'IF-MIB::ifOperStatus.3') . "\n";
?>
```

The above would return

          
     INTEGER: up(1)
     INTEGER: 1

### Notes

> **Note**:
>
> <span class="function">snmp\_set\_enum\_print</span> is only available
> when using the UCD SNMP library. This function is not available when
> using the Windows SNMP library.

snmp\_set\_oid\_numeric\_print
==============================

Set the OID output format

### Description

<span class="type">void</span> <span
class="methodname">snmp\_set\_oid\_numeric\_print</span> ( <span
class="methodparam"><span class="type">int</span> `$oid_format`</span> )

This function is an alias of: <span
class="function">snmp\_set\_oid\_output\_format</span>.

### See Also

-   <span class="function">snmp\_set\_oid\_output\_format</span>

snmp\_set\_oid\_output\_format
==============================

Set the OID output format

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_set\_oid\_output\_format</span> ( <span
class="methodparam"><span class="type">int</span> `$oid_format`<span
class="initializer"> = SNMP\_OID\_OUTPUT\_MODULE</span></span> )

<span class="function">snmp\_set\_oid\_output\_format</span> sets the
output format to be full or numeric.

### Parameters

`oid_format`  
|                               |                                                                     |
|-------------------------------|---------------------------------------------------------------------|
| **`SNMP_OID_OUTPUT_FULL`**    | .iso.org.dod.internet.mgmt.mib-2.system.sysUpTime.sysUpTimeInstance |
| **`SNMP_OID_OUTPUT_NUMERIC`** | .1.3.6.1.2.1.1.3.0                                                  |

Begining from PHP 5.4.0 four additional constants available:

|                              |                                     |
|------------------------------|-------------------------------------|
| **`SNMP_OID_OUTPUT_MODULE`** | DISMAN-EVENT-MIB::sysUpTimeInstance |
| **`SNMP_OID_OUTPUT_SUFFIX`** | sysUpTimeInstance                   |
| **`SNMP_OID_OUTPUT_UCD`**    | system.sysUpTime.sysUpTimeInstance  |
| **`SNMP_OID_OUTPUT_NONE`**   | Undefined                           |

### Return Values

No value is returned.

### Notes

> **Note**:
>
> <span class="function">snmp\_set\_oid\_output\_format</span> is only
> available when using the UCD SNMP library. This function is not
> available when using the Windows SNMP library.

### Examples

**Example \#1 Using <span class="function">snmprealwalk</span>**

``` php
<?php

 snmp_read_mib("/usr/share/mibs/netsnmp/NET-SNMP-TC");

 // default or SNMP_OID_OUTPUT_MODULE in PHP >= 5.3.6
 print_r( snmprealwalk('localhost', 'public', 'RFC1213-MIB::sysObjectID') );

 snmp_set_oid_output_format(SNMP_OID_OUTPUT_NUMERIC);
 print_r( snmprealwalk('localhost', 'public', 'RFC1213-MIB::sysObjectID') );

 snmp_set_oid_output_format(SNMP_OID_OUTPUT_FULL);
 print_r( snmprealwalk('localhost', 'public', 'RFC1213-MIB::sysObjectID') );
?>
```

The above would output:

     Array
     (
        [RFC1213-MIB::sysObjectID.0] => OID: NET-SNMP-TC::linux
     )
     Array
     (
        [.1.3.6.1.2.1.1.2.0] => OID: .1.3.6.1.4.1.8072.3.2.10
     )
     Array
     (
        [.iso.org.dod.internet.mgmt.mib-2.system.sysObjectID.0] => OID: .iso.org.dod.internet.private.enterprises.netSnmp.netSnmpEnumerations.netSnmpAgentOIDs.linux
     )

snmp\_set\_quick\_print
=======================

Set the value of `quick_print` within the UCD SNMP library

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_set\_quick\_print</span> ( <span
class="methodparam"><span class="type">bool</span> `$quick_print`</span>
)

Sets the value of `quick_print` within the UCD SNMP library. When this
is set (1), the SNMP library will return 'quick printed' values. This
means that just the value will be printed. When `quick_print` is not
enabled (default) the UCD SNMP library prints extra information
including the type of the value (i.e. IpAddress or OID). Additionally,
if quick\_print is not enabled, the library prints additional hex values
for all strings of three characters or less.

By default the UCD SNMP library returns verbose values, quick\_print is
used to return only the value.

Currently strings are still returned with extra quotes, this will be
corrected in a later release.

### Parameters

`quick_print`  

### Return Values

No value is returned.

### Examples

Setting quick\_print is often used when using the information returned
rather than displaying it.

**Example \#1 Using <span
class="function">snmp\_set\_quick\_print</span>**

``` php
<?php
snmp_set_quick_print(0);
$a = snmpget("127.0.0.1", "public", ".1.3.6.1.2.1.2.2.1.9.1");
echo "$a\n";
snmp_set_quick_print(1);
$a = snmpget("127.0.0.1", "public", ".1.3.6.1.2.1.2.2.1.9.1");
echo "$a\n";
?>
```

The above example will output something similar to:

    'Timeticks: (0) 0:00:00.00'
    '0:00:00.00'

### See Also

-   <span class="function">snmp\_get\_quick\_print</span>

snmp\_set\_valueretrieval
=========================

Specify the method how the SNMP values will be returned

### Description

<span class="type">bool</span> <span
class="methodname">snmp\_set\_valueretrieval</span> ( <span
class="methodparam"> <span class="type">int</span> `$method` <span
class="initializer"> = SNMP\_VALUE\_LIBRARY</span> </span> )

### Parameters

`method`  
|                      |                                                                                                                                                                                                                                                                                  |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SNMP\_VALUE\_LIBRARY | The return values will be as returned by the Net-SNMP library.                                                                                                                                                                                                                   |
| SNMP\_VALUE\_PLAIN   | The return values will be the plain value without the SNMP type hint.                                                                                                                                                                                                            |
| SNMP\_VALUE\_OBJECT  | The return values will be objects with the properties "value" and "type", where the latter is one of the SNMP\_OCTET\_STR, SNMP\_COUNTER etc. constants. The way "value" is returned is based on which one of constants **`SNMP_VALUE_LIBRARY`**, **`SNMP_VALUE_PLAIN`** is set. |

### Examples

**Example \#1 Using <span
class="function">snmp\_set\_valueretrieval</span>**

``` php
<?php
 snmp_set_valueretrieval(SNMP_VALUE_LIBRARY);
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 // $ret = "STRING: lo"

 snmp_set_valueretrieval(SNMP_VALUE_PLAIN);
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 // $ret = "lo";

 snmp_set_valueretrieval(SNMP_VALUE_OBJECT);
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 // stdClass Object
 // (
 //   [type] => 4        <-- SNMP_OCTET_STR, see constants
 //   [value] => lo
 // )

 // PHP 5.4+ examples
 snmp_set_valueretrieval(SNMP_VALUE_OBJECT | SNMP_VALUE_PLAIN);
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 // stdClass Object
 // (
 //   [type] => 4        <-- SNMP_OCTET_STR, see constants
 //   [value] => lo
 // )

 snmp_set_valueretrieval(SNMP_VALUE_OBJECT | SNMP_VALUE_LIBRARY);
 $ret = snmpget('localhost', 'public', 'IF-MIB::ifName.1');
 // stdClass Object
 // (
 //   [type] => 4        <-- SNMP_OCTET_STR, see constants
 //   [value] => STRING: lo
 // )

?>
```

### See Also

-   <span class="function">snmp\_get\_valueretrieval</span>
-   <a href="/snmp/constants.html" class="xref">Predefined Constants</a>

snmp2\_get
==========

Fetch an SNMP object

### Description

<span class="type">string</span> <span
class="methodname">snmp2\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

The <span class="function">snmp2\_get</span> function is used to read
the value of an SNMP object specified by the `object_id`.

### Parameters

`host`  
The SNMP agent.

`community`  
The read community.

`object_id`  
The SNMP object.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error.

### Examples

**Example \#1 Using <span class="function">snmp2\_get</span>**

``` php
<?php
$syscontact = snmp2_get("127.0.0.1", "public", "system.SysContact.0");
?>
```

### See Also

-   <span class="function">snmp2\_set</span>

snmp2\_getnext
==============

Fetch the SNMP object which follows the given object id

### Description

<span class="type">string</span> <span
class="methodname">snmp2\_getnext</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$community`</span> , <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The <span class="function">snmp2\_get\_next</span> function is used to
read the value of the SNMP object that follows the specified
`object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The read community.

`object_id`  
The SNMP object id which precedes the wanted one.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error. In case of
an error, an E\_WARNING message is shown.

### Examples

**Example \#1 Using <span class="function">snmp2\_get\_next</span>**

``` php
<?php
$nameOfSecondInterface = snmp2_get_next('localhost', 'public', 'IF-MIB::ifName.1';
?>
```

### See Also

-   <span class="function">snmp2\_get</span>
-   <span class="function">snmp2\_walk</span>

snmp2\_real\_walk
=================

Return all objects including their respective object ID within the
specified one

### Description

<span class="type">array</span> <span
class="methodname">snmp2\_real\_walk</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$community`</span> , <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The <span class="function">snmp2\_real\_walk</span> function is used to
traverse over a number of SNMP objects starting from `object_id` and
return not only their values but also their object ids.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The read community.

`object_id`  
The SNMP object id which precedes the wanted one.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an associative array of the SNMP object ids and their values on
success or **`FALSE`** on error. In case of an error, an E\_WARNING
message is shown.

### Examples

**Example \#1 Using <span class="function">snmp2\_real\_walk</span>**

``` php
<?php
 print_r(snmp2_real_walk("localhost", "public", "IF-MIB::ifName"));
?>
```

The above will output something like:

        Array
          (
          [IF-MIB::ifName.1] => STRING: lo
          [IF-MIB::ifName.2] => STRING: eth0
          [IF-MIB::ifName.3] => STRING: eth2
          [IF-MIB::ifName.4] => STRING: sit0
          [IF-MIB::ifName.5] => STRING: sixxs
        )

### See Also

-   <span class="function">snmp2\_walk</span>

snmp2\_set
==========

Set the value of an SNMP object

### Description

<span class="type">bool</span> <span
class="methodname">snmp2\_set</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> , <span class="methodparam"><span
class="type">string</span> `$type`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

<span class="function">snmp2\_set</span> is used to set the value of an
SNMP object specified by the `object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The write community.

`object_id`  
The SNMP object id.

`type`  
The MIB defines the type of each object id. It has to be specified as a
single character from the below list.

|     |                                |
|-----|--------------------------------|
| =   | The type is taken from the MIB |
| i   | INTEGER                        |
| u   | INTEGER                        |
| s   | STRING                         |
| x   | HEX STRING                     |
| d   | DECIMAL STRING                 |
| n   | NULLOBJ                        |
| o   | OBJID                          |
| t   | TIMETICKS                      |
| a   | IPADDRESS                      |
| b   | BITS                           |

If **`OPAQUE_SPECIAL_TYPES`** was defined while compiling the SNMP
library, the following are also valid:

|     |                |
|-----|----------------|
| U   | unsigned int64 |
| I   | signed int64   |
| F   | float          |
| D   | double         |

Most of these will use the obvious corresponding ASN.1 type. 's', 'x',
'd' and 'b' are all different ways of specifying an OCTET STRING value,
and the 'u' unsigned type is also used for handling Gauge32 values.

If the MIB-Files are loaded by into the MIB Tree with "snmp\_read\_mib"
or by specifying it in the libsnmp config, '=' may be used as the `type`
parameter for all object ids as the type can then be automatically read
from the MIB.

Note that there are two ways to set a variable of the type BITS like
e.g. "SYNTAX BITS {telnet(0), ftp(1), http(2), icmp(3), snmp(4), ssh(5),
https(6)}":

-   <span class="simpara"> Using type "b" and a list of bit numbers.
    This method is not recommended since GET query for the same OID
    would return e.g. 0xF8. </span>
-   <span class="simpara"> Using type "x" and a hex number but
    without(!) the usual "0x" prefix. </span>

See examples section for more details.

`value`  
The new value.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

If the SNMP host rejects the data type, an E\_WARNING message like
"Warning: Error in packet. Reason: (badValue) The value given has the
wrong type or length." is shown. If an unknown or invalid OID is
specified the warning probably reads "Could not add variable".

### Examples

**Example \#1 Using <span class="function">snmp2\_set</span>**

``` php
<?php
  snmp2_set("localhost", "public", "IF-MIB::ifAlias.3", "s", "foo");
?>
```

**Example \#2 Using <span class="function">snmp2\_set</span> for setting
BITS SNMP object id**

``` php
<?php
  snmp2_set("localhost", "public", 'FOO-MIB::bar.42', 'b', '0 1 2 3 4');
// or
  snmp2_set("localhost", "public", 'FOO-MIB::bar.42', 'x', 'F0');
?>
```

### See Also

-   <span class="function">snmp2\_get</span>

snmp2\_walk
===========

Fetch all the SNMP objects from an agent

### Description

<span class="type">array</span> <span
class="methodname">snmp2\_walk</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

<span class="function">snmp2\_walk</span> function is used to read all
the values from an SNMP agent specified by the `hostname`.

### Parameters

`host`  
The SNMP agent (server).

`community`  
The read community.

`object_id`  
If **`NULL`**, `object_id` is taken as the root of the SNMP objects tree
and all objects under that tree are returned as an array.

If `object_id` is specified, all the SNMP objects below that `object_id`
are returned.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an array of SNMP object values starting from the `object_id` as
root or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">snmp2\_walk</span> Example**

``` php
<?php
$a = snmp2_walk("127.0.0.1", "public", "");

foreach ($a as $val) {
    echo "$val\n";
}

?>
```

Above function call would return all the SNMP objects from the SNMP
agent running on localhost. One can step through the values with a loop

### See Also

-   <span class="function">snmp2\_real\_walk</span>

snmp3\_get
==========

Fetch an SNMP object

### Description

<span class="type">string</span> <span
class="methodname">snmp3\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$sec_name`</span>
, <span class="methodparam"><span class="type">string</span>
`$sec_level`</span> , <span class="methodparam"><span
class="type">string</span> `$auth_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$auth_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$priv_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$priv_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The <span class="function">snmp3\_get</span> function is used to read
the value of an SNMP object specified by the `object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`sec_name`  
the security name, usually some kind of username

`sec_level`  
the security level (noAuthNoPriv\|authNoPriv\|authPriv)

`auth_protocol`  
the authentication protocol (MD5 or SHA)

`auth_passphrase`  
the authentication pass phrase

`priv_protocol`  
the privacy protocol (DES or AES)

`priv_passphrase`  
the privacy pass phrase

`object_id`  
The SNMP object id.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error.

### Examples

**Example \#1 Using <span class="function">snmp3\_get</span>**

``` php
<?php
$nameOfSecondInterface = snmp3_get('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'IF-MIB::ifName.2');
?>
```

### See Also

-   <span class="function">snmp3\_set</span>

snmp3\_getnext
==============

Fetch the SNMP object which follows the given object id

### Description

<span class="type">string</span> <span
class="methodname">snmp3\_getnext</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$sec_name`</span> , <span class="methodparam"><span
class="type">string</span> `$sec_level`</span> , <span
class="methodparam"><span class="type">string</span>
`$auth_protocol`</span> , <span class="methodparam"><span
class="type">string</span> `$auth_passphrase`</span> , <span
class="methodparam"><span class="type">string</span>
`$priv_protocol`</span> , <span class="methodparam"><span
class="type">string</span> `$priv_passphrase`</span> , <span
class="methodparam"><span class="type">string</span> `$object_id`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`<span class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The <span class="function">snmp3\_getnext</span> function is used to
read the value of the SNMP object that follows the specified
`object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`sec_name`  
the security name, usually some kind of username

`sec_level`  
the security level (noAuthNoPriv\|authNoPriv\|authPriv)

`auth_protocol`  
the authentication protocol (MD5 or SHA)

`auth_passphrase`  
the authentication pass phrase

`priv_protocol`  
the privacy protocol (DES or AES)

`priv_passphrase`  
the privacy pass phrase

`object_id`  
The SNMP object id.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error. In case of
an error, an E\_WARNING message is shown.

### Examples

**Example \#1 Using <span class="function">snmp3\_getnext</span>**

``` php
<?php
$nameOfSecondInterface = snmp3_getnext('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'IF-MIB::ifName.1');
?>
```

### See Also

-   <span class="function">snmp3\_get</span>
-   <span class="function">snmp3\_walk</span>

snmp3\_real\_walk
=================

Return all objects including their respective object ID within the
specified one

### Description

<span class="type">array</span> <span
class="methodname">snmp3\_real\_walk</span> ( <span class="methodparam">
<span class="type">string</span> `$host` </span> , <span
class="methodparam"> <span class="type">string</span> `$sec_name`
</span> , <span class="methodparam"> <span class="type">string</span>
`$sec_level` </span> , <span class="methodparam"> <span
class="type">string</span> `$auth_protocol` </span> , <span
class="methodparam"> <span class="type">string</span> `$auth_passphrase`
</span> , <span class="methodparam"> <span class="type">string</span>
`$priv_protocol` </span> , <span class="methodparam"> <span
class="type">string</span> `$priv_passphrase` </span> , <span
class="methodparam"> <span class="type">string</span> `$object_id`
</span> \[, <span class="methodparam"> <span class="type">int</span>
`$timeout` <span class="initializer"> = 1000000</span> </span> \[, <span
class="methodparam"> <span class="type">int</span> `$retries` <span
class="initializer"> = 5</span> </span> \]\] )

The <span class="function">snmp3\_real\_walk</span> function is used to
traverse over a number of SNMP objects starting from `object_id` and
return not only their values but also their object ids.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`sec_name`  
the security name, usually some kind of username

`sec_level`  
the security level (noAuthNoPriv\|authNoPriv\|authPriv)

`auth_protocol`  
the authentication protocol (MD5 or SHA)

`auth_passphrase`  
the authentication pass phrase

`priv_protocol`  
the privacy protocol (DES or AES)

`priv_passphrase`  
the privacy pass phrase

`object_id`  
The SNMP object id.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an associative array of the SNMP object ids and their values on
success or **`FALSE`** on error. In case of an error, an E\_WARNING
message is shown.

### Examples

**Example \#1 Using <span class="function">snmp3\_real\_walk</span>**

``` php
<?php
 var_export(snmp3_real_walk('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'IF-MIB::ifName'));
?>
```

The above will output something like:

    array (
      'IF-MIB::ifName.1' => 'STRING: lo',
      'IF-MIB::ifName.2' => 'STRING: eth0',
      'IF-MIB::ifName.3' => 'STRING: eth2',
      'IF-MIB::ifName.4' => 'STRING: sit0',
      'IF-MIB::ifName.5' => 'STRING: sixxs',
    )

### See Also

-   <span class="function">snmpwalk</span>

snmp3\_set
==========

Set the value of an SNMP object

### Description

<span class="type">bool</span> <span
class="methodname">snmp3\_set</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$sec_name`</span>
, <span class="methodparam"><span class="type">string</span>
`$sec_level`</span> , <span class="methodparam"><span
class="type">string</span> `$auth_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$auth_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$priv_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$priv_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$object_id`</span> , <span
class="methodparam"><span class="type">string</span> `$type`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

<span class="function">snmp3\_set</span> is used to set the value of an
SNMP object specified by the `object_id`.

Even if the security level does not use an auth or priv
protocol/password valid values have to be specified.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`sec_name`  
the security name, usually some kind of username

`sec_level`  
the security level (noAuthNoPriv\|authNoPriv\|authPriv)

`auth_protocol`  
the authentication protocol (MD5 or SHA)

`auth_passphrase`  
the authentication pass phrase

`priv_protocol`  
the privacy protocol (DES or AES)

`priv_passphrase`  
the privacy pass phrase

`object_id`  
The SNMP object id.

`type`  
The MIB defines the type of each object id. It has to be specified as a
single character from the below list.

|     |                                |
|-----|--------------------------------|
| =   | The type is taken from the MIB |
| i   | INTEGER                        |
| u   | INTEGER                        |
| s   | STRING                         |
| x   | HEX STRING                     |
| d   | DECIMAL STRING                 |
| n   | NULLOBJ                        |
| o   | OBJID                          |
| t   | TIMETICKS                      |
| a   | IPADDRESS                      |
| b   | BITS                           |

If **`OPAQUE_SPECIAL_TYPES`** was defined while compiling the SNMP
library, the following are also valid:

|     |                |
|-----|----------------|
| U   | unsigned int64 |
| I   | signed int64   |
| F   | float          |
| D   | double         |

Most of these will use the obvious corresponding ASN.1 type. 's', 'x',
'd' and 'b' are all different ways of specifying an OCTET STRING value,
and the 'u' unsigned type is also used for handling Gauge32 values.

If the MIB-Files are loaded by into the MIB Tree with "snmp\_read\_mib"
or by specifying it in the libsnmp config, '=' may be used as the `type`
parameter for all object ids as the type can then be automatically read
from the MIB.

Note that there are two ways to set a variable of the type BITS like
e.g. "SYNTAX BITS {telnet(0), ftp(1), http(2), icmp(3), snmp(4), ssh(5),
https(6)}":

-   <span class="simpara"> Using type "b" and a list of bit numbers.
    This method is not recommended since GET query for the same OID
    would return e.g. 0xF8. </span>
-   <span class="simpara"> Using type "x" and a hex number but
    without(!) the usual "0x" prefix. </span>

See examples section for more details.

`value`  
The new value

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

If the SNMP host rejects the data type, an E\_WARNING message like
"Warning: Error in packet. Reason: (badValue) The value given has the
wrong type or length." is shown. If an unknown or invalid OID is
specified the warning probably reads "Could not add variable".

### Examples

**Example \#1 Using <span class="function">snmp3\_set</span>**

``` php
<?php
  snmp3_set('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'IF-MIB::ifAlias.3', 's', "foo");
?>
```

**Example \#2 Using <span class="function">snmp3\_set</span> for setting
BITS SNMP object id**

``` php
<?php
  snmp3_set('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'FOO-MIB::bar.42', 'b', '0 1 2 3 4');
// or
  snmp3_set('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'FOO-MIB::bar.42', 'x', 'F0');
?>
```

snmp3\_walk
===========

Fetch all the SNMP objects from an agent

### Description

<span class="type">array</span> <span
class="methodname">snmp3\_walk</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$sec_name`</span>
, <span class="methodparam"><span class="type">string</span>
`$sec_level`</span> , <span class="methodparam"><span
class="type">string</span> `$auth_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$auth_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$priv_protocol`</span> , <span
class="methodparam"><span class="type">string</span>
`$priv_passphrase`</span> , <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

<span class="function">snmp3\_walk</span> function is used to read all
the values from an SNMP agent specified by the `hostname`.

Even if the security level does not use an auth or priv
protocol/password valid values have to be specified.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`sec_name`  
the security name, usually some kind of username

`sec_level`  
the security level (noAuthNoPriv\|authNoPriv\|authPriv)

`auth_protocol`  
the authentication protocol (MD5 or SHA)

`auth_passphrase`  
the authentication pass phrase

`priv_protocol`  
the privacy protocol (DES or AES)

`priv_passphrase`  
the privacy pass phrase

`object_id`  
If **`NULL`**, `object_id` is taken as the root of the SNMP objects tree
and all objects under that tree are returned as an array.

If `object_id` is specified, all the SNMP objects below that `object_id`
are returned.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an array of SNMP object values starting from the `object_id` as
root or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">snmp3\_walk</span> Example**

``` php
<?php
$ret = snmp3_walk('localhost', 'james', 'authPriv', 'SHA', 'secret007', 'AES', 'secret007', 'IF-MIB::ifName');
var_export($ret);
?>
```

Above function call would return all the SNMP objects from the SNMP
agent running on localhost:

          
    array (
      0 => 'STRING: lo',
      1 => 'STRING: eth0',
      2 => 'STRING: eth2',
      3 => 'STRING: sit0',
      4 => 'STRING: sixxs',
    )

### See Also

-   <span class="function">snmp3\_real\_walk</span>

snmpget
=======

Fetch an SNMP object

### Description

<span class="type">string</span> <span class="methodname">snmpget</span>
( <span class="methodparam"><span class="type">string</span>
`$hostname`</span> , <span class="methodparam"><span
class="type">string</span> `$community`</span> , <span
class="methodparam"><span class="type">string</span> `$object_id`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`<span class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The <span class="function">snmpget</span> function is used to read the
value of an SNMP object specified by the `object_id`.

### Parameters

`hostname`  
The SNMP agent.

`community`  
The read community.

`object_id`  
The SNMP object.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error.

### Examples

**Example \#1 Using <span class="function">snmpget</span>**

``` php
<?php
$syscontact = snmpget("127.0.0.1", "public", "system.SysContact.0");
?>
```

### See Also

-   <span class="function">snmpset</span>

snmpgetnext
===========

Fetch the SNMP object which follows the given object id

### Description

<span class="type">string</span> <span
class="methodname">snmpgetnext</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

The <span class="function">snmpgetnext</span> function is used to read
the value of the SNMP object that follows the specified `object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The read community.

`object_id`  
The SNMP object id which precedes the wanted one.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns SNMP object value on success or **`FALSE`** on error. In case of
an error, an E\_WARNING message is shown.

### Examples

**Example \#1 Using <span class="function">snmpgetnext</span>**

``` php
<?php
$nameOfSecondInterface = snmpgetnetxt('localhost', 'public', 'IF-MIB::ifName.1';
?>
```

### See Also

-   <span class="function">snmpget</span>
-   <span class="function">snmpwalk</span>

snmprealwalk
============

Return all objects including their respective object ID within the
specified one

### Description

<span class="type">array</span> <span
class="methodname">snmprealwalk</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

The <span class="function">snmprealwalk</span> function is used to
traverse over a number of SNMP objects starting from `object_id` and
return not only their values but also their object ids.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The read community.

`object_id`  
The SNMP object id which precedes the wanted one.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an associative array of the SNMP object ids and their values on
success or **`FALSE`** on error. In case of an error, an E\_WARNING
message is shown.

### Examples

**Example \#1 Using <span class="function">snmprealwalk</span>**

``` php
<?php
 print_r(snmprealwalk("localhost", "public", "IF-MIB::ifName"));
?>
```

The above will output something like:

         
        Array
          (
          [IF-MIB::ifName.1] => STRING: lo
          [IF-MIB::ifName.2] => STRING: eth0
          [IF-MIB::ifName.3] => STRING: eth2
          [IF-MIB::ifName.4] => STRING: sit0
          [IF-MIB::ifName.5] => STRING: sixxs
        )

### See Also

-   <span class="function">snmpwalk</span>

snmpset
=======

Set the value of an SNMP object

### Description

<span class="type">bool</span> <span class="methodname">snmpset</span> (
<span class="methodparam"><span class="type">string</span>
`$host`</span> , <span class="methodparam"><span
class="type">string</span> `$community`</span> , <span
class="methodparam"><span class="type">string</span> `$object_id`</span>
, <span class="methodparam"><span class="type">string</span>
`$type`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

<span class="function">snmpset</span> is used to set the value of an
SNMP object specified by the `object_id`.

### Parameters

`host`  
The hostname of the SNMP agent (server).

`community`  
The write community.

`object_id`  
The SNMP object id.

`type`  
The MIB defines the type of each object id. It has to be specified as a
single character from the below list.

|     |                                |
|-----|--------------------------------|
| =   | The type is taken from the MIB |
| i   | INTEGER                        |
| u   | INTEGER                        |
| s   | STRING                         |
| x   | HEX STRING                     |
| d   | DECIMAL STRING                 |
| n   | NULLOBJ                        |
| o   | OBJID                          |
| t   | TIMETICKS                      |
| a   | IPADDRESS                      |
| b   | BITS                           |

If **`OPAQUE_SPECIAL_TYPES`** was defined while compiling the SNMP
library, the following are also valid:

|     |                |
|-----|----------------|
| U   | unsigned int64 |
| I   | signed int64   |
| F   | float          |
| D   | double         |

Most of these will use the obvious corresponding ASN.1 type. 's', 'x',
'd' and 'b' are all different ways of specifying an OCTET STRING value,
and the 'u' unsigned type is also used for handling Gauge32 values.

If the MIB-Files are loaded by into the MIB Tree with "snmp\_read\_mib"
or by specifying it in the libsnmp config, '=' may be used as the `type`
parameter for all object ids as the type can then be automatically read
from the MIB.

Note that there are two ways to set a variable of the type BITS like
e.g. "SYNTAX BITS {telnet(0), ftp(1), http(2), icmp(3), snmp(4), ssh(5),
https(6)}":

-   <span class="simpara"> Using type "b" and a list of bit numbers.
    This method is not recommended since GET query for the same OID
    would return e.g. 0xF8. </span>
-   <span class="simpara"> Using type "x" and a hex number but
    without(!) the usual "0x" prefix. </span>

See examples section for more details.

`value`  
The new value.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

If the SNMP host rejects the data type, an E\_WARNING message like
"Warning: Error in packet. Reason: (badValue) The value given has the
wrong type or length." is shown. If an unknown or invalid OID is
specified the warning probably reads "Could not add variable".

### Examples

**Example \#1 Using <span class="function">snmpset</span>**

``` php
<?php
  snmpset("localhost", "public", "IF-MIB::ifAlias.3", "s", "foo");
?>
```

**Example \#2 Using <span class="function">snmpset</span> for setting
BITS SNMP object id**

``` php
<?php
  snmpset("localhost", "public", 'FOO-MIB::bar.42', 'b', '0 1 2 3 4');
// or
  snmpset("localhost", "public", 'FOO-MIB::bar.42', 'x', 'F0');
?>
```

### See Also

-   <span class="function">snmpget</span>

snmpwalk
========

Fetch all the SNMP objects from an agent

### Description

<span class="type">array</span> <span class="methodname">snmpwalk</span>
( <span class="methodparam"><span class="type">string</span>
`$hostname`</span> , <span class="methodparam"><span
class="type">string</span> `$community`</span> , <span
class="methodparam"><span class="type">string</span> `$object_id`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`<span class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

<span class="function">snmpwalk</span> function is used to read all the
values from an SNMP agent specified by the `hostname`.

### Parameters

`hostname`  
The SNMP agent (server).

`community`  
The read community.

`object_id`  
If **`NULL`**, `object_id` is taken as the root of the SNMP objects tree
and all objects under that tree are returned as an array.

If `object_id` is specified, all the SNMP objects below that `object_id`
are returned.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an array of SNMP object values starting from the `object_id` as
root or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">snmpwalk</span> Example**

``` php
<?php
$a = snmpwalk("127.0.0.1", "public", ""); 

foreach ($a as $val) {
    echo "$val\n";
}

?>
```

Above function call would return all the SNMP objects from the SNMP
agent running on localhost. One can step through the values with a loop

### See Also

-   <span class="function">snmprealwalk</span>

snmpwalkoid
===========

Query for a tree of information about a network entity

### Description

<span class="type">array</span> <span
class="methodname">snmpwalkoid</span> ( <span class="methodparam"><span
class="type">string</span> `$hostname`</span> , <span
class="methodparam"><span class="type">string</span> `$community`</span>
, <span class="methodparam"><span class="type">string</span>
`$object_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
1000000</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$retries`<span class="initializer"> =
5</span></span> \]\] )

<span class="function">snmpwalkoid</span> function is used to read all
object ids and their respective values from an SNMP agent specified by
`hostname`.

The existence of <span class="function">snmpwalkoid</span> and <span
class="function">snmpwalk</span> has historical reasons. Both functions
are provided for backward compatibility. Use <span
class="function">snmprealwalk</span> instead.

### Parameters

`hostname`  
The SNMP agent.

`community`  
The read community.

`object_id`  
If **`NULL`**, `object_id` is taken as the root of the SNMP objects tree
and all objects under that tree are returned as an array.

If `object_id` is specified, all the SNMP objects below that `object_id`
are returned.

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of times to retry if timeouts occur.

### Return Values

Returns an associative array with object ids and their respective object
value starting from the `object_id` as root or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">snmpwalkoid</span> Example**

``` php
<?php
$a = snmpwalkoid("127.0.0.1", "public", ""); 
for (reset($a); $i = key($a); next($a)) {
    echo "$i: $a[$i]<br />\n";
}
?>
```

Above function call would return all the SNMP objects from the SNMP
agent running on localhost. One can step through the values with a loop

### See Also

-   <span class="function">snmpwalk</span>

**Table of Contents**

-   [snmp\_get\_quick\_print](/ref/snmp.html#snmp_get_quick_print) —
    Fetches the current value of the UCD library's quick\_print setting
-   [snmp\_get\_valueretrieval](/ref/snmp.html#snmp_get_valueretrieval)
    — Return the method how the SNMP values will be returned
-   [snmp\_read\_mib](/ref/snmp.html#snmp_read_mib) — Reads and parses a
    MIB file into the active MIB tree
-   [snmp\_set\_enum\_print](/ref/snmp.html#snmp_set_enum_print) —
    Return all values that are enums with their enum value instead of
    the raw integer
-   [snmp\_set\_oid\_numeric\_print](/ref/snmp.html#snmp_set_oid_numeric_print)
    — Set the OID output format
-   [snmp\_set\_oid\_output\_format](/ref/snmp.html#snmp_set_oid_output_format)
    — Set the OID output format
-   [snmp\_set\_quick\_print](/ref/snmp.html#snmp_set_quick_print) — Set
    the value of quick\_print within the UCD SNMP library
-   [snmp\_set\_valueretrieval](/ref/snmp.html#snmp_set_valueretrieval)
    — Specify the method how the SNMP values will be returned
-   [snmp2\_get](/ref/snmp.html#snmp2_get) — Fetch an SNMP object
-   [snmp2\_getnext](/ref/snmp.html#snmp2_getnext) — Fetch the SNMP
    object which follows the given object id
-   [snmp2\_real\_walk](/ref/snmp.html#snmp2_real_walk) — Return all
    objects including their respective object ID within the specified
    one
-   [snmp2\_set](/ref/snmp.html#snmp2_set) — Set the value of an SNMP
    object
-   [snmp2\_walk](/ref/snmp.html#snmp2_walk) — Fetch all the SNMP
    objects from an agent
-   [snmp3\_get](/ref/snmp.html#snmp3_get) — Fetch an SNMP object
-   [snmp3\_getnext](/ref/snmp.html#snmp3_getnext) — Fetch the SNMP
    object which follows the given object id
-   [snmp3\_real\_walk](/ref/snmp.html#snmp3_real_walk) — Return all
    objects including their respective object ID within the specified
    one
-   [snmp3\_set](/ref/snmp.html#snmp3_set) — Set the value of an SNMP
    object
-   [snmp3\_walk](/ref/snmp.html#snmp3_walk) — Fetch all the SNMP
    objects from an agent
-   [snmpget](/ref/snmp.html#snmpget) — Fetch an SNMP object
-   [snmpgetnext](/ref/snmp.html#snmpgetnext) — Fetch the SNMP object
    which follows the given object id
-   [snmprealwalk](/ref/snmp.html#snmprealwalk) — Return all objects
    including their respective object ID within the specified one
-   [snmpset](/ref/snmp.html#snmpset) — Set the value of an SNMP object
-   [snmpwalk](/ref/snmp.html#snmpwalk) — Fetch all the SNMP objects
    from an agent
-   [snmpwalkoid](/ref/snmp.html#snmpwalkoid) — Query for a tree of
    information about a network entity
