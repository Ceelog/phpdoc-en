SNMP
====

**Table of Contents**

-   [Introduction](/intro/snmp.html)
-   [Installing/Configuring](/snmp/setup.html)
    -   [Requirements](/snmp/setup.html#Requirements)
    -   [Installation](/snmp/setup.html#Installation)
    -   [Runtime
        Configuration](/snmp/setup.html#Runtime%20Configuration)
    -   [Resource Types](/snmp/setup.html#Resource%20Types)
-   [Predefined Constants](/snmp/constants.html)
-   [SNMP Functions](/ref/snmp.html)
    -   [snmp\_get\_quick\_print](/ref/snmp.html#snmp_get_quick_print) —
        Fetches the current value of the UCD library's quick\_print
        setting
    -   [snmp\_get\_valueretrieval](/ref/snmp.html#snmp_get_valueretrieval)
        — Return the method how the SNMP values will be returned
    -   [snmp\_read\_mib](/ref/snmp.html#snmp_read_mib) — Reads and
        parses a MIB file into the active MIB tree
    -   [snmp\_set\_enum\_print](/ref/snmp.html#snmp_set_enum_print) —
        Return all values that are enums with their enum value instead
        of the raw integer
    -   [snmp\_set\_oid\_numeric\_print](/ref/snmp.html#snmp_set_oid_numeric_print)
        — Set the OID output format
    -   [snmp\_set\_oid\_output\_format](/ref/snmp.html#snmp_set_oid_output_format)
        — Set the OID output format
    -   [snmp\_set\_quick\_print](/ref/snmp.html#snmp_set_quick_print) —
        Set the value of quick\_print within the UCD SNMP library
    -   [snmp\_set\_valueretrieval](/ref/snmp.html#snmp_set_valueretrieval)
        — Specify the method how the SNMP values will be returned
    -   [snmp2\_get](/ref/snmp.html#snmp2_get) — Fetch an SNMP object
    -   [snmp2\_getnext](/ref/snmp.html#snmp2_getnext) — Fetch the SNMP
        object which follows the given object id
    -   [snmp2\_real\_walk](/ref/snmp.html#snmp2_real_walk) — Return all
        objects including their respective object ID within the
        specified one
    -   [snmp2\_set](/ref/snmp.html#snmp2_set) — Set the value of an
        SNMP object
    -   [snmp2\_walk](/ref/snmp.html#snmp2_walk) — Fetch all the SNMP
        objects from an agent
    -   [snmp3\_get](/ref/snmp.html#snmp3_get) — Fetch an SNMP object
    -   [snmp3\_getnext](/ref/snmp.html#snmp3_getnext) — Fetch the SNMP
        object which follows the given object id
    -   [snmp3\_real\_walk](/ref/snmp.html#snmp3_real_walk) — Return all
        objects including their respective object ID within the
        specified one
    -   [snmp3\_set](/ref/snmp.html#snmp3_set) — Set the value of an
        SNMP object
    -   [snmp3\_walk](/ref/snmp.html#snmp3_walk) — Fetch all the SNMP
        objects from an agent
    -   [snmpget](/ref/snmp.html#snmpget) — Fetch an SNMP object
    -   [snmpgetnext](/ref/snmp.html#snmpgetnext) — Fetch the SNMP
        object which follows the given object id
    -   [snmprealwalk](/ref/snmp.html#snmprealwalk) — Return all objects
        including their respective object ID within the specified one
    -   [snmpset](/ref/snmp.html#snmpset) — Set the value of an SNMP
        object
    -   [snmpwalk](/ref/snmp.html#snmpwalk) — Fetch all the SNMP objects
        from an agent
    -   [snmpwalkoid](/ref/snmp.html#snmpwalkoid) — Query for a tree of
        information about a network entity
-   [SNMP](/class/snmp.html) — The SNMP class
    -   [SNMP::close](/class/snmp.html#SNMP::close) — Close SNMP session
    -   [SNMP::\_\_construct](/class/snmp.html#SNMP::__construct) —
        Creates SNMP instance representing session to remote SNMP agent
    -   [SNMP::get](/class/snmp.html#SNMP::get) — Fetch an SNMP object
    -   [SNMP::getErrno](/class/snmp.html#SNMP::getErrno) — Get last
        error code
    -   [SNMP::getError](/class/snmp.html#SNMP::getError) — Get last
        error message
    -   [SNMP::getnext](/class/snmp.html#SNMP::getnext) — Fetch an SNMP
        object which follows the given object id
    -   [SNMP::set](/class/snmp.html#SNMP::set) — Set the value of an
        SNMP object
    -   [SNMP::setSecurity](/class/snmp.html#SNMP::setSecurity) —
        Configures security-related SNMPv3 session parameters
    -   [SNMP::walk](/class/snmp.html#SNMP::walk) — Fetch SNMP object
        subtree
-   [SNMPException](/class/snmpexception.html) — The SNMPException class

Introduction
------------

Represents SNMP session.

Class synopsis
--------------

**SNMP**

<span class="ooclass"> class **SNMP** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">int</span>
`$max_oids` ;

<span class="modifier">public</span> <span class="type">int</span>
`$valueretrieval` ;

<span class="modifier">public</span> <span class="type">bool</span>
`$quick_print` ;

<span class="modifier">public</span> <span class="type">bool</span>
`$enum_print` ;

<span class="modifier">public</span> <span class="type">int</span>
`$oid_output_format` ;

<span class="modifier">public</span> <span class="type">bool</span>
`$oid_increasing_check` ;

<span class="modifier">public</span> <span class="type">int</span>
`$exceptions_enabled` ;

<span class="modifier">public</span> <span class="type">array</span>
`$info` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$version`</span> ,
<span class="methodparam"><span class="type">string</span>
`$hostname`</span> , <span class="methodparam"><span
class="type">string</span> `$community`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">mixed</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$preserve_keys`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getErrno</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getnext</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">set</span> ( <span class="methodparam"><span
class="type">mixed</span> `$object_id`</span> , <span
class="methodparam"><span class="type">mixed</span> `$type`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSecurity</span> ( <span
class="methodparam"><span class="type">string</span> `$sec_level`</span>
\[, <span class="type">string</span> `$auth_protocol`<span
class="initializer"> = </span> \[, <span class="type">string</span>
`$auth_passphrase`<span class="initializer"> = </span> \[, <span
class="type">string</span> `$priv_protocol`<span class="initializer"> =
</span> \[, <span class="type">string</span> `$priv_passphrase`<span
class="initializer"> = </span> \[, <span class="type">string</span>
`$contextName`<span class="initializer"> = </span> \[, <span
class="type">string</span> `$contextEngineID`<span class="initializer">
= </span> \]\]\]\]\]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">walk</span> ( <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$suffix_as_key`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$max_repetitions`</span> \[, <span class="methodparam"><span
class="type">int</span> `$non_repeaters`</span> \]\]\] )

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_NOERROR` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_GENERIC` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_TIMEOUT` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_ERROR_IN_REPLY` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_OID_NOT_INCREASING` <span class="initializer"> = 16</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_OID_PARSING_ERROR` <span class="initializer"> = 32</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_MULTIPLE_SET_QUERIES` <span class="initializer"> =
64</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::ERRNO_ANY` <span class="initializer"> = 126</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::VERSION_1` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::VERSION_2C` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::VERSION_2c` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SNMP::VERSION_3` <span class="initializer"> = 3</span> ;

}

Properties
----------

`max_oids`  
Maximum OID per GET/SET/GETBULK request

`valueretrieval`  
Controls the method how the SNMP values will be returned

|                          |                                                                                                                                                                                                                                                                       |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`SNMP_VALUE_LIBRARY`** | The return values will be as returned by the Net-SNMP library.                                                                                                                                                                                                        |
| **`SNMP_VALUE_PLAIN`**   | The return values will be the plain value without the SNMP type hint.                                                                                                                                                                                                 |
| **`SNMP_VALUE_OBJECT`**  | The return values will be objects with the properties "value" and "type", where the latter is one of the SNMP\_OCTET\_STR, SNMP\_COUNTER etc. constants. The way "value" is returned is based on which one of **`SNMP_VALUE_LIBRARY`**, **`SNMP_VALUE_PLAIN`** is set |

`quick_print`  
Value of `quick_print` within the NET-SNMP library

Sets the value of `quick_print` within the NET-SNMP library. When this
is set (1), the SNMP library will return 'quick printed' values. This
means that just the value will be printed. When `quick_print` is not
enabled (default) the UCD SNMP library prints extra information
including the type of the value (i.e. IpAddress or OID). Additionally,
if quick\_print is not enabled, the library prints additional hex values
for all strings of three characters or less.

`enum_print`  
Controls the way enum values are printed

Parameter toggles if walk/get etc. should automatically lookup enum
values in the MIB and return them together with their human readable
string.

`oid_output_format`  
Controls OID output format

|                               |                                                                     |
|-------------------------------|---------------------------------------------------------------------|
| **`SNMP_OID_OUTPUT_FULL`**    | .iso.org.dod.internet.mgmt.mib-2.system.sysUpTime.sysUpTimeInstance |
| **`SNMP_OID_OUTPUT_NUMERIC`** | .1.3.6.1.2.1.1.3.0                                                  |
| **`SNMP_OID_OUTPUT_MODULE`**  | DISMAN-EVENT-MIB::sysUpTimeInstance                                 |
| **`SNMP_OID_OUTPUT_SUFFIX`**  | sysUpTimeInstance                                                   |
| **`SNMP_OID_OUTPUT_UCD`**     | system.sysUpTime.sysUpTimeInstance                                  |
| **`SNMP_OID_OUTPUT_NONE`**    | Undefined                                                           |

`oid_increasing_check`  
Controls disabling check for increasing OID while walking OID tree

Some SNMP agents are known for returning OIDs out of order but can
complete the walk anyway. Other agents return OIDs that are out of order
and can cause <span class="methodname">SNMP::walk</span> to loop
indefinitely until memory limit will be reached. PHP SNMP library by
default performs OID increasing check and stops walking on OID tree when
it detects possible loop with issuing warning about non-increasing OID
faced. Set `oid_increasing_check` to **`FALSE`** to disable this check.

`exceptions_enabled`  
Controls which failures will raise SNMPException instead of warning. Use
bitwise OR'ed **`SNMP::ERRNO_*`** constants. By default all SNMP
exceptions are disabled.

`info`  
Read-only property with remote agent configuration: hostname, port,
default timeout, default retries count

Predefined Constants
--------------------

SNMP Error Types
----------------

**`SNMP::ERRNO_NOERROR`**  
No SNMP-specific error occurred.

**`SNMP::ERRNO_GENERIC`**  
A generic SNMP error occurred.

**`SNMP::ERRNO_TIMEOUT`**  
Request to SNMP agent timed out.

**`SNMP::ERRNO_ERROR_IN_REPLY`**  
SNMP agent returned an error in reply.

**`SNMP::ERRNO_OID_NOT_INCREASING`**  
SNMP agent faced OID cycling reporning non-increasing OID while
executing (BULK)WALK command. This indicates bogus remote SNMP agent.

**`SNMP::ERRNO_OID_PARSING_ERROR`**  
Library failed while parsing OID (and/or type for SET command). No
queries has been made.

**`SNMP::ERRNO_MULTIPLE_SET_QUERIES`**  
Library will use multiple queries for SET operation requested. That
means that operation will be performed in a non-transaction manner and
second or subsequent chunks may fail if a type or value failure will be
faced.

**`SNMP::ERRNO_ANY`**  
All SNMP::ERRNO\_\* codes bitwise OR'ed.

SNMP Protocol Versions
----------------------

**`SNMP::VERSION_1`**  

**`SNMP::VERSION_2C`**, **`SNMP::VERSION_2c`**  

**`SNMP::VERSION_3`**  

SNMP::close
===========

Close SNMP session

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SNMP::close</span> ( <span
class="methodparam">void</span> )

Frees previously allocated SNMP session object.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SNMP::close</span> example**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  # ...
  # get, walk, etc goes here
  # ...
  $session->close();
?>
```

### See Also

-   <span class="methodname">SNMP::\_\_construct</span>

SNMP::\_\_construct
===================

Creates SNMP instance representing session to remote SNMP agent

### Description

<span class="modifier">public</span> <span
class="methodname">SNMP::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$version`</span> ,
<span class="methodparam"><span class="type">string</span>
`$hostname`</span> , <span class="methodparam"><span
class="type">string</span> `$community`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 1000000</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$retries`<span
class="initializer"> = 5</span></span> \]\] )

The function description goes here.

### Parameters

`version`  
SNMP protocol version: **`SNMP::VERSION_1`**, **`SNMP::VERSION_2C`**,
**`SNMP::VERSION_3`**.

`hostname`  
The SNMP agent. `hostname` may be suffixed with optional SNMP agent port
after colon. IPv6 addresses must be enclosed in square brackets if used
with port. If FQDN is used for `hostname` it will be resolved by
php-snmp library, not by Net-SNMP engine. Usage of IPv6 addresses when
specifying FQDN may be forced by enclosing FQDN into square brackets.
Here it is some examples:

|                                                      |                      |
|------------------------------------------------------|----------------------|
| IPv4 with default port                               | 127.0.0.1            |
| IPv6 with default port                               | ::1 or \[::1\]       |
| IPv4 with specific port                              | 127.0.0.1:1161       |
| IPv6 with specific port                              | \[::1\]:1161         |
| FQDN with default port                               | host.domain          |
| FQDN with specific port                              | host.domain:1161     |
| FQDN with default port, force usage of IPv6 address  | \[host.domain\]      |
| FQDN with specific port, force usage of IPv6 address | \[host.domain\]:1161 |

`community`  
The purpuse of `community` is SNMP version specific:

|                   |                     |
|-------------------|---------------------|
| SNMP::VERSION\_1  | SNMP community      |
| SNMP::VERSION\_2C | SNMP community      |
| SNMP::VERSION\_3  | SNMPv3 securityName |

`timeout`  
The number of microseconds until the first timeout.

`retries`  
The number of retries in case timeout occurs.

### Return Values

Returns SNMP object representing remote SNMP agent.

### Errors/Exceptions

<span class="methodname">SNMP::\_\_construct</span> throws an exception
when parameters count or types are wrong or unknown SNMP protocol
version specified.

### Examples

**Example \#1 Fetching sysLocation**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $sysdescr = $session->get("sysDescr.0");
  echo "$sysdescr\n";
?>
```

The above example will output something similar to:

    STRING: Test server

### See Also

-   <span class="methodname">SNMP::close</span>

SNMP::get
=========

Fetch an SNMP object

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SNMP::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$preserve_keys`<span class="initializer"> = **`FALSE`**</span></span>
\] )

Fetch an SNMP object specified in `object_id` using GET query.

### Parameters

If `object_id` is a string, then <span
class="methodname">SNMP::get</span> will return SNMP object as string.
If `object_id` is a array, all requested SNMP objects will be returned
as associative array of the SNMP object ids and their values.

`object_id`  
The SNMP object (OID) or objects

`preserve_keys`  
When `object_id` is a array and `preserve_keys` set to **`TRUE`** keys
in results will be taken exactly as in `object_id`, otherwise
`SNMP::oid_output_format` property is used to determinate the form of
keys.

### Return Values

Returns SNMP objects requested as string or array depending on
`object_id` type or **`FALSE`** on error.

### Errors/Exceptions

This method does not throw any exceptions by default. To enable throwing
an SNMPException exception when some of library errors occur the SNMP
class parameter `exceptions_enabled` should be set to a corresponding
value. See
<a href="/class/snmp.html#" class="link"><code class="parameter">SNMP::$exceptions_enabled</code> explanation</a>
for more details.

### Examples

**Example \#1 Single SNMP object**

Single SNMP object may be requested in two ways: as string resulting
string return value or as single-element array with associative array as
output.

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $sysdescr = $session->get("sysDescr.0");
  echo "$sysdescr\n";
  $sysdescr = $session->get(array("sysDescr.0"));
  print_r($sysdescr);
?>
```

The above example will output something similar to:

    STRING: Test server
    Array
    (
        [SNMPv2-MIB::sysDescr.0] => STRING: Test server
    )

**Example \#2 Multiple SNMP objects**

``` php
$session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $results = $session->get(array("sysDescr.0", "sysName.0"));
  print_r($results);
  $session->close();
```

The above example will output something similar to:

    Array
    (
        [SNMPv2-MIB::sysDescr.0] => STRING: Test server
        [SNMPv2-MIB::sysName.0] => STRING: myhost.nodomain
    )

### See Also

-   <span class="methodname">SNMP::getErrno</span>
-   <span class="methodname">SNMP::getError</span>

SNMP::getErrno
==============

Get last error code

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SNMP::getErrno</span> ( <span
class="methodparam">void</span> )

Returns error code from last SNMP request.

### Return Values

Returns one of SNMP error code values described in constants chapter.

### Examples

**Example \#1 <span class="methodname">SNMP::getErrno</span> example**

``` php
<?php
$session = new SNMP(SNMP::VERSION_2c, '127.0.0.1', 'boguscommunity');
var_dump(@$session->get('.1.3.6.1.2.1.1.1.0'));
var_dump($session->getErrno() == SNMP::ERRNO_TIMEOUT);
?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="methodname">SNMP::getError</span>

SNMP::getError
==============

Get last error message

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SNMP::getError</span> ( <span
class="methodparam">void</span> )

Returns string with error from last SNMP request.

### Return Values

String describing error from last SNMP request.

### Examples

**Example \#1 <span class="methodname">SNMP::getError</span> example**

``` php
<?php
$session = new SNMP(SNMP::VERSION_2c, '127.0.0.1', 'boguscommunity');
var_dump(@$session->get('.1.3.6.1.2.1.1.1.0'));
var_dump($session->getError());
?>
```

The above example will output:

    bool(false)
    string(26) "No response from 127.0.0.1"

### See Also

-   <span class="methodname">SNMP::getErrno</span>

SNMP::getnext
=============

Fetch an SNMP object which follows the given object id

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SNMP::getnext</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
)

Fetch an SNMP object that follows specified `object_id`.

### Parameters

If `object_id` is a string, then <span
class="methodname">SNMP::getnext</span> will return SNMP object as
string. If `object_id` is a array, all requested SNMP objects will be
returned as associative array of the SNMP object ids and their values.

`object_id`  
The SNMP object (OID) or objects

### Return Values

Returns SNMP objects requested as string or array depending on
`object_id` type or **`FALSE`** on error.

### Errors/Exceptions

This method does not throw any exceptions by default. To enable throwing
an SNMPException exception when some of library errors occur the SNMP
class parameter `exceptions_enabled` should be set to a corresponding
value. See
<a href="/class/snmp.html#" class="link"><code class="parameter">SNMP::$exceptions_enabled</code> explanation</a>
for more details.

### Examples

**Example \#1 Single SNMP object**

Single SNMP object may be requested in two ways: as string resulting
string return value or as single-element array with associative array as
output.

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $nsysdescr = $session->getnext("sysDescr.0");
  echo "$nsysdescr\n";
  $nsysdescr = $session->getnext(array("sysDescr.0"));
  print_r($nsysdescr);
?>
```

The above example will output something similar to:

    OID: NET-SNMP-MIB::netSnmpAgentOIDs.8
    Array
    (
        [SNMPv2-MIB::sysObjectID.0] => OID: NET-SNMP-MIB::netSnmpAgentOIDs.8
    )

**Example \#2 Miltiple SNMP objects**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $results = $session->getnext(array("sysDescr.0", "sysName.0"));
  print_r($results);
  $session->close();
?>
```

The above example will output something similar to:

    Array
    (
        [SNMPv2-MIB::sysObjectID.0] => OID: NET-SNMP-MIB::netSnmpAgentOIDs.8
        [SNMPv2-MIB::sysLocation.0] => STRING: Nowhere
    )

### See Also

-   <span class="methodname">SNMP::getErrno</span>
-   <span class="methodname">SNMP::getError</span>

SNMP::set
=========

Set the value of an SNMP object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SNMP::set</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$type`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

Requests remote SNMP agent setting the value of one or more SNMP objects
specified by the `object_id`.

### Parameters

`object_id`  
The SNMP object id

When count of OIDs in object\_id array is greater than max\_oids object
property set method will have to use multiple queries to perform
requested value updates. In this case type and value checks are made
per-chunk so second or subsequent requests may fail due to wrong type or
value for OID requested. To mark this a warning is raised when count of
OIDs in object\_id array is greater than max\_oids.

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

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

This method does not throw any exceptions by default. To enable throwing
an SNMPException exception when some of library errors occur the SNMP
class parameter `exceptions_enabled` should be set to a corresponding
value. See
<a href="/class/snmp.html#" class="link"><code class="parameter">SNMP::$exceptions_enabled</code> explanation</a>
for more details.

### Examples

**Example \#1 Set single SNMP object id**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_2C, "127.0.0.1", "private");
  $session->set('SNMPv2-MIB::sysContact.0', 's', "Nobody");
?>
```

**Example \#2 Set multiple values using single <span
class="methodname">SNMP::set</span> call**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_2C, "127.0.0.1", "private");
  $session->set(array('SNMPv2-MIB::sysContact.0', 'SNMPv2-MIB::sysLocation.0'), array('s', 's'), array("Nobody", "Nowhere"));
// or
  $session->set(array('SNMPv2-MIB::sysContact.0', 'SNMPv2-MIB::sysLocation.0'), 's', array("Nobody", "Nowhere"));
?>
```

**Example \#3 Using <span class="methodname">SNMP::set</span> for
setting BITS SNMP object id**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_2C, "127.0.0.1", "private");
  $session->set('FOO-MIB::bar.42', 'b', '0 1 2 3 4');
// or
  $session->set('FOO-MIB::bar.42', 'x', 'F0');
?>
```

### See Also

-   <span class="methodname">SNMP::get</span>

SNMP::setSecurity
=================

Configures security-related SNMPv3 session parameters

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SNMP::setSecurity</span> ( <span
class="methodparam"><span class="type">string</span> `$sec_level`</span>
\[, <span class="type">string</span> `$auth_protocol`<span
class="initializer"> = </span> \[, <span class="type">string</span>
`$auth_passphrase`<span class="initializer"> = </span> \[, <span
class="type">string</span> `$priv_protocol`<span class="initializer"> =
</span> \[, <span class="type">string</span> `$priv_passphrase`<span
class="initializer"> = </span> \[, <span class="type">string</span>
`$contextName`<span class="initializer"> = </span> \[, <span
class="type">string</span> `$contextEngineID`<span class="initializer">
= </span> \]\]\]\]\]\] )

setSecurity configures security-related session parameters used in SNMP
protocol version 3

### Parameters

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

`contextName`  
the context name

`contextEngineID`  
the context EngineID

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SNMP::setSecurity</span>
example**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_3, $hostname, $rwuser, $timeout, $retries);
  $session->setSecurity('authPriv', 'MD5', $auth_pass, 'AES', $priv_pass, '', 'aeeeff');
?>
```

### See Also

-   <span class="methodname">SNMP::\_\_construct</span>

SNMP::walk
==========

Fetch SNMP object subtree

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">SNMP::walk</span> ( <span class="methodparam"><span
class="type">string</span> `$object_id`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$suffix_as_key`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$max_repetitions`</span> \[, <span class="methodparam"><span
class="type">int</span> `$non_repeaters`</span> \]\]\] )

<span class="methodname">SNMP::walk</span> is used to read SNMP subtree
rooted at specified `object_id`.

### Parameters

`object_id`  
Root of subtree to be fetched

`suffix_as_key`  
By default full OID notation is used for keys in output array. If set to
**`TRUE`** subtree prefix will be removed from keys leaving only suffix
of object\_id.

`non_repeaters`  
This specifies the number of supplied variables that should not be
iterated over. The default is to use this value from SNMP object.

`max_repetitions`  
This specifies the maximum number of iterations over the repeating
variables. The default is to use this value from SNMP object.

### Return Values

Returns an associative array of the SNMP object ids and their values on
success or **`FALSE`** on error. When a SNMP error occures <span
class="methodname">SNMP::getErrno</span> and <span
class="methodname">SNMP::getError</span> can be used for retrieving
error number (specific to SNMP extension, see class constants) and error
message respectively.

### Errors/Exceptions

This method does not throw any exceptions by default. To enable throwing
an SNMPException exception when some of library errors occur the SNMP
class parameter `exceptions_enabled` should be set to a corresponding
value. See
<a href="/class/snmp.html#" class="link"><code class="parameter">SNMP::$exceptions_enabled</code> explanation</a>
for more details.

### Examples

**Example \#1 <span class="methodname">SNMP::walk</span> example**

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $fulltree = $session->walk(".");
  print_r($fulltree);
  $session->close();
?>
```

The above example will output something similar to:

    Array
    (
        [SNMPv2-MIB::sysDescr.0] => STRING: Test server
        [SNMPv2-MIB::sysObjectID.0] => OID: NET-SNMP-MIB::netSnmpAgentOIDs.8
        [DISMAN-EVENT-MIB::sysUpTimeInstance] => Timeticks: (1150681750) 133 days, 4:20:17.50
        [SNMPv2-MIB::sysContact.0] => STRING: Nobody
        [SNMPv2-MIB::sysName.0] => STRING: server.localdomain
        ...
    )

**Example \#2 `suffix_as_key` example**

`suffix_as_key` may be used when merging multiple SNMP subtrees into
one. This example maps interface names to their type.

``` php
<?php
  $session = new SNMP(SNMP::VERSION_1, "127.0.0.1", "public");
  $session->valueretrieval = SNMP_VALUE_PLAIN;
  $ifDescr = $session->walk(".1.3.6.1.2.1.2.2.1.2", TRUE);
  $session->valueretrieval = SNMP_VALUE_LIBRARY;
  $ifType = $session->walk(".1.3.6.1.2.1.2.2.1.3", TRUE);
  print_r($ifDescr);
  print_r($ifType);
  $result = array();
  foreach($ifDescr as $i => $n) {
    $result[$n] = $ifType[$i];
  }
  print_r($result);
?>
```

The above example will output something similar to:

    Array
    (
        [1] => igb0
        [2] => igb1
        [3] => ipfw0
        [4] => lo0
        [5] => lagg0
    )
    Array
    (
        [1] => INTEGER: ieee8023adLag(161)
        [2] => INTEGER: ieee8023adLag(161)
        [3] => INTEGER: ethernetCsmacd(6)
        [4] => INTEGER: softwareLoopback(24)
        [5] => INTEGER: ethernetCsmacd(6)
    )
    Array
    (
        [igb0] => INTEGER: ieee8023adLag(161)
        [igb1] => INTEGER: ieee8023adLag(161)
        [ipfw0] => INTEGER: ethernetCsmacd(6)
        [lo0] => INTEGER: softwareLoopback(24)
        [lagg0] => INTEGER: ethernetCsmacd(6)
    )

### See Also

-   <span class="methodname">SNMP::getErrno</span>
-   <span class="methodname">SNMP::getError</span>

Introduction
------------

Represents an error raised by SNMP. You should not throw a <span
class="classname">SNMPException</span> from your own code. See
<a href="/language/exceptions.html" class="link">Exceptions</a> for more
information about Exceptions in PHP.

Class synopsis
--------------

**SNMPException**

<span class="ooclass"> class **SNMPException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**RuntimeException** </span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$code` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`code`  
*SNMP*library error code. Use <span
class="function">Exception::getCode</span> to access it.
