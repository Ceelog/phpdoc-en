Other Changes
-------------

### Loosening Reserved Word Restrictions

Globally reserved words as property, constant, and method names within
classes, interfaces, and traits are now allowed. This reduces the
surface of BC breaks when new keywords are introduced and avoids naming
restrictions on APIs.

This is particularly useful when creating internal DSLs with fluent
interfaces:

``` php
<?php
// 'new', 'private', and 'for' were previously unusable
Project::new('Project Name')->private()->for('purpose here')->with('username here');
?>
```

The only limitation is that the *class* keyword still cannot be used as
a constant name, otherwise it would conflict with the class name
resolution syntax (*ClassName::class*).

### Removal of date.timezone Warning

Previously, a warning was emitted if the `date.timezone` INI setting had
not been set prior to using any date- or time-based functions. Now, this
warning has been removed (with `date.timezone` still defaulting to UTC).
