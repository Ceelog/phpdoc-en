Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`YAC_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`YAC_MAX_KEY_LEN`** (<span class="type">int</span>)  
<span class="simpara"> Max length of a key could be, it is 48 bytes.
</span>

**`YAC_MAX_VALUE_RAW_LEN`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`YAC_MAX_RAW_COMPRESSED_LEN`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`YAC_SERIALIZER_PHP`** (<span class="type">int</span>)  
<span class="simpara"> Use php serialize as serializer </span>

**`YAC_SERIALIZER_JSON`** (<span class="type">int</span>)  
<span class="simpara"> Use json as serializer(requrie --enable-json)
</span>

**`YAC_SERIALIZER_IGBINARY`** (<span class="type">int</span>)  
<span class="simpara"> Use igbinary as serializer(require
--enable-igbinary) </span>

**`YAC_SERIALIZER_MSGPACK`** (<span class="type">int</span>)  
<span class="simpara"> Use msgpack as serializer(require
--enable-msgpack) </span>

**`YAC_SERIALIZER`** (<span class="type">string</span>)  
<span class="simpara"> Which serialzier is yac used </span>
