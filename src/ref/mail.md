ezmlm\_hash
===========

Calculate the hash value needed by EZMLM

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">ezmlm\_hash</span> ( <span class="methodparam"><span
class="type">string</span> `$addr`</span> )

<span class="function">ezmlm\_hash</span> calculates the hash value
needed when keeping EZMLM mailing lists in a MySQL database.

### Parameters

`addr`  
The email address that's being hashed.

### Return Values

The hash value of `addr`.

### Examples

**Example \#1 Calculating the hash and subscribing a user**

``` php
<?php

$user = "joecool@example.com";
$hash = ezmlm_hash($user);
$query = sprintf("INSERT INTO sample VALUES (%s, '%s')", $hash, $user);
$db->query($query); // using PHPLIB db interface

?>
```

mail
====

Send mail

### Description

<span class="type">bool</span> <span class="methodname">mail</span> (
<span class="methodparam"><span class="type">string</span> `$to`</span>
, <span class="methodparam"><span class="type">string</span>
`$subject`</span> , <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$additional_headers`</span> \[, <span class="methodparam"><span
class="type">string</span> `$additional_parameters`</span> \]\] )

Sends an email.

### Parameters

`to`  
Receiver, or receivers of the mail.

The formatting of this string must comply with
<a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC 2822</a>.
Some examples are:

-   user@example.com
-   user@example.com, anotheruser@example.com
-   User \<user@example.com\>
-   User \<user@example.com\>, Another User \<anotheruser@example.com\>

`subject`  
Subject of the email to be sent.

**Caution**
Subject must satisfy
<a href="http://www.faqs.org/rfcs/rfc2047" class="link external">» RFC 2047</a>.

`message`  
Message to be sent.

Each line should be separated with a CRLF (\\r\\n). Lines should not be
larger than 70 characters.

**Caution**
(Windows only) When PHP is talking to a SMTP server directly, if a full
stop is found on the start of a line, it is removed. To counter-act
this, replace these occurrences with a double dot.

``` php
<?php
$text = str_replace("\n.", "\n..", $text);
?>
```

`additional_headers` (optional)  
<span class="type">String</span> or <span class="type">array</span> to
be inserted at the end of the email header.

This is typically used to add extra headers (From, Cc, and Bcc).
Multiple extra headers should be separated with a CRLF (\\r\\n). If
outside data are used to compose this header, the data should be
sanitized so that no unwanted headers could be injected.

If an <span class="type">array</span> is passed, its keys are the header
names and its values are the respective header values.

> **Note**:
>
> Before PHP 5.4.42 and 5.5.27, repectively, `additional_headers` did
> not have mail header injection protection. Therefore, users must make
> sure specified headers are safe and contains headers only. i.e. Never
> start mail body by putting multiple newlines.

> **Note**:
>
> When sending mail, the mail *must* contain a *From* header. This can
> be set with the `additional_headers` parameter, or a default can be
> set in `php.ini`.
>
> Failing to do this will result in an error message similar to
> *Warning: mail(): "sendmail\_from" not set in php.ini or custom
> "From:" header missing*. The *From* header sets also *Return-Path*
> under Windows.

> **Note**:
>
> If messages are not received, try using a LF (\\n) only. Some Unix
> mail transfer agents (most notably
> <a href="http://cr.yp.to/qmail.html" class="link external">» qmail</a>)
> replace LF by CRLF automatically (which leads to doubling CR if CRLF
> is used). This should be a last resort, as it does not comply with
> <a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC 2822</a>.

`additional_parameters` (optional)  
The `additional_parameters` parameter can be used to pass additional
flags as command line options to the program configured to be used when
sending mail, as defined by the *sendmail\_path* configuration setting.
For example, this can be used to set the envelope sender address when
using sendmail with the *-f* sendmail option.

This parameter is escaped by <span
class="function">escapeshellcmd</span> internally to prevent command
execution. <span class="function">escapeshellcmd</span> prevents command
execution, but allows to add additional parameters. For security
reasons, it is recommended for the user to sanitize this parameter to
avoid adding unwanted parameters to the shell command.

Since <span class="function">escapeshellcmd</span> is applied
automatically, some characters that are allowed as email addresses by
internet RFCs cannot be used. <span class="function">mail</span> can not
allow such characters, so in programs where the use of such characters
is required, alternative means of sending emails (such as using a
framework or a library) is recommended.

The user that the webserver runs as should be added as a trusted user to
the sendmail configuration to prevent a 'X-Warning' header from being
added to the message when the envelope sender (-f) is set using this
method. For sendmail users, this file is `/etc/mail/trusted-users`.

### Return Values

Returns **`TRUE`** if the mail was successfully accepted for delivery,
**`FALSE`** otherwise.

It is important to note that just because the mail was accepted for
delivery, it does NOT mean the mail will actually reach the intended
destination.

### Changelog

| Version        | Description                                                                                                                                             |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0          | The `additional_headers` parameter now also accepts an <span class="type">array</span>.                                                                 |
| 5.4.42, 5.5.27 | Header injection protection has been added for the `additional_headers` parameter. This means that multiple consecutive newlines are no longer allowed. |

### Examples

**Example \#1 Sending mail.**

Using <span class="function">mail</span> to send a simple email:

``` php
<?php
// The message
$message = "Line 1\r\nLine 2\r\nLine 3";

// In case any of our lines are larger than 70 characters, we should use wordwrap()
$message = wordwrap($message, 70, "\r\n");

// Send
mail('caffeinated@example.com', 'My Subject', $message);
?>
```

**Example \#2 Sending mail with extra headers.**

The addition of basic headers, telling the MUA the From and Reply-To
addresses:

``` php
<?php
$to      = 'nobody@example.com';
$subject = 'the subject';
$message = 'hello';
$headers = 'From: webmaster@example.com' . "\r\n" .
    'Reply-To: webmaster@example.com' . "\r\n" .
    'X-Mailer: PHP/' . phpversion();

mail($to, $subject, $message, $headers);
?>
```

**Example \#3 Sending mail with extra headers as <span
class="type">array</span>**

This example sends the same mail as the example immediately above, but
passes the additional headers as array (available as of PHP 7.2.0).

``` php
<?php
$to      = 'nobody@example.com';
$subject = 'the subject';
$message = 'hello';
$headers = array(
    'From' => 'webmaster@example.com',
    'Reply-To' => 'webmaster@example.com',
    'X-Mailer' => 'PHP/' . phpversion()
);

mail($to, $subject, $message, $headers);
?>
```

**Example \#4 Sending mail with an additional command line parameter.**

The `additional_parameters` parameter can be used to pass an additional
parameter to the program configured to use when sending mail using the
*sendmail\_path*.

``` php
<?php
mail('nobody@example.com', 'the subject', 'the message', null,
   '-fwebmaster@example.com');
?>
```

**Example \#5 Sending HTML email**

It is also possible to send HTML email with <span
class="function">mail</span>.

``` php
<?php
// Multiple recipients
$to = 'johny@example.com, sally@example.com'; // note the comma

// Subject
$subject = 'Birthday Reminders for August';

// Message
$message = '
<html>
<head>
  <title>Birthday Reminders for August</title>
</head>
<body>
  <p>Here are the birthdays upcoming in August!</p>
  <table>
    <tr>
      <th>Person</th><th>Day</th><th>Month</th><th>Year</th>
    </tr>
    <tr>
      <td>Johny</td><td>10th</td><td>August</td><td>1970</td>
    </tr>
    <tr>
      <td>Sally</td><td>17th</td><td>August</td><td>1973</td>
    </tr>
  </table>
</body>
</html>
';

// To send HTML mail, the Content-type header must be set
$headers[] = 'MIME-Version: 1.0';
$headers[] = 'Content-type: text/html; charset=iso-8859-1';

// Additional headers
$headers[] = 'To: Mary <mary@example.com>, Kelly <kelly@example.com>';
$headers[] = 'From: Birthday Reminder <birthday@example.com>';
$headers[] = 'Cc: birthdayarchive@example.com';
$headers[] = 'Bcc: birthdaycheck@example.com';

// Mail it
mail($to, $subject, $message, implode("\r\n", $headers));
?>
```

> **Note**:
>
> If intending to send HTML or otherwise Complex mails, it is
> recommended to use the PEAR package
> <a href="https://pear.php.net/package/Mail_Mime" class="link external">» PEAR::Mail_Mime</a>.

### Notes

> **Note**:
>
> The Windows implementation of <span class="function">mail</span>
> differs in many ways from the Unix implementation. First, it doesn't
> use a local binary for composing messages but only operates on direct
> sockets which means a *MTA* is needed listening on a network socket
> (which can either on the localhost or a remote machine).
>
> Second, the custom headers like *From:*, *Cc:*, *Bcc:* and *Date:* are
> *not* interpreted by the *MTA* in the first place, but are parsed by
> PHP.
>
> As such, the `to` parameter should not be an address in the form of
> "Something \<someone@example.com\>". The mail command may not parse
> this properly while talking with the MTA.

> **Note**:
>
> It is worth noting that the <span class="function">mail</span>
> function is not suitable for larger volumes of email in a loop. This
> function opens and closes an SMTP socket for each email, which is not
> very efficient.
>
> For the sending of large amounts of email, see the
> <a href="https://pear.php.net/package/Mail" class="link external">» PEAR::Mail</a>,
> and
> <a href="https://pear.php.net/package/Mail_Queue" class="link external">» PEAR::Mail_Queue</a>
> packages.

> **Note**:
>
> The following RFCs may be useful:
> <a href="http://www.faqs.org/rfcs/rfc1896" class="link external">» RFC 1896</a>,
> <a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC 2045</a>,
> <a href="http://www.faqs.org/rfcs/rfc2046" class="link external">» RFC 2046</a>,
> <a href="http://www.faqs.org/rfcs/rfc2047" class="link external">» RFC 2047</a>,
> <a href="http://www.faqs.org/rfcs/rfc2048" class="link external">» RFC 2048</a>,
> <a href="http://www.faqs.org/rfcs/rfc2049" class="link external">» RFC 2049</a>,
> and
> <a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC 2822</a>.

### See Also

-   <span class="function">mb\_send\_mail</span>
-   <span class="function">imap\_mail</span>
-   <a href="https://pear.php.net/package/Mail" class="link external">» PEAR::Mail</a>
-   <a href="https://pear.php.net/package/Mail_Mime" class="link external">» PEAR::Mail_Mime</a>

**Table of Contents**

-   [ezmlm\_hash](/ref/mail.html#ezmlm_hash) — Calculate the hash value
    needed by EZMLM
-   [mail](/ref/mail.html#mail) — Send mail
