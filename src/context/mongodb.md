MongoDB context options
=======================

MongoDB context option listing

### Description

Context options for *mongodb://* transports.

### Options

`log_cmd_insert` <span class="type">callable</span>  
A callback function called when inserting a document, see <span
class="function">log\_cmd\_insert</span>.

`log_cmd_delete` <span class="type">callable</span>  
A callback function called when deleting a document, see <span
class="function">log\_cmd\_delete</span>.

`log_cmd_update` <span class="type">callable</span>  
A callback function called when updating a document, see <span
class="function">log\_cmd\_update</span>.

`log_write_batch` <span class="type">callable</span>  
A callback function called when executing a Write Batch, see <span
class="function">log\_write\_batch</span>.

`log_reply` <span class="type">callable</span>  
A callback function called when reading a reply from MongoDB, see <span
class="function">log\_reply</span>.

`log_getmore` <span class="type">callable</span>  
A callback function called when retrieving more results from a MongoDB
cursor, see <span class="function">log\_getmore</span>.

`log_killcursor` <span class="type">callable</span>  
A callback function called executing a killcursor opcode, see <span
class="function">log\_killcursor</span>.

### Changelog

| Version          | Description                     |
|------------------|---------------------------------|
| pecl/mongo 1.5.0 | Added Write API Context options |

### See Also

-   <a href="/context/socket.html" class="xref">Socket context options</a>
-   <a href="/context/ssl.html" class="xref">SSL context options</a>
