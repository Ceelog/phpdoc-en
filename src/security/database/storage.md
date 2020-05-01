Encrypted Storage Model
-----------------------

SSL/SSH protects data travelling from the client to the server: SSL/SSH
does not protect persistent data stored in a database. SSL is an
on-the-wire protocol.

Once an attacker gains access to your database directly (bypassing the
webserver), stored sensitive data may be exposed or misused, unless the
information is protected by the database itself. Encrypting the data is
a good way to mitigate this threat, but very few databases offer this
type of data encryption.

The easiest way to work around this problem is to first create your own
encryption package, and then use it from within your PHP scripts. PHP
can assist you in this with several extensions, such as
<a href="/ref/mcrypt.html" class="link">Mcrypt</a> and
<a href="/ref/mhash.html" class="link">Mhash</a>, covering a wide
variety of encryption algorithms. The script encrypts the data before
inserting it into the database, and decrypts it when retrieving. See the
references for further examples of how encryption works.

### Hashing

In the case of truly hidden data, if its raw representation is not
needed (i.e. will not be displayed), hashing should be taken into
consideration. The well-known example for hashing is storing the
cryptographic hash of a password in a database, instead of the password
itself.

In PHP 5.5 or newer
<a href="/ref/password.html" class="link">password</a> functions provide
a convenient way to hash sensitive data and work with these hashes. In
PHP 5.3.7+
<a href="https://github.com/ircmaxell/password_compat" class="link external">»  password_compat</a>
library can also be used.

<span class="function">password\_hash</span> is used to hash a given
string using the strongest algorithm currently available and <span
class="function">password\_verify</span> checks whether the given
password matches the hash stored in database.

**Example \#1 Hashing password field**

``` php
<?php

// storing password hash
$query  = sprintf("INSERT INTO users(name,pwd) VALUES('%s','%s');",
            pg_escape_string($username),
            password_hash($password, PASSWORD_DEFAULT));
$result = pg_query($connection, $query);

// querying if user submitted the right password
$query = sprintf("SELECT pwd FROM users WHERE name='%s';",
            pg_escape_string($username));
$row = pg_fetch_assoc(pg_query($connection, $query));

if ($row && password_verify($password, $row['pwd'])) {
    echo 'Welcome, ' . htmlspecialchars($username) . '!';
} else {
    echo 'Authentication failed for ' . htmlspecialchars($username) . '.';
}

?>
```

In older versions of PHP this can be achieved using <span
class="function">crypt</span> function.

**Example \#2 Hashing password using <span
class="function">crypt</span>s**

``` php
<?php

// storing password hash
// $random_chars retrieved e.g. using /dev/random
$query  = sprintf("INSERT INTO users(name,pwd) VALUES('%s','%s');",
            pg_escape_string($username),
            pg_escape_string(crypt($password, '$2a$07$' . $random_chars . '$')));
$result = pg_query($connection, $query);

// querying if user submitted the right password
$query = sprintf("SELECT pwd FROM users WHERE name='%s';",
            pg_escape_string($username));
$row = pg_fetch_assoc(pg_query($connection, $query));

if ($row && crypt($password, $row['pwd']) == $row['pwd']) {
    echo 'Welcome, ' . htmlspecialchars($username) . '!';
} else {
    echo 'Authentication failed for ' . htmlspecialchars($username) . '.';
}

?>
```
