History of PHP related projects
-------------------------------

### PEAR

<a href="https://pear.php.net/" class="link external">» PEAR</a>, the
*PHP Extension and Application Repository* (originally, PHP Extension
and Add-on Repository) is PHP's version of foundation classes, and may
grow in the future to be one of the key ways to distribute PHP
extensions among developers.

PEAR was born in discussions held in the PHP Developers' Meeting (PDM)
held in January 2000 in Tel Aviv. It was created by Stig S. Bakken, and
is dedicated to his first-born daughter, Malin Bakken.

Since early 2000, PEAR has grown to be a big, significant project with a
large number of developers working on implementing common, reusable
functionality for the benefit of the entire PHP community. PEAR today
includes a wide variety of infrastructure foundation classes for
database access, content caching, mathematical calculations, eCommerce
and much more.

More information about PEAR can be found in
<a href="https://pear.php.net/manual/" class="link external">» the manual</a>.

### PHP Quality Assurance Initiative

The
<a href="https://qa.php.net/" class="link external">» PHP Quality Assurance Initiative</a>
was set up in the summer of 2000 in response to criticism that PHP
releases were not being tested well enough for production environments.
The team now consists of a core group of developers with a good
understanding of the PHP code base. These developers spend a lot of
their time localizing and fixing bugs within PHP. In addition there are
many other team members who test and provide feedback on these fixes
using a wide variety of platforms.

### PHP-GTK

<a href="http://gtk.php.net/" class="link external">» PHP-GTK</a> is the
PHP solution for writing client side GUI applications. Andrei Zmievski
remembers the planing and creation process of PHP-GTK:

> GUI programming has always been of my interests, and I found that Gtk+
> is a very nice toolkit, except that programming with it in C is
> somewhat tedious. After witnessing PyGtk and GTK-Perl implementations,
> I decided to see if PHP could be made to interface with Gtk+, even
> minimally. Starting in August of 2000, I began to have a bit more free
> time so that is when I started experimenting. My main guideline was
> the PyGtk implementation as it was fairly feature complete and had a
> nice object-oriented interface. James Henstridge, the author of PyGtk,
> provided very helpful advice during those initial stages.
>
> Hand-writing the interfaces to all the Gtk+ functions was out of the
> question, so I seized upon the idea of code-generator, similar to how
> PyGtk did it. The code generator is a PHP program that reads a set of
> `.defs` file containing the Gtk+ classes, constants, and methods
> information and generates C code that interfaces PHP with them. What
> cannot be generated automatically can be written by hand in
> `.overrides` file.
>
> Working on the code generator and the infrastructure took some time,
> because I could spend little time on PHP-GTK during the fall of 2000.
> After I showed PHP-GTK to Frank Kromann, he got interested and started
> helping me out with code generator work and Win32 implementation. When
> we wrote the first Hello World program and fired it up, it was
> extremely exciting. It took a couple more months to get the project to
> a presentable condition and the initial version was released on March
> 1, 2001. The story promptly hit SlashDot.
>
> Sensing that PHP-GTK might be extensive, I set up separate mailing
> lists and CVS repositories for it, as well as the gtk.php.net website
> with the help of Colin Viebrock. The documentation would also need to
> be done and James Moore came in to help with that.
>
> Since its release PHP-GTK has been gaining popularity. We have our own
> documentation team, the manual keeps improving, people start writing
> extensions for PHP-GTK, and more and more exciting applications with
> it.
