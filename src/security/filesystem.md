Filesystem Security
===================

**Table of Contents**

-   [Null bytes related issues](/security/filesystem/nullbytes.html)

PHP is subject to the security built into most server systems with
respect to permissions on a file and directory basis. This allows you to
control which files in the filesystem may be read. Care should be taken
with any files which are world readable to ensure that they are safe for
reading by all users who have access to that filesystem.

Since PHP was designed to allow user level access to the filesystem,
it's entirely possible to write a PHP script that will allow you to read
system files such as /etc/passwd, modify your ethernet connections, send
massive printer jobs out, etc. This has some obvious implications, in
that you need to ensure that the files that you read from and write to
are the appropriate ones.

Consider the following script, where a user indicates that they'd like
to delete a file in their home directory. This assumes a situation where
a PHP web interface is regularly used for file management, so the Apache
user is allowed to delete files in the user home directories.

**Example \#1 Poor variable checking leads to....**

``` php
<?php
// remove a file from the user's home directory
$username = $_POST['user_submitted_name'];
$userfile = $_POST['user_submitted_filename'];
$homedir  = "/home/$username";

unlink("$homedir/$userfile");

echo "The file has been deleted!";
?>
```

Since the username and the filename are postable from a user form, they
can submit a username and a filename belonging to someone else, and
delete it even if they're not supposed to be allowed to do so. In this
case, you'd want to use some other form of authentication. Consider what
could happen if the variables submitted were "../etc/" and "passwd". The
code would then effectively read:

**Example \#2 ... A filesystem attack**

``` php
<?php
// removes a file from anywhere on the hard drive that
// the PHP user has access to. If PHP has root access:
$username = $_POST['user_submitted_name']; // "../etc"
$userfile = $_POST['user_submitted_filename']; // "passwd"
$homedir  = "/home/$username"; // "/home/../etc"

unlink("$homedir/$userfile"); // "/home/../etc/passwd"

echo "The file has been deleted!";
?>
```

There are two important measures you should take to prevent these
issues.

-   <span class="simpara"> Only allow limited permissions to the PHP web
    user binary. </span>
-   <span class="simpara"> Check all variables which are submitted.
    </span>

Here is an improved script:

**Example \#3 More secure file name checking**

``` php
<?php
// removes a file from the hard drive that
// the PHP user has access to.
$username = $_SERVER['REMOTE_USER']; // using an authentication mechanism
$userfile = basename($_POST['user_submitted_filename']);
$homedir  = "/home/$username";

$filepath = "$homedir/$userfile";

if (file_exists($filepath) && unlink($filepath)) {
    $logstring = "Deleted $filepath\n";
} else {
    $logstring = "Failed to delete $filepath\n";
}
$fp = fopen("/home/logging/filedelete.log", "a");
fwrite($fp, $logstring);
fclose($fp);

echo htmlentities($logstring, ENT_QUOTES);

?>
```

However, even this is not without its flaws. If your authentication
system allowed users to create their own user logins, and a user chose
the login "../etc/", the system is once again exposed. For this reason,
you may prefer to write a more customized check:

**Example \#4 More secure file name checking**

``` php
<?php
$username     = $_SERVER['REMOTE_USER']; // using an authentication mechanisim
$userfile     = $_POST['user_submitted_filename'];
$homedir      = "/home/$username";

$filepath     = "$homedir/$userfile";

if (!ctype_alnum($username) || !preg_match('/^(?:[a-z0-9_-]|\.(?!\.))+$/iD', $userfile)) {
    die("Bad username/filename");
}

//etc...
?>
```

Depending on your operating system, there are a wide variety of files
which you should be concerned about, including device entries (/dev/ or
COM1), configuration files (/etc/ files and the .ini files), well known
file storage areas (/home/, My Documents), etc. For this reason, it's
usually easier to create a policy where you forbid everything except for
what you explicitly allow.
