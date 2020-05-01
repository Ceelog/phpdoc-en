ogg://
======

Audio streams

### Description

Files opened for reading via the `ogg://` wrapper are treated as
compressed audio encoded using the *OGG/Vorbis* codec. Similarly, files
opened for writing or appending via the `ogg://` wrapper are written as
compressed audio data. <span
class="function">stream\_get\_meta\_data</span>, when used on an
*OGG/Vorbis* file opened for reading will return various details about
the stream including the `vendor` tag, any included `comments`, the
number of `channels`, the sampling `rate`, and the encoding rate range
described by: `bitrate_lower`, `bitrate_upper`, `bitrate_nominal`, and
`bitrate_window`.

`ogg://` (PECL)

> **Note**: **This wrapper is not enabled by default**  
> <span class="simpara"> In order to use the `ogg://` wrapper you must
> install the
> <a href="https://pecl.php.net/package/oggvorbis" class="link external">» OGG/Vorbis</a>
> extension available from
> <a href="https://pecl.php.net/" class="link external">» PECL</a>.
> </span>

### Usage

-   <span class="simpara">`ogg://soundfile.ogg`</span>
-   <span class="simpara">`ogg:///path/to/soundfile.ogg`</span>
-   <span
    class="simpara">`ogg://http://www.example.com/path/to/soundstream.ogg`</span>

### Options

| Attribute                                                                        | Supported |
|----------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | No        |
| Allows Reading                                                                   | Yes       |
| Allows Writing                                                                   | Yes       |
| Allows Appending                                                                 | Yes       |
| Allows Simultaneous Reading and Writing                                          | No        |
| Supports <span class="function">stat</span>                                      | No        |
| Supports <span class="function">unlink</span>                                    | No        |
| Supports <span class="function">rename</span>                                    | No        |
| Supports <span class="function">mkdir</span>                                     | No        |
| Supports <span class="function">rmdir</span>                                     | No        |

| Name        | Usage                                                                                                                                                                                                                                                                      | Default                 | Mode         |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|--------------|
| *pcm\_mode* | PCM encoding to apply while reading, one of: **`OGGVORBIS_PCM_U8`**, **`OGGVORBIS_PCM_S8`**, **`OGGVORBIS_PCM_U16_BE`**, **`OGGVORBIS_PCM_S16_BE`**, **`OGGVORBIS_PCM_U16_LE`**, and **`OGGVORBIS_PCM_S16_LE`**. (8 vs 16 bit, signed or unsigned, big or little *endian*) | OGGVORBIS\_PCM\_S16\_LE | Read         |
| *rate*      | Sampling rate of input data, expressed in Hz                                                                                                                                                                                                                               | 44100                   | Write/Append |
| *bitrate*   | When given as an integer, the fixed bitrate at which to encode. (16000 to 131072) When given as a float, the variable bitrate quality to use. (-1.0 to 1.0)                                                                                                                | 128000                  | Write/Append |
| *channels*  | The number of audio channels to encode, typically 1 (Mono), or 2 (Stereo). May range as high as 16.                                                                                                                                                                        | 2                       | Write/Append |
| *comments*  | An array of string values to encode into the track header.                                                                                                                                                                                                                 |                         | Write/Append |

### Examples
