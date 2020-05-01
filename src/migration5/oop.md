New Object Model
----------------

In PHP 5 there is a new Object Model. PHP's handling of objects has been
completely rewritten, allowing for better performance and more features.
In previous versions of PHP, objects were handled like primitive types
(for instance integers and strings). The drawback of this method was
that semantically the whole object was copied when a variable was
assigned, or passed as a parameter to a method. In the new approach,
objects are referenced by handle, and not by value (one can think of a
handle as an object's identifier).

Many PHP programmers aren't even aware of the copying quirks of the old
object model and, therefore, the majority of PHP applications will work
out of the box, or with very few modifications.

The new Object Model is documented at the
<a href="/language/oop5.html" class="link">Language Reference</a>.

In PHP 5, function with the name of a class is called as a constructor
only if defined in the same class. In PHP 4, it is called also if
defined in the parent class.

See also the
<a href="/ini/core.html#ini.zend.ze1-compatibility-mode" class="link">zend.ze1_compatibility_mode</a>
directive for compatibility with PHP 4.
