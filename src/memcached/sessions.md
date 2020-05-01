Sessions support
================

Memcached provides a custom session handler that can be used to store
user sessions in memcache. A completely separate memcached instance is
used for that internally, so you can use a different server pool if
necessary. The session keys are stored under the prefix
*memc.sess.key.*, so be aware of this if you use the same server pool
for sessions and generic caching.

`session.save_handler` <span class="type">string</span>  
Set to *memcached* to enable sessions support.

`session.save_path` <span class="type">string</span>  
Defines a comma separated of *hostname:port* entries to use for session
server pool, for example *"sess1:11211, sess2:11211"*.
