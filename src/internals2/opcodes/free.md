FREE
----

PHP code
--------

``` php
<?php
/*
 * Release the allocated space of the value.
 * opcode number: 70
 */
 print "Hello World";
?>
```

PHP opcodes
-----------

Function name: (null)

Compiled variables: none

| line | \#  | op     | fetch | ext | return | operands      |
|------|-----|--------|-------|-----|--------|---------------|
| 6    | 0   | PRINT  |       |     | \~0    | 'Hello+World' |
|      | 1   | FREE   |       |     |        | \~0           |
| 7    | 2   | RETURN |       |     |        | 1             |
