Predefined Constants
====================

It is possible to identify at runtime which *iconv* implementation is
adopted by this extension.

| Name                | Type                             | Description                |
|---------------------|----------------------------------|----------------------------|
| **`ICONV_IMPL`**    | <span class="type">string</span> | The implementation name    |
| **`ICONV_VERSION`** | <span class="type">string</span> | The implementation version |

> **Note**:
>
> Writing implementation-dependent scripts with these constants is
> strongly discouraged.

The following constants are also available:

| Name                                      | Type                          | Description                                                          |
|-------------------------------------------|-------------------------------|----------------------------------------------------------------------|
| **`ICONV_MIME_DECODE_STRICT`**            | <span class="type">int</span> | A bitmask used for <span class="function">iconv\_mime\_decode</span> |
| **`ICONV_MIME_DECODE_CONTINUE_ON_ERROR`** | <span class="type">int</span> | A bitmask used for <span class="function">iconv\_mime\_decode</span> |
