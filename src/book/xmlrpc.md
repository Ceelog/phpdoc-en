XML-RPC
=======

**Table of Contents**

-   [Introduction](/intro/xmlrpc.html)
-   [Installing/Configuring](/xmlrpc/setup.html)
    -   [Requirements](/xmlrpc/setup.html#Requirements)
    -   [Installation](/xmlrpc/setup.html#Installation)
    -   [Runtime
        Configuration](/xmlrpc/setup.html#Runtime%20Configuration)
    -   [Resource Types](/xmlrpc/setup.html#Resource%20Types)
-   [Predefined Constants](/xmlrpc/constants.html)
-   [XML-RPC Functions](/ref/xmlrpc.html)
    -   [xmlrpc\_decode\_request](/ref/xmlrpc.html#xmlrpc_decode_request)
        — Decodes XML into native PHP types
    -   [xmlrpc\_decode](/ref/xmlrpc.html#xmlrpc_decode) — Decodes XML
        into native PHP types
    -   [xmlrpc\_encode\_request](/ref/xmlrpc.html#xmlrpc_encode_request)
        — Generates XML for a method request
    -   [xmlrpc\_encode](/ref/xmlrpc.html#xmlrpc_encode) — Generates XML
        for a PHP value
    -   [xmlrpc\_get\_type](/ref/xmlrpc.html#xmlrpc_get_type) — Gets
        xmlrpc type for a PHP value
    -   [xmlrpc\_is\_fault](/ref/xmlrpc.html#xmlrpc_is_fault) —
        Determines if an array value represents an XMLRPC fault
    -   [xmlrpc\_parse\_method\_descriptions](/ref/xmlrpc.html#xmlrpc_parse_method_descriptions)
        — Decodes XML into a list of method descriptions
    -   [xmlrpc\_server\_add\_introspection\_data](/ref/xmlrpc.html#xmlrpc_server_add_introspection_data)
        — Adds introspection documentation
    -   [xmlrpc\_server\_call\_method](/ref/xmlrpc.html#xmlrpc_server_call_method)
        — Parses XML requests and call methods
    -   [xmlrpc\_server\_create](/ref/xmlrpc.html#xmlrpc_server_create)
        — Creates an xmlrpc server
    -   [xmlrpc\_server\_destroy](/ref/xmlrpc.html#xmlrpc_server_destroy)
        — Destroys server resources
    -   [xmlrpc\_server\_register\_introspection\_callback](/ref/xmlrpc.html#xmlrpc_server_register_introspection_callback)
        — Register a PHP function to generate documentation
    -   [xmlrpc\_server\_register\_method](/ref/xmlrpc.html#xmlrpc_server_register_method)
        — Register a PHP function to resource method matching
        method\_name
    -   [xmlrpc\_set\_type](/ref/xmlrpc.html#xmlrpc_set_type) — Sets
        xmlrpc type, base64 or datetime, for a PHP string value
