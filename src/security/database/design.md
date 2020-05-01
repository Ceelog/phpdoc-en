Designing Databases
-------------------

The first step is always to create the database, unless you want to use
one from a third party. When a database is created, it is assigned to an
owner, who executed the creation statement. Usually, only the owner (or
a superuser) can do anything with the objects in that database, and in
order to allow other users to use it, privileges must be granted.

Applications should never connect to the database as its owner or a
superuser, because these users can execute any query at will, for
example, modifying the schema (e.g. dropping tables) or deleting its
entire content.

You may create different database users for every aspect of your
application with very limited rights to database objects. The most
required privileges should be granted only, and avoid that the same user
can interact with the database in different use cases. This means that
if intruders gain access to your database using your applications
credentials, they can only effect as many changes as your application
can.
