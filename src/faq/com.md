PHP and COM
===========

PHP can be used to access COM and DCOM objects on Win32 platforms.

1.  [I have built a DLL to calculate something. Is there any way to run
    this DLL under PHP ?](#faq.com.q1)
2.  [What does 'Unsupported variant type: xxxx (0xxxxx)' mean
    ?](#faq.com.q2)
3.  [Is it possible manipulate visual objects in PHP ?](#faq.com.q3)
4.  [Can I store a COM object in a session ?](#faq.com.q4)
5.  [How can I trap COM errors?](#faq.com.q5)
6.  [Can I generate DLL files from PHP scripts like I can in Perl
    ?](#faq.com.q6)
7.  [What does 'Unable to obtain IDispatch interface for CLSID
    {xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}' mean ?](#faq.com.q7)
8.  [How can I run COM object from remote server ?](#faq.com.q8)
9.  [I get 'DCOM is disabled in C:\\path...\\scriptname.php on line 6',
    what can I do ?](#faq.com.q9)
10. [Is it possible to load/manipulate an ActiveX object in a page with
    PHP ?](#faq.com.q10)
11. [Is it possible to get a running instance of a component
    ?](#faq.com.q11)
12. [Is there a way to handle an event sent from COM object
    ?](#faq.com.q12)
13. [I'm having problems when trying to invoke a method of a COM object
    which exposes more than one interface. What can I do
    ?](#faq.com.q13)
14. [So PHP works with COM, how about COM+ ?](#faq.com.q14)
15. [If PHP can manipulate COM objects, can we imagine to use MTS to
    manage components resources, in conjunction with PHP
    ?](#faq.com.q15)

**I have built a DLL to calculate something. Is there any way to run this DLL under PHP ?**  
If this is a simple DLL there is no way yet to run it from PHP. If the
DLL contains a COM server you may be able to access it if it implements
the IDispatch interface.

<!-- -->

**What does 'Unsupported variant type: xxxx (0xxxxx)' mean ?**  
There are dozens of VARIANT types and combinations of them. Most of them
are already supported but a few still have to be implemented. Arrays are
not completely supported. Only single dimensional indexed only arrays
can be passed between PHP and COM. If you find other types that aren't
supported, please report them as a bug (if not already reported) and
provide as much information as available.

<!-- -->

**Is it possible manipulate visual objects in PHP ?**  
Generally it is, but as PHP is mostly used as a web scripting language
it runs in the web servers context, thus visual objects will never
appear on the servers desktop. If you use PHP for application scripting
e.g. in conjunction with PHP-GTK there is no limitation in accessing and
manipulating visual objects through COM.

<!-- -->

**Can I store a COM object in a session ?**  
No, you can't. COM instances are treated as resources and therefore they
are only available in a single script's context.

<!-- -->

**How can I trap COM errors?**  
The COM extension throws *com\_exception* exceptions, which you can
catch and then inspect the *code* member to determine what to do next.

<!-- -->

**Can I generate DLL files from PHP scripts like I can in Perl ?**  
No, unfortunately there is no such tool available for PHP.

<!-- -->

**What does 'Unable to obtain IDispatch interface for CLSID {xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}' mean ?**  
This error can have multiple reasons:

-   <span class="simpara"> the CLSID is wrong </span>
-   <span class="simpara"> the requested DLL is missing </span>
-   <span class="simpara"> the requested component doesn't implement the
    IDispatch interface </span>

<!-- -->

**How can I run COM object from remote server ?**  
Exactly like you run local objects. You only have to pass the IP of the
remote machine as second parameter to the COM constructor.

Make sure that you have set
<a href="/com/setup.html#" class="link">com.allow_dcom</a>*=***`true`**
in your `php.ini`.

<!-- -->

**I get 'DCOM is disabled in C:\\path...\\scriptname.php on line 6', what can I do ?**  
Edit your `php.ini` and set
<a href="/com/setup.html#" class="link">com.allow_dcom</a>*=***`true`**.

<!-- -->

**Is it possible to load/manipulate an ActiveX object in a page with PHP ?**  
This has nothing to do with PHP. ActiveX objects are loaded on client
side if they are requested by the HTML document. There is no relation to
the PHP script and therefore there is no direct server side interaction
possible.

<!-- -->

**Is it possible to get a running instance of a component ?**  
This is possible with the help of monikers. If you want to get multiple
references to the same word instance you can create that instance like
shown:

``` php
<?php
$word = new COM("C:\docs\word.doc");
?>
```

This will create a new instance if there is no running instance
available or it will return a handle to the running instance, if
available.

<!-- -->

**Is there a way to handle an event sent from COM object ?**  
You can define an event sink and bind it using <span
class="function">com\_event\_sink</span>. You can use <span
class="function">com\_print\_typeinfo</span> to have PHP generate a
skeleton for the event sink class.

<!-- -->

**I'm having problems when trying to invoke a method of a COM object which exposes more than one interface. What can I do ?**  
The answer is as simple as unsatisfying. I don't know exactly but i
think you can do nothing. If someone has specific information about
this, please let
<a href="mailto:harald.radi@nme.at" class="link external">» me</a> know
:)

<!-- -->

**So PHP works with COM, how about COM+ ?**  
COM+ extends COM by a framework for managing components through MTS and
MSMQ but there is nothing special that PHP has to support to use such
components.

<!-- -->

**If PHP can manipulate COM objects, can we imagine to use MTS to manage components resources, in conjunction with PHP ?**  
PHP itself doesn't handle transactions yet. Thus if an error occurs no
rollback is initiated. If you use components that support transactions
you will have to implement the transaction management yourself.
