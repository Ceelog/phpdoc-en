geoip\_asnum\_by\_name
======================

Get the Autonomous System Numbers (ASN)

### Description

<span class="type">string</span> <span
class="methodname">geoip\_asnum\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_asnum\_by\_name</span> function will
return the Autonomous System Numbers (ASN) associated with an IP
address.

### Parameters

`hostname`  
The hostname or IP address.

### Return Values

Returns the ASN on success, or **`FALSE`** if the address cannot be
found in the database.

### Examples

**Example \#1 A <span class="function">geoip\_asnum\_by\_name</span>
example**

This will output the ASN of the host www.example.com.

``` php
<?php
$asn = geoip_asnum_by_name('www.example.com');

if ($asn) {
    echo 'The ASN is: ' . $asn;
}
?>
```

The above example will output:

    The ASN is: AS15133 EdgeCast Networks, Inc

geoip\_continent\_code\_by\_name
================================

Get the two letter continent code

### Description

<span class="type">string</span> <span
class="methodname">geoip\_continent\_code\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_continent\_code\_by\_name</span>
function will return the two letter continent code corresponding to a
hostname or an IP address.

### Parameters

`hostname`  
The hostname or IP address whose location is to be looked-up.

### Return Values

Returns the two letter continent code on success, or **`FALSE`** if the
address cannot be found in the database.

| Code | Continent name |
|------|----------------|
| *AF* | Africa         |
| *AN* | Antarctica     |
| *AS* | Asia           |
| *EU* | Europe         |
| *NA* | North america  |
| *OC* | Oceania        |
| *SA* | South america  |

### Examples

**Example \#1 A <span
class="function">geoip\_continent\_code\_by\_name</span> example**

This will print where the host example.com is located.

``` php
<?php
$continent = geoip_continent_code_by_name('www.example.com');
if ($continent) {
    echo 'This host is located in: ' . $continent;
}
?>
```

The above example will output:

     This host is located in: NA

### See Also

-   <span class="function">geoip\_country\_code\_by\_name</span>

geoip\_country\_code\_by\_name
==============================

Get the two letter country code

### Description

<span class="type">string</span> <span
class="methodname">geoip\_country\_code\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_country\_code\_by\_name</span>
function will return the two letter country code corresponding to a
hostname or an IP address.

### Parameters

`hostname`  
The hostname or IP address whose location is to be looked-up.

### Return Values

Returns the two letter ISO country code on success, or **`FALSE`** if
the address cannot be found in the database.

### Examples

**Example \#1 A <span
class="function">geoip\_country\_code\_by\_name</span> example**

This will print where the host example.com is located.

``` php
<?php
$country = geoip_country_code_by_name('www.example.com');
if ($country) {
    echo 'This host is located in: ' . $country;
}
?>
```

The above example will output:

    This host is located in: US

### Notes

**Caution**

Please see
<a href="http://www.maxmind.com/en/iso3166" class="link external">» http://www.maxmind.com/en/iso3166</a>
for a complete list of possible return values, including special codes.

### See Also

-   <span class="function">geoip\_country\_code3\_by\_name</span>
-   <span class="function">geoip\_country\_name\_by\_name</span>

geoip\_country\_code3\_by\_name
===============================

Get the three letter country code

### Description

<span class="type">string</span> <span
class="methodname">geoip\_country\_code3\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_country\_code3\_by\_name</span>
function will return the three letter country code corresponding to a
hostname or an IP address.

### Parameters

`hostname`  
The hostname or IP address whose location is to be looked-up.

### Return Values

Returns the three letter country code on success, or **`FALSE`** if the
address cannot be found in the database.

### Examples

**Example \#1 A <span
class="function">geoip\_country\_code3\_by\_name</span> example**

This will print where the host example.com is located.

``` php
<?php
$country = geoip_country_code3_by_name('www.example.com');
if ($country) {
    echo 'This host is located in: ' . $country;
}
?>
```

The above example will output:

    This host is located in: USA

### See Also

-   <span class="function">geoip\_country\_code\_by\_name</span>
-   <span class="function">geoip\_country\_name\_by\_name</span>

geoip\_country\_name\_by\_name
==============================

Get the full country name

### Description

<span class="type">string</span> <span
class="methodname">geoip\_country\_name\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_country\_name\_by\_name</span>
function will return the full country name corresponding to a hostname
or an IP address.

### Parameters

`hostname`  
The hostname or IP address whose location is to be looked-up.

### Return Values

Returns the country name on success, or **`FALSE`** if the address
cannot be found in the database.

### Examples

**Example \#1 A <span
class="function">geoip\_country\_name\_by\_name</span> example**

This will print where the host example.com is located.

``` php
<?php
$country = geoip_country_name_by_name('www.example.com');
if ($country) {
    echo 'This host is located in: ' . $country;
}
?>
```

The above example will output:

     This host is located in: United States

### See Also

-   <span class="function">geoip\_country\_code\_by\_name</span>
-   <span class="function">geoip\_country\_code3\_by\_name</span>

geoip\_database\_info
=====================

Get GeoIP Database information

### Description

<span class="type">string</span> <span
class="methodname">geoip\_database\_info</span> (\[ <span
class="methodparam"><span class="type">int</span> `$database`<span
class="initializer"> = GEOIP\_COUNTRY\_EDITION</span></span> \] )

The <span class="function">geoip\_database\_info</span> function returns
the corresponding GeoIP Database version as it is defined inside the
binary file.

If this function is called without arguments, it returns the version of
the GeoIP Free Country Edition.

### Parameters

`database`  
The database type as an integer. You can use the
<a href="/geoip/constants.html" class="link">various constants</a>
defined with this extension (ie: GEOIP\_\*\_EDITION).

### Return Values

Returns the corresponding database version, or **`NULL`** on error.

### Examples

**Example \#1 A <span class="function">geoip\_database\_info</span>
example**

This will output information regarding the database.

``` php
<?php
print geoip_database_info(GEOIP_COUNTRY_EDITION);
?>
```

The above example will output:

    GEO-106FREE 20060801 Build 1 Copyright (c) 2006 MaxMind LLC All Rights Reserved

geoip\_db\_avail
================

Determine if GeoIP Database is available

### Description

<span class="type">bool</span> <span
class="methodname">geoip\_db\_avail</span> ( <span
class="methodparam"><span class="type">int</span> `$database`</span> )

The <span class="function">geoip\_db\_avail</span> function returns if
the corresponding GeoIP Database is available and can be opened on disk.

It does not indicate if the file is a proper database, only if it is
readable.

### Parameters

`database`  
The database type as an integer. You can use the
<a href="/geoip/constants.html" class="link">various constants</a>
defined with this extension (ie: GEOIP\_\*\_EDITION).

### Return Values

Returns **`TRUE`** is database exists, **`FALSE`** if not found, or
**`NULL`** on error.

### Examples

**Example \#1 A <span class="function">geoip\_db\_avail</span> example**

This will output the current database version string.

``` php
<?php

if (geoip_db_avail(GEOIP_COUNTRY_EDITION))
    print geoip_database_info(GEOIP_COUNTRY_EDITION);
?>
```

The above example will output:

    GEO-106FREE 20080801 Build 1 Copyright (c) 2006 MaxMind LLC All Rights Reserved

geoip\_db\_filename
===================

Returns the filename of the corresponding GeoIP Database

### Description

<span class="type">string</span> <span
class="methodname">geoip\_db\_filename</span> ( <span
class="methodparam"><span class="type">int</span> `$database`</span> )

The <span class="function">geoip\_db\_filename</span> function returns
the filename of the corresponding GeoIP Database.

It does not indicate if the file exists or not on disk, only where the
library is looking for the database.

### Parameters

`database`  
The database type as an integer. You can use the
<a href="/geoip/constants.html" class="link">various constants</a>
defined with this extension (ie: GEOIP\_\*\_EDITION).

### Return Values

Returns the filename of the corresponding database, or **`NULL`** on
error.

### Examples

**Example \#1 A <span class="function">geoip\_db\_filename</span>
example**

This will output the filename of the corresponding database.

``` php
<?php

print geoip_db_filename(GEOIP_COUNTRY_EDITION);

?>
```

The above example will output:

    /usr/share/GeoIP/GeoIP.dat

geoip\_db\_get\_all\_info
=========================

Returns detailed information about all GeoIP database types

### Description

<span class="type">array</span> <span
class="methodname">geoip\_db\_get\_all\_info</span> ( <span
class="methodparam">void</span> )

The <span class="function">geoip\_db\_get\_all\_info</span> function
will return detailed information as a multi-dimensional array about all
the GeoIP database types.

This function is available even if no databases are installed. It will
simply list them as non-available.

The names of the different keys of the returning associative array are
as follows:

-   <span class="simpara"> "available" -- Boolean, indicate if DB is
    available (see <span class="function">geoip\_db\_avail</span>)
    </span>
-   <span class="simpara"> "description" -- The database description
    </span>
-   <span class="simpara"> "filename" -- The database filename on disk
    (see <span class="function">geoip\_db\_filename</span>) </span>

### Return Values

Returns the associative array.

### Examples

**Example \#1 A <span class="function">geoip\_db\_get\_all\_info</span>
example**

This will print the array containing all the information.

``` php
<?php
$infos = geoip_db_get_all_info();
if (is_array($infos)) {
    var_dump($infos);
}
?>
```

The above example will output:

    array(11) {
      [1]=>
      array(3) {
        ["available"]=>
        bool(true)
        ["description"]=>
        string(21) "GeoIP Country Edition"
        ["filename"]=>
        string(32) "/usr/share/GeoIP/GeoIP.dat"
      }

    [ ... ]

      [11]=>
      array(3) {
        ["available"]=>
        bool(false)
        ["description"]=>
        string(25) "GeoIP Domain Name Edition"
        ["filename"]=>
        string(38) "/usr/share/GeoIP/GeoIPDomain.dat"
      }
    }

**Example \#2 A <span class="function">geoip\_db\_get\_all\_info</span>
example**

You can use the various constants as keys to get only parts of the
information.

``` php
<?php
$infos = geoip_db_get_all_info();
if ($infos[GEOIP_COUNTRY_EDITION]['available']) {
    echo $infos[GEOIP_COUNTRY_EDITION]['description'];
}
?>
```

The above example will output:

    GeoIP Country Edition

geoip\_domain\_by\_name
=======================

Get the second level domain name

### Description

<span class="type">string</span> <span
class="methodname">geoip\_domain\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_domain\_by\_name</span> function will
return the second level domain names associated with a hostname or an IP
address.

This function is currently only available to users who have bought a
commercial GeoIP Domain Edition. A warning will be issued if the proper
database cannot be located.

### Parameters

`hostname`  
The hostname or IP address.

### Return Values

Returns the domain name on success, or **`FALSE`** if the address cannot
be found in the database.

### Examples

**Example \#1 A <span class="function">geoip\_domain\_by\_name</span>
example**

This will output the domain associated with IP 61.106.139.1.

``` php
<?php
$domain = geoip_domain_by_name('61.106.139.1');

if ($domain) {
    echo 'The domain is: '. $domain;
}

?>
```

The above example will output:

    The domain is: von.co.kr

geoip\_id\_by\_name
===================

Get the Internet connection type

### Description

<span class="type">int</span> <span
class="methodname">geoip\_id\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_id\_by\_name</span> function will
return the Internet connection type corresponding to a hostname or an IP
address.

The return value is numeric and can be compared to the following
constants:

-   <span class="simpara"> GEOIP\_UNKNOWN\_SPEED </span>
-   <span class="simpara"> GEOIP\_DIALUP\_SPEED </span>
-   <span class="simpara"> GEOIP\_CABLEDSL\_SPEED </span>
-   <span class="simpara"> GEOIP\_CORPORATE\_SPEED </span>

### Parameters

`hostname`  
The hostname or IP address whose connection type is to be looked-up.

### Return Values

Returns the connection type.

### Examples

**Example \#1 A <span class="function">geoip\_id\_by\_name</span>
example**

This will output the connection type of the host example.com.

``` php
<?php
$netspeed = geoip_id_by_name('www.example.com');

echo 'The connection type is ';

switch ($netspeed) {
    case GEOIP_DIALUP_SPEED:
        echo 'dial-up';
        break;
    case GEOIP_CABLEDSL_SPEED:
        echo 'cable or DSL';
        break;
    case GEOIP_CORPORATE_SPEED:
        echo 'corporate';
        break;
    case GEOIP_UNKNOWN_SPEED:
    default:
        echo 'unknown';
}
?>
```

The above example will output:

    The connection type is corporate

geoip\_isp\_by\_name
====================

Get the Internet Service Provider (ISP) name

### Description

<span class="type">string</span> <span
class="methodname">geoip\_isp\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_isp\_by\_name</span> function will
return the name of the Internet Service Provider (ISP) that an IP is
assigned to.

This function is currently only available to users who have bought a
commercial GeoIP ISP Edition. A warning will be issued if the proper
database cannot be located.

### Parameters

`hostname`  
The hostname or IP address.

### Return Values

Returns the ISP name on success, or **`FALSE`** if the address cannot be
found in the database.

### Examples

**Example \#1 A <span class="function">geoip\_isp\_by\_name</span>
example**

This will print the ISP name of host example.com.

``` php
<?php
$isp = geoip_isp_by_name('www.example.com');
if ($isp) {
    echo 'This host IP is from ISP: ' . $isp;
}
?>
```

The above example will output:

    This host IP is from ISP: ICANN c/o Internet Assigned Numbers Authority

geoip\_netspeedcell\_by\_name
=============================

Get the Internet connection speed

### Description

<span class="type">string</span> <span
class="methodname">geoip\_netspeedcell\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_netspeedcell\_by\_name</span> function
will return the Internet connection type and speed corresponding to a
hostname or an IP address.

This function is only available if using GeoIP Library version 1.4.8 or
newer.

This function is currently only available to users who have bought a
commercial GeoIP NetSpeedCell Edition. A warning will be issued if the
proper database cannot be located.

The return value is a string, common values are:

-   <span class="simpara"> Cable/DSL </span>
-   <span class="simpara"> Dialup </span>
-   <span class="simpara"> Cellular </span>
-   <span class="simpara"> Corporate </span>

### Parameters

`hostname`  
The hostname or IP address.

### Return Values

Returns the connection speed on success, or **`FALSE`** if the address
cannot be found in the database.

### Examples

**Example \#1 A <span
class="function">geoip\_netspeedcell\_by\_name</span> example**

This will output the connection speed of the host example.com.

``` php
<?php
$netspeed = geoip_netspeedcell_by_name('www.example.com');

if ($netspeed) {
    echo 'The connection type is: '. $netspeed;
}
?>
```

The above example will output:

    The connection type is: Corporate

geoip\_org\_by\_name
====================

Get the organization name

### Description

<span class="type">string</span> <span
class="methodname">geoip\_org\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_org\_by\_name</span> function will
return the name of the organization that an IP is assigned to.

This function is currently only available to users who have bought a
commercial GeoIP Organization, ISP or AS Edition. A warning will be
issued if the proper database cannot be located.

### Parameters

`hostname`  
The hostname or IP address.

### Return Values

Returns the organization name on success, or **`FALSE`** if the address
cannot be found in the database.

### Examples

**Example \#1 A <span class="function">geoip\_org\_by\_name</span>
example**

This will print to whom the host example.com IP is allocated.

``` php
<?php
$org = geoip_org_by_name('www.example.com');
if ($org) {
    echo 'This host IP is allocated to: ' . $org;
}
?>
```

The above example will output:

    This host IP is allocated to: ICANN c/o Internet Assigned Numbers Authority

geoip\_record\_by\_name
=======================

Returns the detailed City information found in the GeoIP Database

### Description

<span class="type">array</span> <span
class="methodname">geoip\_record\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_record\_by\_name</span> function will
return the record information corresponding to a hostname or an IP
address.

This function is available for both GeoLite City Edition and commercial
GeoIP City Edition. A warning will be issued if the proper database
cannot be located.

The names of the different keys of the returning associative array are
as follows:

-   <span class="simpara"> "continent\_code" -- Two letter continent
    code (as of version 1.0.4 with libgeoip 1.4.3 or newer) </span>
-   <span class="simpara"> "country\_code" -- Two letter country code
    (see <span class="function">geoip\_country\_code\_by\_name</span>)
    </span>
-   <span class="simpara"> "country\_code3" -- Three letter country code
    (see <span class="function">geoip\_country\_code3\_by\_name</span>)
    </span>
-   <span class="simpara"> "country\_name" -- The country name (see
    <span class="function">geoip\_country\_name\_by\_name</span>)
    </span>
-   <span class="simpara"> "region" -- The region code (ex: CA for
    California) </span>
-   <span class="simpara"> "city" -- The city. </span>
-   <span class="simpara"> "postal\_code" -- The Postal Code, FSA or Zip
    Code. </span>
-   <span class="simpara"> "latitude" -- The Latitude as signed double.
    </span>
-   <span class="simpara"> "longitude" -- The Longitude as signed
    double. </span>
-   <span class="simpara"> "dma\_code" -- Designated Market Area code
    (USA and Canada only) </span>
-   <span class="simpara"> "area\_code" -- The PSTN area code (ex: 212)
    </span>

### Parameters

`hostname`  
The hostname or IP address whose record is to be looked-up.

### Return Values

Returns the associative array on success, or **`FALSE`** if the address
cannot be found in the database.

### Changelog

| Version          | Description                                                       |
|------------------|-------------------------------------------------------------------|
| PECL geoip 1.0.4 | Adding the continent\_code with GeoIP Library 1.4.3 or newer only |
| PECL geoip 1.0.3 | Adding country\_code3 and country\_name                           |

### Examples

**Example \#1 A <span class="function">geoip\_record\_by\_name</span>
example**

This will print the array containing the record of host example.com.

``` php
<?php
$record = geoip_record_by_name('www.example.com');
if ($record) {
    print_r($record);
}
?>
```

The above example will output:

    Array
    (
        [continent_code] => NA
        [country_code] => US
        [country_code3] => USA
        [country_name] => United States
        [region] => CA
        [city] => Marina Del Rey
        [postal_code] => 
        [latitude] => 33.9776992798
        [longitude] => -118.435096741
        [dma_code] => 803
        [area_code] => 310
    )

geoip\_region\_by\_name
=======================

Get the country code and region

### Description

<span class="type">array</span> <span
class="methodname">geoip\_region\_by\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

The <span class="function">geoip\_region\_by\_name</span> function will
return the country and region corresponding to a hostname or an IP
address.

This function is currently only available to users who have bought a
commercial GeoIP Region Edition. A warning will be issued if the proper
database cannot be located.

The names of the different keys of the returning associative array are
as follows:

-   <span class="simpara"> "country\_code" -- Two letter country code
    (see <span class="function">geoip\_country\_code\_by\_name</span>)
    </span>
-   <span class="simpara"> "region" -- The region code (ex: CA for
    California) </span>

### Parameters

`hostname`  
The hostname or IP address whose region is to be looked-up.

### Return Values

Returns the associative array on success, or **`FALSE`** if the address
cannot be found in the database.

### Examples

**Example \#1 A <span class="function">geoip\_region\_by\_name</span>
example**

This will print the array containing the country code and region of the
host example.com.

``` php
<?php
$region = geoip_region_by_name('www.example.com');
if ($region) {
    print_r($region);
}
?>
```

The above example will output:

    Array
    (
        [country_code] => US
        [region] => CA
    )

geoip\_region\_name\_by\_code
=============================

Returns the region name for some country and region code combo

### Description

<span class="type">string</span> <span
class="methodname">geoip\_region\_name\_by\_code</span> ( <span
class="methodparam"><span class="type">string</span>
`$country_code`</span> , <span class="methodparam"><span
class="type">string</span> `$region_code`</span> )

The <span class="function">geoip\_region\_name\_by\_code</span> function
will return the region name corresponding to a country and region code
combo.

In the United States, the region code corresponds to the two-letter
abbreviation of each state. In Canada, the region code corresponds to
the two-letter province or territory code as attributed by Canada Post.

For the rest of the world, GeoIP uses FIPS 10-4 codes to represent
regions. You can check
<a href="http://www.maxmind.com/app/fips10_4" class="link external">» http://www.maxmind.com/app/fips10_4</a>
for a detailed list of FIPS 10-4 codes.

This function is always available if using GeoIP Library version 1.4.1
or newer. The data is taken directly from the GeoIP Library and not from
any database.

### Parameters

`country_code`  
The two-letter country code (see <span
class="function">geoip\_country\_code\_by\_name</span>)

`region_code`  
The two-letter (or digit) region code (see <span
class="function">geoip\_region\_by\_name</span>)

### Return Values

Returns the region name on success, or **`FALSE`** if the country and
region code combo cannot be found.

### Examples

**Example \#1 A <span
class="function">geoip\_region\_name\_by\_code</span> example using
region code for US/Canada**

This will print the region name for country CA (Canada), region QC
(Quebec).

``` php
<?php
$region = geoip_region_name_by_code('CA', 'QC');
if ($region) {
    echo 'Region name for CA/QC is: ' . $region;
}
?>
```

The above example will output:

    Region name for CA/QC is: Quebec

**Example \#2 A <span
class="function">geoip\_region\_name\_by\_code</span> example using FIPS
codes**

This will print the region name for country JP (Japan), region 01.

``` php
<?php
$region = geoip_region_name_by_code('JP', '01');
if ($region) {
    echo 'Region name for JP/01 is: ' . $region;
}
?>
```

The above example will output:

    Region name for JP/01 is: Aichi

geoip\_setup\_custom\_directory
===============================

Set a custom directory for the GeoIP database

### Description

<span class="type">void</span> <span
class="methodname">geoip\_setup\_custom\_directory</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

The <span class="function">geoip\_setup\_custom\_directory</span>
function will change the default directory of the GeoIP database. This
is equivalent to changing
<a href="/geoip/setup.html#" class="link">geoip.custom_directory</a>.

### Parameters

`path`  
The full path of where the GeoIP database is on disk.

### Return Values

No value is returned.

### Examples

**Example \#1 A <span
class="function">geoip\_setup\_custom\_directory</span> example**

This will change the GeoIP default database path.

``` php
<?php

geoip_setup_custom_directory('/some/other/path');

print geoip_db_filename(GEOIP_COUNTRY_EDITION);

?>
```

The above example will output:

    /some/other/path/GeoIP.dat

geoip\_time\_zone\_by\_country\_and\_region
===========================================

Returns the time zone for some country and region code combo

### Description

<span class="type">string</span> <span
class="methodname">geoip\_time\_zone\_by\_country\_and\_region</span> (
<span class="methodparam"><span class="type">string</span>
`$country_code`</span> \[, <span class="methodparam"><span
class="type">string</span> `$region_code`</span> \] )

The <span
class="function">geoip\_time\_zone\_by\_country\_and\_region</span>
function will return the time zone corresponding to a country and region
code combo.

In the United States, the region code corresponds to the two-letter
abbreviation of each state. In Canada, the region code corresponds to
the two-letter province or territory code as attributed by Canada Post.

For the rest of the world, GeoIP uses FIPS 10-4 codes to represent
regions. You can check
<a href="http://www.maxmind.com/app/fips10_4" class="link external">» http://www.maxmind.com/app/fips10_4</a>
for a detailed list of FIPS 10-4 codes.

This function is always available if using GeoIP Library version 1.4.1
or newer. The data is taken directly from the GeoIP Library and not from
any database.

### Parameters

`country_code`  
The two-letter country code (see <span
class="function">geoip\_country\_code\_by\_name</span>)

`region_code`  
The two-letter (or digit) region code (see <span
class="function">geoip\_region\_by\_name</span>)

### Return Values

Returns the time zone on success, or **`FALSE`** if the country and
region code combo cannot be found.

### Examples

**Example \#1 A <span
class="function">geoip\_time\_zone\_by\_country\_and\_region</span>
example using region code for US/Canada**

This will print the time zone for country CA (Canada), region QC
(Quebec).

``` php
<?php
$timezone = geoip_time_zone_by_country_and_region('CA', 'QC');
if ($timezone) {
    echo 'Time zone for CA/QC is: ' . $timezone;
}
?>
```

The above example will output:

    Time zone for CA/QC is: America/Montreal

**Example \#2 A <span
class="function">geoip\_time\_zone\_by\_country\_and\_region</span>
example using FIPS codes**

This will print the time zone for country JP (Japan), region 01 (Aichi).

``` php
<?php
$timezone = geoip_time_zone_by_country_and_region('JP', '01');
if ($timezone) {
    echo 'Time zone for JP/01 is: ' . $timezone;
}
?>
```

The above example will output:

    Time zone for JP/01 is: Asia/Tokyo

**Table of Contents**

-   [geoip\_asnum\_by\_name](/ref/geoip.html#geoip_asnum_by_name) — Get
    the Autonomous System Numbers (ASN)
-   [geoip\_continent\_code\_by\_name](/ref/geoip.html#geoip_continent_code_by_name)
    — Get the two letter continent code
-   [geoip\_country\_code\_by\_name](/ref/geoip.html#geoip_country_code_by_name)
    — Get the two letter country code
-   [geoip\_country\_code3\_by\_name](/ref/geoip.html#geoip_country_code3_by_name)
    — Get the three letter country code
-   [geoip\_country\_name\_by\_name](/ref/geoip.html#geoip_country_name_by_name)
    — Get the full country name
-   [geoip\_database\_info](/ref/geoip.html#geoip_database_info) — Get
    GeoIP Database information
-   [geoip\_db\_avail](/ref/geoip.html#geoip_db_avail) — Determine if
    GeoIP Database is available
-   [geoip\_db\_filename](/ref/geoip.html#geoip_db_filename) — Returns
    the filename of the corresponding GeoIP Database
-   [geoip\_db\_get\_all\_info](/ref/geoip.html#geoip_db_get_all_info) —
    Returns detailed information about all GeoIP database types
-   [geoip\_domain\_by\_name](/ref/geoip.html#geoip_domain_by_name) —
    Get the second level domain name
-   [geoip\_id\_by\_name](/ref/geoip.html#geoip_id_by_name) — Get the
    Internet connection type
-   [geoip\_isp\_by\_name](/ref/geoip.html#geoip_isp_by_name) — Get the
    Internet Service Provider (ISP) name
-   [geoip\_netspeedcell\_by\_name](/ref/geoip.html#geoip_netspeedcell_by_name)
    — Get the Internet connection speed
-   [geoip\_org\_by\_name](/ref/geoip.html#geoip_org_by_name) — Get the
    organization name
-   [geoip\_record\_by\_name](/ref/geoip.html#geoip_record_by_name) —
    Returns the detailed City information found in the GeoIP Database
-   [geoip\_region\_by\_name](/ref/geoip.html#geoip_region_by_name) —
    Get the country code and region
-   [geoip\_region\_name\_by\_code](/ref/geoip.html#geoip_region_name_by_code)
    — Returns the region name for some country and region code combo
-   [geoip\_setup\_custom\_directory](/ref/geoip.html#geoip_setup_custom_directory)
    — Set a custom directory for the GeoIP database
-   [geoip\_time\_zone\_by\_country\_and\_region](/ref/geoip.html#geoip_time_zone_by_country_and_region)
    — Returns the time zone for some country and region code combo
