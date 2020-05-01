PHP comes with a complete reflection API that adds the ability to
introspect classes, interfaces, functions, methods and extensions.
Additionally, the reflection API offers ways to retrieve doc comments
for functions, classes and methods.

Please note that certain parts of the internal API are missing the
necessary code to work with the Reflection extension. E.g., an internal
PHP class might be missing reflection data for properties. These few
cases are considered bugs, however, so they should be discovered and
fixed.
