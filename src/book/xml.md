XML Parser
==========

**Table of Contents**

-   [Introduction](/intro/xml.html)
-   [Installing/Configuring](/xml/setup.html)
    -   [Requirements](/xml/setup.html#Requirements)
    -   [Installation](/xml/setup.html#Installation)
    -   [Runtime Configuration](/xml/setup.html#Runtime%20Configuration)
    -   [Resource Types](/xml/setup.html#Resource%20Types)
-   [Predefined Constants](/xml/constants.html)
-   [Event Handlers](/xml/eventhandlers.html)
-   [Case Folding](/xml/case-folding.html)
-   [Error Codes](/xml/error-codes.html)
-   [Character Encoding](/xml/encoding.html)
-   [Examples](/xml/examples.html)
    -   [XML Element Structure
        Example](/xml/examples.html#XML%20Element%20Structure%20Example)
    -   [XML Tag Mapping
        Example](/xml/examples.html#XML%20Tag%20Mapping%20Example)
    -   [XML External Entity
        Example](/xml/examples.html#XML%20External%20Entity%20Example)
-   [XML Parser Functions](/ref/xml.html)
    -   [utf8\_decode](/ref/xml.html#utf8_decode) — Converts a string
        with ISO-8859-1 characters encoded with UTF-8 to single-byte
        ISO-8859-1
    -   [utf8\_encode](/ref/xml.html#utf8_encode) — Encodes an
        ISO-8859-1 string to UTF-8
    -   [xml\_error\_string](/ref/xml.html#xml_error_string) — Get XML
        parser error string
    -   [xml\_get\_current\_byte\_index](/ref/xml.html#xml_get_current_byte_index)
        — Get current byte index for an XML parser
    -   [xml\_get\_current\_column\_number](/ref/xml.html#xml_get_current_column_number)
        — Get current column number for an XML parser
    -   [xml\_get\_current\_line\_number](/ref/xml.html#xml_get_current_line_number)
        — Get current line number for an XML parser
    -   [xml\_get\_error\_code](/ref/xml.html#xml_get_error_code) — Get
        XML parser error code
    -   [xml\_parse\_into\_struct](/ref/xml.html#xml_parse_into_struct)
        — Parse XML data into an array structure
    -   [xml\_parse](/ref/xml.html#xml_parse) — Start parsing an XML
        document
    -   [xml\_parser\_create\_ns](/ref/xml.html#xml_parser_create_ns) —
        Create an XML parser with namespace support
    -   [xml\_parser\_create](/ref/xml.html#xml_parser_create) — Create
        an XML parser
    -   [xml\_parser\_free](/ref/xml.html#xml_parser_free) — Free an XML
        parser
    -   [xml\_parser\_get\_option](/ref/xml.html#xml_parser_get_option)
        — Get options from an XML parser
    -   [xml\_parser\_set\_option](/ref/xml.html#xml_parser_set_option)
        — Set options in an XML parser
    -   [xml\_set\_character\_data\_handler](/ref/xml.html#xml_set_character_data_handler)
        — Set up character data handler
    -   [xml\_set\_default\_handler](/ref/xml.html#xml_set_default_handler)
        — Set up default handler
    -   [xml\_set\_element\_handler](/ref/xml.html#xml_set_element_handler)
        — Set up start and end element handlers
    -   [xml\_set\_end\_namespace\_decl\_handler](/ref/xml.html#xml_set_end_namespace_decl_handler)
        — Set up end namespace declaration handler
    -   [xml\_set\_external\_entity\_ref\_handler](/ref/xml.html#xml_set_external_entity_ref_handler)
        — Set up external entity reference handler
    -   [xml\_set\_notation\_decl\_handler](/ref/xml.html#xml_set_notation_decl_handler)
        — Set up notation declaration handler
    -   [xml\_set\_object](/ref/xml.html#xml_set_object) — Use XML
        Parser within an object
    -   [xml\_set\_processing\_instruction\_handler](/ref/xml.html#xml_set_processing_instruction_handler)
        — Set up processing instruction (PI) handler
    -   [xml\_set\_start\_namespace\_decl\_handler](/ref/xml.html#xml_set_start_namespace_decl_handler)
        — Set up start namespace declaration handler
    -   [xml\_set\_unparsed\_entity\_decl\_handler](/ref/xml.html#xml_set_unparsed_entity_decl_handler)
        — Set up unparsed entity declaration handler
