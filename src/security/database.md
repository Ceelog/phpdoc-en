Database Security
=================

**Table of Contents**

-   [Designing Databases](/security/database/design.html)
-   [Connecting to Database](/security/database/connection.html)
-   [Encrypted Storage Model](/security/database/storage.html)
-   [SQL Injection](/security/database/sql-injection.html)

Nowadays, databases are cardinal components of any web based application
by enabling websites to provide varying dynamic content. Since very
sensitive or secret information can be stored in a database, you should
strongly consider protecting your databases.

To retrieve or to store any information you need to connect to the
database, send a legitimate query, fetch the result, and close the
connection. Nowadays, the commonly used query language in this
interaction is the Structured Query Language (SQL). See how an attacker
can
<a href="/security/database/sql-injection.html" class="link">tamper with an SQL query</a>.

As you can surmise, PHP cannot protect your database by itself. The
following sections aim to be an introduction into the very basics of how
to access and manipulate databases within PHP scripts.

Keep in mind this simple rule: defense in depth. The more places you
take action to increase the protection of your database, the less
probability of an attacker succeeding in exposing or abusing any stored
information. Good design of the database schema and the application
deals with your greatest fears.
