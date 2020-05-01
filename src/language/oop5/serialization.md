Object Serialization
--------------------

Serializing objects - objects in sessions
-----------------------------------------

<span class="function">serialize</span> returns a string containing a
byte-stream representation of any value that can be stored in PHP. <span
class="function">unserialize</span> can use this string to recreate the
original variable values. Using serialize to save an object will save
all variables in an object. The methods in an object will not be saved,
only the name of the class.

In order to be able to <span class="function">unserialize</span> an
object, the class of that object needs to be defined. That is, if you
have an object of class A and serialize this, you'll get a string that
refers to class A and contains all values of variables contained in it.
If you want to be able to unserialize this in another file, an object of
class A, the definition of class A must be present in that file first.
This can be done for example by storing the class definition of class A
in an include file and including this file or making use of the <span
class="function">spl\_autoload\_register</span> function.

``` php
<?php
// classa.inc:
  
  class A {
      public $one = 1;
    
      public function show_one() {
          echo $this->one;
      }
  }
  
// page1.php:

  include("classa.inc");
  
  $a = new A;
  $s = serialize($a);
  // store $s somewhere where page2.php can find it.
  file_put_contents('store', $s);

// page2.php:
  
  // this is needed for the unserialize to work properly.
  include("classa.inc");

  $s = file_get_contents('store');
  $a = unserialize($s);

  // now use the function show_one() of the $a object.  
  $a->show_one();
?>
```

If an application is using sessions and uses <span
class="function">session\_register</span> to register objects, these
objects are serialized automatically at the end of each PHP page, and
are unserialized automatically on each of the following pages. This
means that these objects can show up on any of the application's pages
once they become part of the session. However, the <span
class="function">session\_register</span> is removed since PHP 5.4.0.

It is strongly recommended that if an application serializes objects,
for use later in the application, that the application includes the
class definition for that object throughout the application. Not doing
so might result in an object being unserialized without a class
definition, which will result in PHP giving the object a class of <span
class="classname">\_\_PHP\_Incomplete\_Class\_Name</span>, which has no
methods and would render the object useless.

So if in the example above `$a` became part of a session by running
*session\_register("a")*, you should include the file *classa.inc* on
all of your pages, not only `page1.php` and `page2.php`.

Beyond the above advice, note that you can also hook into the
serialization and unserialization events on an object using the
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
and
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
methods. Using
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
also allows you to only serialize a subset of the object's properties.
