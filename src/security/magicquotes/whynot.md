Why not to use Magic Quotes
---------------------------

**Warning**

This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

-   <span class="simpara"> Portability </span> <span class="simpara">
    Assuming it to be on, or off, affects portability. Use <span
    class="function">get\_magic\_quotes\_gpc</span> to check for this,
    and code accordingly. </span>
-   <span class="simpara"> Performance </span> <span class="simpara">
    Because not every piece of escaped data is inserted into a database,
    there is a performance loss for escaping all this data. Simply
    calling on the escaping functions (like <span
    class="function">addslashes</span>) at runtime is more efficient.
    </span> <span class="simpara"> Although `php.ini-development`
    enables these directives by default, `php.ini-production` disables
    it. This recommendation is mainly due to performance reasons.
    </span>
-   <span class="simpara"> Inconvenience </span> <span class="simpara">
    Because not all data needs escaping, it's often annoying to see
    escaped data where it shouldn't be. For example, emailing from a
    form, and seeing a bunch of \\' within the email. To fix, this may
    require excessive use of <span class="function">stripslashes</span>.
    </span>
