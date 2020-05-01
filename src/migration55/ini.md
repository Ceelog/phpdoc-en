Changes to INI file handling
----------------------------

### <a href="/book/intl.html" class="link">Intl</a>

The *intl.use\_exceptions* configuration directive has been added, which
controls the behaviour of intl when global errors occur in conjunction
with the already extant *intl.error\_level* configuration directive.

### <a href="/set/mysqlinfo.html#Mysqlnd" class="link">MySQLnd</a>

The
<a href="/set/mysqlinfo.html#" class="link">mysqlnd.sha256_server_public_key</a>
configuration directive has been added to allow
<a href="/set/mysqlinfo.html#MySQLi" class="link">mysqli</a> to use the
new MySQL authentication protocol.
