include\_once
-------------

The *include\_once* statement includes and evaluates the specified file
during the execution of the script. This is a behavior similar to the
<span class="function">include</span> statement, with the only
difference being that if the code from a file has already been included,
it will not be included again, and include\_once returns **`true`**. As
the name suggests, the file will be included just once.

*include\_once* may be used in cases where the same file might be
included and evaluated more than once during a particular execution of a
script, so in this case it may help avoid problems such as function
redefinitions, variable value reassignments, etc.

See the <span class="function">include</span> documentation for
information about how this function works.
