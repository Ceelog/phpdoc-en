Expiration Times
================

Some storage commands involve sending an expiration value (relative to
an item or to an operation requested by the client) to the server. In
all such cases, the actual value sent may either be Unix time (number of
seconds since January 1, 1970, as an integer), or a number of seconds
starting from current time. In the latter case, this number of seconds
may not exceed 60\*60\*24\*30 (number of seconds in 30 days); if the
expiration value is larger than that, the server will consider it to be
real Unix time value rather than an offset from current time.

If the expiration value is *0* (the default), the item never expires
(although it may be deleted from the server to make place for other
items).
