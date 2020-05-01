openal\_buffer\_create
======================

Generate OpenAL buffer

### Description

<span class="type">resource</span> <span
class="methodname">openal\_buffer\_create</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns an
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Buffer)</a>
resource on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_buffer\_loadwav</span>
-   <span class="function">openal\_buffer\_data</span>

openal\_buffer\_data
====================

Load a buffer with data

### Description

<span class="type">bool</span> <span
class="methodname">openal\_buffer\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$buffer`</span>
, <span class="methodparam"><span class="type">int</span>
`$format`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> , <span
class="methodparam"><span class="type">int</span> `$freq`</span> )

### Parameters

`buffer`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Buffer)</a>
resource (previously created by <span
class="function">openal\_buffer\_create</span>).

`format`  
Format of `data`, one of: **`AL_FORMAT_MONO8`**, **`AL_FORMAT_MONO16`**,
**`AL_FORMAT_STEREO8`** and **`AL_FORMAT_STEREO16`**

`data`  
Block of binary audio data in the `format` and `freq` specified.

`freq`  
Frequency of `data` given in Hz.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_buffer\_loadwav</span>
-   <span class="function">openal\_stream</span>

openal\_buffer\_destroy
=======================

Destroys an OpenAL buffer

### Description

<span class="type">bool</span> <span
class="methodname">openal\_buffer\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$buffer`</span>
)

### Parameters

`buffer`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Buffer)</a>
resource (previously created by <span
class="function">openal\_buffer\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_buffer\_create</span>

openal\_buffer\_get
===================

Retrieve an OpenAL buffer property

### Description

<span class="type">int</span> <span
class="methodname">openal\_buffer\_get</span> ( <span
class="methodparam"><span class="type">resource</span> `$buffer`</span>
, <span class="methodparam"><span class="type">int</span>
`$property`</span> )

### Parameters

`buffer`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Buffer)</a>
resource (previously created by <span
class="function">openal\_buffer\_create</span>).

`property`  
Specific property, one of: **`AL_FREQUENCY`**, **`AL_BITS`**,
**`AL_CHANNELS`** and **`AL_SIZE`**.

### Return Values

Returns an integer value appropriate to the `property` requested or
**`FALSE`** on failure.

### See Also

-   <span class="function">openal\_buffer\_create</span>

openal\_buffer\_loadwav
=======================

Load a .wav file into a buffer

### Description

<span class="type">bool</span> <span
class="methodname">openal\_buffer\_loadwav</span> ( <span
class="methodparam"><span class="type">resource</span> `$buffer`</span>
, <span class="methodparam"><span class="type">string</span>
`$wavfile`</span> )

### Parameters

`buffer`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Buffer)</a>
resource (previously created by <span
class="function">openal\_buffer\_create</span>).

`wavfile`  
Path to `.wav` file on *local* file system.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_buffer\_data</span>
-   <span class="function">openal\_stream</span>

openal\_context\_create
=======================

Create an audio processing context

### Description

<span class="type">resource</span> <span
class="methodname">openal\_context\_create</span> ( <span
class="methodparam"><span class="type">resource</span> `$device`</span>
)

### Parameters

`device`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Device)</a>
resource (previously created by <span
class="function">openal\_device\_open</span>).

### Return Values

Returns an
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Context)</a>
resource on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_device\_open</span>
-   <span class="function">openal\_context\_destroy</span>

openal\_context\_current
========================

Make the specified context current

### Description

<span class="type">bool</span> <span
class="methodname">openal\_context\_current</span> ( <span
class="methodparam"><span class="type">resource</span> `$context`</span>
)

### Parameters

`context`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Context)</a>
resource (previously created by <span
class="function">openal\_context\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_context\_create</span>

openal\_context\_destroy
========================

Destroys a context

### Description

<span class="type">bool</span> <span
class="methodname">openal\_context\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$context`</span>
)

### Parameters

`context`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Context)</a>
resource (previously created by <span
class="function">openal\_context\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_context\_create</span>

openal\_context\_process
========================

Process the specified context

### Description

<span class="type">bool</span> <span
class="methodname">openal\_context\_process</span> ( <span
class="methodparam"><span class="type">resource</span> `$context`</span>
)

### Parameters

`context`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Context)</a>
resource (previously created by <span
class="function">openal\_context\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_context\_create</span>
-   <span class="function">openal\_context\_current</span>
-   <span class="function">openal\_context\_suspend</span>

openal\_context\_suspend
========================

Suspend the specified context

### Description

<span class="type">bool</span> <span
class="methodname">openal\_context\_suspend</span> ( <span
class="methodparam"><span class="type">resource</span> `$context`</span>
)

### Parameters

`context`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Context)</a>
resource (previously created by <span
class="function">openal\_context\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_context\_create</span>
-   <span class="function">openal\_context\_current</span>
-   <span class="function">openal\_context\_process</span>

openal\_device\_close
=====================

Close an OpenAL device

### Description

<span class="type">bool</span> <span
class="methodname">openal\_device\_close</span> ( <span
class="methodparam"><span class="type">resource</span> `$device`</span>
)

### Parameters

`device`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Device)</a>
resource (previously created by <span
class="function">openal\_device\_open</span>) to be closed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_device\_open</span>

openal\_device\_open
====================

Initialize the OpenAL audio layer

### Description

<span class="type">resource</span> <span
class="methodname">openal\_device\_open</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$device_desc`</span> \] )

### Parameters

`device_desc`  
Open an audio device optionally specified by `device_desc`. If
`device_desc` is not specified the first available audio device will be
used.

### Return Values

Returns an
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Device)</a>
resource on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_device\_close</span>
-   <span class="function">openal\_context\_create</span>

openal\_listener\_get
=====================

Retrieve a listener property

### Description

<span class="type">mixed</span> <span
class="methodname">openal\_listener\_get</span> ( <span
class="methodparam"><span class="type">int</span> `$property`</span> )

### Parameters

`property`  
Property to retrieve, one of: **`AL_GAIN`** (float), **`AL_POSITION`**
(array(float,float,float)), **`AL_VELOCITY`** (array(float,float,float))
and **`AL_ORIENTATION`** (array(float,float,float)).

### Return Values

Returns a float or array of floats (as appropriate) or **`FALSE`** on
failure.

### See Also

-   <span class="function">openal\_listener\_set</span>

openal\_listener\_set
=====================

Set a listener property

### Description

<span class="type">bool</span> <span
class="methodname">openal\_listener\_set</span> ( <span
class="methodparam"><span class="type">int</span> `$property`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$setting`</span> )

### Parameters

`property`  
Property to set, one of: **`AL_GAIN`** (float), **`AL_POSITION`**
(array(float,float,float)), **`AL_VELOCITY`** (array(float,float,float))
and **`AL_ORIENTATION`** (array(float,float,float)).

`setting`  
Value to set, either float, or an array of floats as appropriate.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_listener\_get</span>

openal\_source\_create
======================

Generate a source resource

### Description

<span class="type">resource</span> <span
class="methodname">openal\_source\_create</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns an
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_set</span>
-   <span class="function">openal\_source\_play</span>
-   <span class="function">openal\_source\_destroy</span>

openal\_source\_destroy
=======================

Destroy a source resource

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
)

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_create</span>

openal\_source\_get
===================

Retrieve an OpenAL source property

### Description

<span class="type">mixed</span> <span
class="methodname">openal\_source\_get</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
, <span class="methodparam"><span class="type">int</span>
`$property`</span> )

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

`property`  
Property to get, one of: **`AL_SOURCE_RELATIVE`** (int),
**`AL_SOURCE_STATE`** (int), **`AL_PITCH`** (float), **`AL_GAIN`**
(float), **`AL_MIN_GAIN`** (float), **`AL_MAX_GAIN`** (float),
**`AL_MAX_DISTANCE`** (float), **`AL_ROLLOFF_FACTOR`** (float),
**`AL_CONE_OUTER_GAIN`** (float), **`AL_CONE_INNER_ANGLE`** (float),
**`AL_CONE_OUTER_ANGLE`** (float), **`AL_REFERENCE_DISTANCE`** (float),
**`AL_POSITION`** (array(float,float,float)), **`AL_VELOCITY`**
(array(float,float,float)), **`AL_DIRECTION`**
(array(float,float,float)).

### Return Values

Returns the type associated with the property being retrieved or
**`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_create</span>
-   <span class="function">openal\_source\_set</span>
-   <span class="function">openal\_source\_play</span>

openal\_source\_pause
=====================

Pause the source

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_pause</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
)

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_stop</span>
-   <span class="function">openal\_source\_play</span>
-   <span class="function">openal\_source\_rewind</span>

openal\_source\_play
====================

Start playing the source

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_play</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
)

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_stop</span>
-   <span class="function">openal\_source\_pause</span>
-   <span class="function">openal\_source\_rewind</span>

openal\_source\_rewind
======================

Rewind the source

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_rewind</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
)

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_stop</span>
-   <span class="function">openal\_source\_pause</span>
-   <span class="function">openal\_source\_play</span>

openal\_source\_set
===================

Set source property

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
, <span class="methodparam"><span class="type">int</span>
`$property`</span> , <span class="methodparam"><span
class="type">mixed</span> `$setting`</span> )

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

`property`  
Property to set, one of: **`AL_BUFFER`** (OpenAL(Source)),
**`AL_LOOPING`** (bool), **`AL_SOURCE_RELATIVE`** (int),
**`AL_SOURCE_STATE`** (int), **`AL_PITCH`** (float), **`AL_GAIN`**
(float), **`AL_MIN_GAIN`** (float), **`AL_MAX_GAIN`** (float),
**`AL_MAX_DISTANCE`** (float), **`AL_ROLLOFF_FACTOR`** (float),
**`AL_CONE_OUTER_GAIN`** (float), **`AL_CONE_INNER_ANGLE`** (float),
**`AL_CONE_OUTER_ANGLE`** (float), **`AL_REFERENCE_DISTANCE`** (float),
**`AL_POSITION`** (array(float,float,float)), **`AL_VELOCITY`**
(array(float,float,float)), **`AL_DIRECTION`**
(array(float,float,float)).

`setting`  
Value to assign to specified `property`. Refer to the description of
`property` for a description of the value(s) expected.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_create</span>
-   <span class="function">openal\_source\_get</span>
-   <span class="function">openal\_source\_play</span>

openal\_source\_stop
====================

Stop playing the source

### Description

<span class="type">bool</span> <span
class="methodname">openal\_source\_stop</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
)

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_play</span>
-   <span class="function">openal\_source\_pause</span>
-   <span class="function">openal\_source\_rewind</span>

openal\_stream
==============

Begin streaming on a source

### Description

<span class="type">resource</span> <span
class="methodname">openal\_stream</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
, <span class="methodparam"><span class="type">int</span>
`$format`</span> , <span class="methodparam"><span
class="type">int</span> `$rate`</span> )

### Parameters

`source`  
An
<a href="/openal/setup.html#Resource%20Types" class="link">Open AL(Source)</a>
resource (previously created by <span
class="function">openal\_source\_create</span>).

`format`  
Format of `data`, one of: **`AL_FORMAT_MONO8`**, **`AL_FORMAT_MONO16`**,
**`AL_FORMAT_STEREO8`** and **`AL_FORMAT_STEREO16`**

`rate`  
Frequency of data to stream given in Hz.

### Return Values

Returns a stream resource on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openal\_source\_create</span>
-   <span class="function">fwrite</span>

**Table of Contents**

-   [openal\_buffer\_create](/ref/openal.html#openal_buffer_create) —
    Generate OpenAL buffer
-   [openal\_buffer\_data](/ref/openal.html#openal_buffer_data) — Load a
    buffer with data
-   [openal\_buffer\_destroy](/ref/openal.html#openal_buffer_destroy) —
    Destroys an OpenAL buffer
-   [openal\_buffer\_get](/ref/openal.html#openal_buffer_get) — Retrieve
    an OpenAL buffer property
-   [openal\_buffer\_loadwav](/ref/openal.html#openal_buffer_loadwav) —
    Load a .wav file into a buffer
-   [openal\_context\_create](/ref/openal.html#openal_context_create) —
    Create an audio processing context
-   [openal\_context\_current](/ref/openal.html#openal_context_current)
    — Make the specified context current
-   [openal\_context\_destroy](/ref/openal.html#openal_context_destroy)
    — Destroys a context
-   [openal\_context\_process](/ref/openal.html#openal_context_process)
    — Process the specified context
-   [openal\_context\_suspend](/ref/openal.html#openal_context_suspend)
    — Suspend the specified context
-   [openal\_device\_close](/ref/openal.html#openal_device_close) —
    Close an OpenAL device
-   [openal\_device\_open](/ref/openal.html#openal_device_open) —
    Initialize the OpenAL audio layer
-   [openal\_listener\_get](/ref/openal.html#openal_listener_get) —
    Retrieve a listener property
-   [openal\_listener\_set](/ref/openal.html#openal_listener_set) — Set
    a listener property
-   [openal\_source\_create](/ref/openal.html#openal_source_create) —
    Generate a source resource
-   [openal\_source\_destroy](/ref/openal.html#openal_source_destroy) —
    Destroy a source resource
-   [openal\_source\_get](/ref/openal.html#openal_source_get) — Retrieve
    an OpenAL source property
-   [openal\_source\_pause](/ref/openal.html#openal_source_pause) —
    Pause the source
-   [openal\_source\_play](/ref/openal.html#openal_source_play) — Start
    playing the source
-   [openal\_source\_rewind](/ref/openal.html#openal_source_rewind) —
    Rewind the source
-   [openal\_source\_set](/ref/openal.html#openal_source_set) — Set
    source property
-   [openal\_source\_stop](/ref/openal.html#openal_source_stop) — Stop
    playing the source
-   [openal\_stream](/ref/openal.html#openal_stream) — Begin streaming
    on a source
