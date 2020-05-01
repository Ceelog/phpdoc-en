HTTP authentication with PHP
============================

It is possible to use the <span class="function">header</span> function
to send an *"Authentication Required"* message to the client browser
causing it to pop up a Username/Password input window. Once the user has
filled in a username and a password, the URL containing the PHP script
will be called again with the
<a href="/reserved/variables.html" class="link">predefined variables</a>
`PHP_AUTH_USER`, `PHP_AUTH_PW`, and `AUTH_TYPE` set to the user name,
password and authentication type respectively. These predefined
variables are found in the `$_SERVER` array. Both "Basic" and "Digest"
(since PHP 5.1.0) authentication methods are supported. See the <span
class="function">header</span> function for more information.

An example script fragment which would force client authentication on a
page is as follows:

**Example \#1 Basic HTTP Authentication example**

``` php
<?php
if (!isset($_SERVER['PHP_AUTH_USER'])) {
    header('WWW-Authenticate: Basic realm="My Realm"');
    header('HTTP/1.0 401 Unauthorized');
    echo 'Text to send if user hits Cancel button';
    exit;
} else {
    echo "<p>Hello {$_SERVER['PHP_AUTH_USER']}.</p>";
    echo "<p>You entered {$_SERVER['PHP_AUTH_PW']} as your password.</p>";
}
?>
```

**Example \#2 Digest HTTP Authentication example**

This example shows you how to implement a simple Digest HTTP
authentication script. For more information read the
<a href="http://www.faqs.org/rfcs/rfc2617" class="link external">» RFC 2617</a>.

``` php
<?php
$realm = 'Restricted area';

//user => password
$users = array('admin' => 'mypass', 'guest' => 'guest');


if (empty($_SERVER['PHP_AUTH_DIGEST'])) {
    header('HTTP/1.1 401 Unauthorized');
    header('WWW-Authenticate: Digest realm="'.$realm.
           '",qop="auth",nonce="'.uniqid().'",opaque="'.md5($realm).'"');

    die('Text to send if user hits Cancel button');
}


// analyze the PHP_AUTH_DIGEST variable
if (!($data = http_digest_parse($_SERVER['PHP_AUTH_DIGEST'])) ||
    !isset($users[$data['username']]))
    die('Wrong Credentials!');


// generate the valid response
$A1 = md5($data['username'] . ':' . $realm . ':' . $users[$data['username']]);
$A2 = md5($_SERVER['REQUEST_METHOD'].':'.$data['uri']);
$valid_response = md5($A1.':'.$data['nonce'].':'.$data['nc'].':'.$data['cnonce'].':'.$data['qop'].':'.$A2);

if ($data['response'] != $valid_response)
    die('Wrong Credentials!');

// ok, valid username & password
echo 'You are logged in as: ' . $data['username'];


// function to parse the http auth header
function http_digest_parse($txt)
{
    // protect against missing data
    $needed_parts = array('nonce'=>1, 'nc'=>1, 'cnonce'=>1, 'qop'=>1, 'username'=>1, 'uri'=>1, 'response'=>1);
    $data = array();
    $keys = implode('|', array_keys($needed_parts));

    preg_match_all('@(' . $keys . ')=(?:([\'"])([^\2]+?)\2|([^\s,]+))@', $txt, $matches, PREG_SET_ORDER);

    foreach ($matches as $m) {
        $data[$m[1]] = $m[3] ? $m[3] : $m[4];
        unset($needed_parts[$m[1]]);
    }

    return $needed_parts ? false : $data;
}
?>
```

> **Note**: **Compatibility Note**  
>
> Please be careful when coding the HTTP header lines. In order to
> guarantee maximum compatibility with all clients, the keyword "Basic"
> should be written with an uppercase "B", the realm string must be
> enclosed in double (not single) quotes, and exactly one space should
> precede the *401* code in the *HTTP/1.0 401* header line.
> Authentication parameters have to be comma-separated as seen in the
> digest example above.

Instead of simply printing out `PHP_AUTH_USER` and `PHP_AUTH_PW`, as
done in the above example, you may want to check the username and
password for validity. Perhaps by sending a query to a database, or by
looking up the user in a dbm file.

Watch out for buggy Internet Explorer browsers out there. They seem very
picky about the order of the headers. Sending the *WWW-Authenticate*
header before the *HTTP/1.0 401* header seems to do the trick for now.

In order to prevent someone from writing a script which reveals the
password for a page that was authenticated through a traditional
external mechanism, the PHP\_AUTH variables will not be set if external
authentication is enabled for that particular page and
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
is enabled. Regardless, `REMOTE_USER` can be used to identify the
externally-authenticated user. So, you can use
`$_SERVER['REMOTE_USER']`.

> **Note**: **Configuration Note**  
>
> PHP uses the presence of an *AuthType* directive to determine whether
> external authentication is in effect.

Note, however, that the above does not prevent someone who controls a
non-authenticated URL from stealing passwords from authenticated URLs on
the same server.

Both Netscape Navigator and Internet Explorer will clear the local
browser window's authentication cache for the realm upon receiving a
server response of 401. This can effectively "log out" a user, forcing
them to re-enter their username and password. Some people use this to
"time out" logins, or provide a "log-out" button.

**Example \#3 HTTP Authentication example forcing a new name/password**

``` php
<?php
function authenticate() {
    header('WWW-Authenticate: Basic realm="Test Authentication System"');
    header('HTTP/1.0 401 Unauthorized');
    echo "You must enter a valid login ID and password to access this resource\n";
    exit;
}
 
if (!isset($_SERVER['PHP_AUTH_USER']) ||
    ($_POST['SeenBefore'] == 1 && $_POST['OldAuth'] == $_SERVER['PHP_AUTH_USER'])) {
    authenticate();
} else {
    echo "<p>Welcome: " . htmlspecialchars($_SERVER['PHP_AUTH_USER']) . "<br />";
    echo "Old: " . htmlspecialchars($_REQUEST['OldAuth']);
    echo "<form action='' method='post'>\n";
    echo "<input type='hidden' name='SeenBefore' value='1' />\n";
    echo "<input type='hidden' name='OldAuth' value=\"" . htmlspecialchars($_SERVER['PHP_AUTH_USER']) . "\" />\n";
    echo "<input type='submit' value='Re Authenticate' />\n";
    echo "</form></p>\n";
}
?>
```

This behavior is not required by the *HTTP Basic* authentication
standard, so you should never depend on this. Testing with *Lynx* has
shown that *Lynx* does not clear the authentication credentials with a
401 server response, so pressing back and then forward again will open
the resource as long as the credential requirements haven't changed. The
user can press the *'\_'* key to clear their authentication information,
however.

In order to get HTTP Authentication to work using IIS server with the
CGI version of PHP you must edit your IIS configuration "*Directory
Security*". Click on "*Edit*" and only check "*Anonymous Access*", all
other fields should be left unchecked.

> **Note**: **IIS Note:**  
> <span class="simpara"> For HTTP Authentication to work with IIS, the
> PHP directive
> <a href="/ini/core.html#ini.cgi.rfc2616-headers" class="link">cgi.rfc2616_headers</a>
> must be set to *0* (the default value). </span>

> **Note**:
>
> If
> <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
> is enabled, the uid of the script is added to the *realm* part of the
> *WWW-Authenticate* header.
