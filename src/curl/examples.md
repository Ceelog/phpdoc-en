Examples
========

**Table of Contents**

-   [Basic curl example](/curl/examples.html#Basic%20curl%20example)

Basic curl example
------------------

Once you've compiled PHP with cURL support, you can begin using the cURL
functions. The basic idea behind the cURL functions is that you
initialize a cURL session using the <span
class="function">curl\_init</span>, then you can set all your options
for the transfer via the <span class="function">curl\_setopt</span>,
then you can execute the session with the <span
class="function">curl\_exec</span> and then you finish off your session
using the <span class="function">curl\_close</span>. Here is an example
that uses the cURL functions to fetch the example.com homepage into a
file:

**Example \#1 Using PHP's cURL module to fetch the example.com
homepage**

``` php
<?php

$ch = curl_init("http://www.example.com/");
$fp = fopen("example_homepage.txt", "w");

curl_setopt($ch, CURLOPT_FILE, $fp);
curl_setopt($ch, CURLOPT_HEADER, 0);

curl_exec($ch);
if(curl_error($ch)) {
    fwrite($fp, curl_error($ch));
}
curl_close($ch);
fclose($fp);
?>
```
