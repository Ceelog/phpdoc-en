Sorting Arrays
==============

PHP has several functions that deal with sorting arrays, and this
document exists to help sort it all out.

The main differences are:

-   Some sort based on the <span class="type">array</span> keys, whereas
    others by the values: *$array\['key'\] = 'value';*
-   Whether or not the correlation between the keys and values are
    maintained after the sort, which may mean the keys are reset
    numerically (0,1,2 ...)
-   The order of the sort: alphabetical, low to high (ascending), high
    to low (descending), numerical, natural, random, or user defined
-   Note: All of these sort functions act directly on the array variable
    itself, as opposed to returning a new sorted array
-   If any of these sort functions evaluates two members as equal then
    the order is undefined (the sorting is not stable).

| Function name                                  | Sorts by | Maintains key association   | Order of sort               | Related functions                         |
|------------------------------------------------|----------|-----------------------------|-----------------------------|-------------------------------------------|
| <span class="function">array\_multisort</span> | value    | associative yes, numeric no | first array or sort options | <span class="function">array\_walk</span> |
| <span class="function">asort</span>            | value    | yes                         | low to high                 | <span class="function">arsort</span>      |
| <span class="function">arsort</span>           | value    | yes                         | high to low                 | <span class="function">asort</span>       |
| <span class="function">krsort</span>           | key      | yes                         | high to low                 | <span class="function">ksort</span>       |
| <span class="function">ksort</span>            | key      | yes                         | low to high                 | <span class="function">asort</span>       |
| <span class="function">natcasesort</span>      | value    | yes                         | natural, case insensitive   | <span class="function">natsort</span>     |
| <span class="function">natsort</span>          | value    | yes                         | natural                     | <span class="function">natcasesort</span> |
| <span class="function">rsort</span>            | value    | no                          | high to low                 | <span class="function">sort</span>        |
| <span class="function">shuffle</span>          | value    | no                          | random                      | <span class="function">array\_rand</span> |
| <span class="function">sort</span>             | value    | no                          | low to high                 | <span class="function">rsort</span>       |
| <span class="function">uasort</span>           | value    | yes                         | user defined                | <span class="function">uksort</span>      |
| <span class="function">uksort</span>           | key      | yes                         | user defined                | <span class="function">uasort</span>      |
| <span class="function">usort</span>            | value    | no                          | user defined                | <span class="function">uasort</span>      |
