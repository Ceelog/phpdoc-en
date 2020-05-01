Safe Password Hashing
=====================

This section explains the reasons behind using hashing functions to
secure passwords, as well as how to do so effectively.

1.  [Why should I hash passwords supplied by users of my
    application?](#faq.passwords.hashing)
2.  [Why are common hashing functions such as md5 and sha1 unsuitable
    for passwords?](#faq.passwords.fasthash)
3.  [How should I hash my passwords, if the common hash functions are
    not suitable?](#faq.passwords.bestpractice)
4.  [What is a salt?](#faq.passwords.salt)
5.  [How do I store my salts?](#faq.password.storing-salts)

**Why should I hash passwords supplied by users of my application?**  
Password hashing is one of the most basic security considerations that
must be made when designing any application that accepts passwords from
users. Without hashing, any passwords that are stored in your
application's database can be stolen if the database is compromised, and
then immediately used to compromise not only your application, but also
the accounts of your users on other services, if they do not use unique
passwords.

By applying a hashing algorithm to your user's passwords before storing
them in your database, you make it implausible for any attacker to
determine the original password, while still being able to compare the
resulting hash to the original password in the future.

It is important to note, however, that hashing passwords only protects
them from being compromised in your data store, but does not necessarily
protect them from being intercepted by malicious code injected into your
application itself.

<!-- -->

**Why are common hashing functions such as <span class="function">md5</span> and <span class="function">sha1</span> unsuitable for passwords?**  
Hashing algorithms such as MD5, SHA1 and SHA256 are designed to be very
fast and efficient. With modern techniques and computer equipment, it
has become trivial to "brute force" the output of these algorithms, in
order to determine the original input.

Because of how quickly a modern computer can "reverse" these hashing
algorithms, many security professionals strongly suggest against their
use for password hashing.

<!-- -->

**How should I hash my passwords, if the common hash functions are not suitable?**  
When hashing passwords, the two most important considerations are the
computational expense, and the salt. The more computationally expensive
the hashing algorithm, the longer it will take to brute force its
output.

PHP 5.5 provides
<a href="/book/password.html" class="link">a native password hashing API</a>
that safely handles both
<a href="/ref/password.html#password_hash" class="link">hashing</a> and
<a href="/ref/password.html#password_verify" class="link">verifying passwords</a>
in a secure manner. There is also
<a href="https://github.com/ircmaxell/password_compat" class="link external">» a pure PHP compatibility library</a>
available for PHP 5.3.7 and later.

Another option is the <span class="function">crypt</span> function,
which supports several hashing algorithms in PHP 5.3 and later. When
using this function, you are guaranteed that the algorithm you select is
available, as PHP contains native implementations of each supported
algorithm, in case one or more are not supported by your system.

The suggested algorithm to use when hashing passwords is Blowfish, which
is also the default used by the password hashing API, as it is
significantly more computationally expensive than MD5 or SHA1, while
still being scalable.

Note that if you are using <span class="function">crypt</span> to verify
a password, you will need to take care to prevent timing attacks by
using a constant time string comparison. Neither PHP's
<a href="/language/operators/comparison.html" class="link">== and === operators</a>
nor <span class="function">strcmp</span> perform constant time string
comparisons. As <span class="function">password\_verify</span> will do
this for you, you are strongly encouraged to use the
<a href="/book/password.html" class="link">native password hashing API</a>
whenever possible.

<!-- -->

**What is a salt?**  
A cryptographic salt is data which is applied during the hashing process
in order to eliminate the possibility of the output being looked up in a
list of pre-calculated pairs of hashes and their input, known as a
rainbow table.

In more simple terms, a salt is a bit of additional data which makes
your hashes significantly more difficult to crack. There are a number of
services online which provide extensive lists of pre-computed hashes, as
well as the original input for those hashes. The use of a salt makes it
implausible or impossible to find the resulting hash in one of these
lists.

<span class="function">password\_hash</span> will create a random salt
if one isn't provided, and this is generally the easiest and most secure
approach.

<!-- -->

**How do I store my salts?**  
When using <span class="function">password\_hash</span> or <span
class="function">crypt</span>, the return value includes the salt as
part of the generated hash. This value should be stored verbatim in your
database, as it includes information about the hash function that was
used and can then be given directly to <span
class="function">password\_verify</span> or <span
class="function">crypt</span> when verifying passwords.

The following diagram shows the format of a return value from <span
class="function">crypt</span> or <span
class="function">password\_hash</span>. As you can see, they are
self-contained, with all the information on the algorithm and salt
required for future password verification.

<img src="images/2a34c7f2e658f6ae74f3869f2aa5886f-crypt-text-rendered.svg" width="690" height="192" alt=" The components of the value returned by password_hash and crypt: in order, the chosen algorithm, the algorithm&#39;s options, the salt used, and the hashed password. " />
