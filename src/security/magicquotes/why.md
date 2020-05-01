Why did we use Magic Quotes
---------------------------

**Warning**

This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

-   <span class="simpara"> There is no reason to use magic quotes
    because they are no longer a supported part of PHP. However, they
    did exist and did help a few beginners blissfully and unknowingly
    write better (more secure) code. But, when dealing with code that
    relies upon this behavior it's better to update the code instead of
    turning magic quotes on. </span> <span class="simpara"> So why did
    this feature exist? Simple, to help prevent
    <a href="/security/database/sql-injection.html" class="link">SQL Injection</a>.
    Today developers are better aware of security and end up using
    database specific escaping mechanisms and/or prepared statements
    instead of relying upon features like magical quotes. </span>
