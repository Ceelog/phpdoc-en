Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

| Constant                                                          | Value                            | Description      |
|-------------------------------------------------------------------|----------------------------------|------------------|
| **`SOAP_1_1`** (<span class="type">int</span>)                    | 1                                |                  |
| **`SOAP_1_2`** (<span class="type">int</span>)                    | 2                                |                  |
| **`SOAP_PERSISTENCE_SESSION`** (<span class="type">int</span>)    | 1                                |                  |
| **`SOAP_PERSISTENCE_REQUEST`** (<span class="type">int</span>)    | 2                                |                  |
| **`SOAP_FUNCTIONS_ALL`** (<span class="type">int</span>)          | 999                              |                  |
| **`SOAP_ENCODED`** (<span class="type">int</span>)                | 1                                |                  |
| **`SOAP_LITERAL`** (<span class="type">int</span>)                | 2                                |                  |
| **`SOAP_RPC`** (<span class="type">int</span>)                    | 1                                |                  |
| **`SOAP_DOCUMENT`** (<span class="type">int</span>)               | 2                                |                  |
| **`SOAP_ACTOR_NEXT`** (<span class="type">int</span>)             | 1                                |                  |
| **`SOAP_ACTOR_NONE`** (<span class="type">int</span>)             | 2                                |                  |
| **`SOAP_ACTOR_UNLIMATERECEIVER`** (<span class="type">int</span>) | 3                                |                  |
| **`SOAP_COMPRESSION_ACCEPT`** (<span class="type">int</span>)     | 32                               |                  |
| **`SOAP_COMPRESSION_GZIP`** (<span class="type">int</span>)       | 0                                |                  |
| **`SOAP_COMPRESSION_DEFLATE`** (<span class="type">int</span>)    | 16                               |                  |
| **`SOAP_AUTHENTICATION_BASIC`** (<span class="type">int</span>)   | 0                                |                  |
| **`SOAP_AUTHENTICATION_DIGEST`** (<span class="type">int</span>)  | 1                                |                  |
| **`SOAP_SSL_METHOD_TLS`** (<span class="type">int</span>)         | 0                                | Since PHP 5.5.0. |
| **`SOAP_SSL_METHOD_SSLv2`** (<span class="type">int</span>)       | 1                                | Since PHP 5.5.0. |
| **`SOAP_SSL_METHOD_SSLv3`** (<span class="type">int</span>)       | 2                                | Since PHP 5.5.0. |
| **`SOAP_SSL_METHOD_SSLv23`** (<span class="type">int</span>)      | 3                                | Since PHP 5.5.0. |
| **`UNKNOWN_TYPE`** (<span class="type">int</span>)                | 999998                           |                  |
| **`XSD_STRING`** (<span class="type">int</span>)                  | 101                              |                  |
| **`XSD_BOOLEAN`** (<span class="type">int</span>)                 | 102                              |                  |
| **`XSD_DECIMAL`** (<span class="type">int</span>)                 | 103                              |                  |
| **`XSD_FLOAT`** (<span class="type">int</span>)                   | 104                              |                  |
| **`XSD_DOUBLE`** (<span class="type">int</span>)                  | 105                              |                  |
| **`XSD_DURATION`** (<span class="type">int</span>)                | 106                              |                  |
| **`XSD_DATETIME`** (<span class="type">int</span>)                | 107                              |                  |
| **`XSD_TIME`** (<span class="type">int</span>)                    | 108                              |                  |
| **`XSD_DATE`** (<span class="type">int</span>)                    | 109                              |                  |
| **`XSD_GYEARMONTH`** (<span class="type">int</span>)              | 110                              |                  |
| **`XSD_GYEAR`** (<span class="type">int</span>)                   | 111                              |                  |
| **`XSD_GMONTHDAY`** (<span class="type">int</span>)               | 112                              |                  |
| **`XSD_GDAY`** (<span class="type">int</span>)                    | 113                              |                  |
| **`XSD_GMONTH`** (<span class="type">int</span>)                  | 114                              |                  |
| **`XSD_HEXBINARY`** (<span class="type">int</span>)               | 115                              |                  |
| **`XSD_BASE64BINARY`** (<span class="type">int</span>)            | 116                              |                  |
| **`XSD_ANYURI`** (<span class="type">int</span>)                  | 117                              |                  |
| **`XSD_QNAME`** (<span class="type">int</span>)                   | 118                              |                  |
| **`XSD_NOTATION`** (<span class="type">int</span>)                | 119                              |                  |
| **`XSD_NORMALIZEDSTRING`** (<span class="type">int</span>)        | 120                              |                  |
| **`XSD_TOKEN`** (<span class="type">int</span>)                   | 121                              |                  |
| **`XSD_LANGUAGE`** (<span class="type">int</span>)                | 122                              |                  |
| **`XSD_NMTOKEN`** (<span class="type">int</span>)                 | 123                              |                  |
| **`XSD_NAME`** (<span class="type">int</span>)                    | 124                              |                  |
| **`XSD_NCNAME`** (<span class="type">int</span>)                  | 125                              |                  |
| **`XSD_ID`** (<span class="type">int</span>)                      | 126                              |                  |
| **`XSD_IDREF`** (<span class="type">int</span>)                   | 127                              |                  |
| **`XSD_IDREFS`** (<span class="type">int</span>)                  | 128                              |                  |
| **`XSD_ENTITY`** (<span class="type">int</span>)                  | 129                              |                  |
| **`XSD_ENTITIES`** (<span class="type">int</span>)                | 130                              |                  |
| **`XSD_INTEGER`** (<span class="type">int</span>)                 | 131                              |                  |
| **`XSD_NONPOSITIVEINTEGER`** (<span class="type">int</span>)      | 132                              |                  |
| **`XSD_NEGATIVEINTEGER`** (<span class="type">int</span>)         | 133                              |                  |
| **`XSD_LONG`** (<span class="type">int</span>)                    | 134                              |                  |
| **`XSD_INT`** (<span class="type">int</span>)                     | 135                              |                  |
| **`XSD_SHORT`** (<span class="type">int</span>)                   | 136                              |                  |
| **`XSD_BYTE`** (<span class="type">int</span>)                    | 137                              |                  |
| **`XSD_NONNEGATIVEINTEGER`** (<span class="type">int</span>)      | 138                              |                  |
| **`XSD_UNSIGNEDLONG`** (<span class="type">int</span>)            | 139                              |                  |
| **`XSD_UNSIGNEDINT`** (<span class="type">int</span>)             | 140                              |                  |
| **`XSD_UNSIGNEDSHORT`** (<span class="type">int</span>)           | 141                              |                  |
| **`XSD_UNSIGNEDBYTE`** (<span class="type">int</span>)            | 142                              |                  |
| **`XSD_POSITIVEINTEGER`** (<span class="type">int</span>)         | 143                              |                  |
| **`XSD_NMTOKENS`** (<span class="type">int</span>)                | 144                              |                  |
| **`XSD_ANYTYPE`** (<span class="type">int</span>)                 | 145                              |                  |
| **`XSD_ANYXML`** (<span class="type">int</span>)                  | 147                              |                  |
| **`APACHE_MAP`** (<span class="type">int</span>)                  | 200                              |                  |
| **`SOAP_ENC_OBJECT`** (<span class="type">int</span>)             | 301                              |                  |
| **`SOAP_ENC_ARRAY`** (<span class="type">int</span>)              | 300                              |                  |
| **`XSD_1999_TIMEINSTANT`** (<span class="type">int</span>)        | 401                              |                  |
| **`XSD_NAMESPACE`** (<span class="type">int</span>)               | http://www.w3.org/2001/XMLSchema |                  |
| **`XSD_1999_NAMESPACE`** (<span class="type">int</span>)          | http://www.w3.org/1999/XMLSchema |                  |
| **`SOAP_SINGLE_ELEMENT_ARRAYS`** (<span class="type">int</span>)  | 1                                |                  |
| **`SOAP_WAIT_ONE_WAY_CALLS`** (<span class="type">int</span>)     | 2                                |                  |
| **`SOAP_USE_XSI_ARRAY_TYPE`** (<span class="type">int</span>)     | 4                                |                  |
| **`WSDL_CACHE_NONE`** (<span class="type">int</span>)             | 0                                |                  |
| **`WSDL_CACHE_DISK`** (<span class="type">int</span>)             | 1                                |                  |
| **`WSDL_CACHE_MEMORY`** (<span class="type">int</span>)           | 2                                |                  |
| **`WSDL_CACHE_BOTH`** (<span class="type">int</span>)             | 3                                |                  |
