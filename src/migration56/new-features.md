New features
------------

### Constant expressions

It is now possible to provide a scalar expression involving numeric and
string literals and/or constants in contexts where PHP previously
expected a static value, such as constant and property declarations and
default function arguments.

``` php
<?php
const ONE = 1;
const TWO = ONE * 2;

class C {
    const THREE = TWO + 1;
    const ONE_THIRD = ONE / self::THREE;
    const SENTENCE = 'The value of THREE is '.self::THREE;

    public function f($a = ONE + self::THREE) {
        return $a;
    }
}

echo (new C)->f()."\n";
echo C::SENTENCE;
?>
```

The above example will output:

    4
    The value of THREE is 3

It is also now possible to define a constant <span
class="type">array</span> using the *const* keyword:

``` php
<?php
const ARR = ['a', 'b'];

echo ARR[0];
?>
```

The above example will output:

    a

### Variadic functions via *...*

<a href="/functions/arguments.html#functions.variable-arg-list" class="link">Variadic functions</a>
can now be implemented using the *...* operator, instead of relying on
<span class="function">func\_get\_args</span>.

``` php
<?php
function f($req, $opt = null, ...$params) {
    // $params is an array containing the remaining arguments.
    printf('$req: %d; $opt: %d; number of params: %d'."\n",
           $req, $opt, count($params));
}

f(1);
f(1, 2);
f(1, 2, 3);
f(1, 2, 3, 4);
f(1, 2, 3, 4, 5);
?>
```

The above example will output:

    $req: 1; $opt: 0; number of params: 0
    $req: 1; $opt: 2; number of params: 0
    $req: 1; $opt: 2; number of params: 1
    $req: 1; $opt: 2; number of params: 2
    $req: 1; $opt: 2; number of params: 3

### Argument unpacking via *...*

<a href="/language/types/array.html" class="link">Arrays</a> and <span
class="interfacename">Traversable</span> objects can be unpacked into
argument lists when calling functions by using the *...* operator. This
is also known as the splat operator in other languages, including Ruby.

``` php
<?php
function add($a, $b, $c) {
    return $a + $b + $c;
}

$operators = [2, 3];
echo add(1, ...$operators);
?>
```

The above example will output:

    6

### Exponentiation via *\*\**

A right associative *\*\** operator has been added to support
exponentiation, along with a *\*\*=* shorthand assignment operator.

``` php
<?php
printf("2 ** 3 ==      %d\n", 2 ** 3);
printf("2 ** 3 ** 2 == %d\n", 2 ** 3 ** 2);

$a = 2;
$a **= 3;
printf("a ==           %d\n", $a);
?>
```

The above example will output:

    2 ** 3 ==      8
    2 ** 3 ** 2 == 512
    a ==           8

### *use function* and *use const*

The
<a href="/language/namespaces/importing.html" class="link"><em>use</em></a>
operator has been extended to support importing functions and constants
in addition to classes. This is achieved via the *use function* and *use
const* constructs, respectively.

``` php
<?php
namespace Name\Space {
    const FOO = 42;
    function f() { echo __FUNCTION__."\n"; }
}

namespace {
    use const Name\Space\FOO;
    use function Name\Space\f;

    echo FOO."\n";
    f();
}
?>
```

The above example will output:

    42
    Name\Space\f

### phpdbg

PHP now includes an interactive debugger called phpdbg implemented as a
SAPI module. For more information, please visit the
<a href="/book/phpdbg.html" class="link">phpdbg documentation</a>.

### Default character encoding

<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
is now used as the default character set for the <span
class="function">htmlentities</span>, <span
class="function">html\_entity\_decode</span> and <span
class="function">htmlspecialchars</span> functions. Note that if the
(now deprecated) iconv and mbstring encoding settings are set, they will
take precedence over default\_charset for iconv and mbstring functions,
respectively.

The default value for this setting is *UTF-8*.

### <a href="/wrappers/php.html#wrappers.php.input" class="link"><em>php://input</em></a> is reusable

<a href="/wrappers/php.html#wrappers.php.input" class="link"><em>php://input</em></a>
may now be reopened and read as many times as required. This work has
also resulted in a major reduction in the amount of memory required to
deal with POST data.

### Large file uploads

Files larger than 2 gigabytes in size are now accepted.

### <a href="/book/gmp.html" class="link">GMP</a> supports operator overloading

<a href="/book/gmp.html" class="link">GMP</a> objects now support
operator overloading and casting to scalar types. This allows for more
expressive code using GMP:

``` php
<?php
$a = gmp_init(42);
$b = gmp_init(17);

if (version_compare(PHP_VERSION, '5.6', '<')) {
    echo gmp_intval(gmp_add($a, $b)), PHP_EOL;
    echo gmp_intval(gmp_add($a, 17)), PHP_EOL;
    echo gmp_intval(gmp_add(42, $b)), PHP_EOL;
} else {
    echo $a + $b, PHP_EOL;
    echo $a + 17, PHP_EOL;
    echo 42 + $b, PHP_EOL;
}
?>
```

The above example will output:

    59
    59
    59

### <span class="function">hash\_equals</span> for timing attack safe string comparison

The <span class="function">hash\_equals</span> function has been added
to compare two strings in constant time. This should be used to mitigate
timing attacks; for instance, when testing <span
class="function">crypt</span> password hashes (assuming that you are
unable to use <span class="function">password\_hash</span> and <span
class="function">password\_verify</span>, which aren't susceptible to
timing attacks).

``` php
<?php
$expected  = crypt('12345', '$2a$07$usesomesillystringforsalt$');
$correct   = crypt('12345', '$2a$07$usesomesillystringforsalt$');
$incorrect = crypt('1234',  '$2a$07$usesomesillystringforsalt$');

var_dump(hash_equals($expected, $correct));
var_dump(hash_equals($expected, $incorrect));
?>
```

The above example will output:

    bool(true)
    bool(false)

### *\_\_debugInfo()*

The
<a href="/language/oop5/magic.html#language.oop5.magic.debuginfo" class="link">__debugInfo()</a>
magic method has been added to allow objects to change the properties
and values that are shown when the object is output using <span
class="function">var\_dump</span>.

``` php
<?php
class C {
    private $prop;

    public function __construct($val) {
        $this->prop = $val;
    }

    public function __debugInfo() {
        return [
            'propSquared' => $this->prop ** 2,
        ];
    }
}

var_dump(new C(42));
?>
```

The above example will output:

    object(C)#1 (1) {
      ["propSquared"]=>
      int(1764)
    }

### gost-crypto hash algorithm

The *gost-crypto* hash algorithm has been added. This implements the
GOST hash function using the CryptoPro S-box tables as specified by
<a href="http://www.faqs.org/rfcs/rfc4357" class="link external">» RFC 4357, section 11.2</a>.

### SSL/TLS improvements

A wide range of improvements have been made to the SSL/TLS support in
PHP 5.6. These include
<a href="/migration56/incompatible.html#migration56.incompatible.peer-verification" class="link">enabling peer verification by default</a>,
supporting certificate fingerprint matching, mitigating against TLS
renegotiation attacks, and many new
<a href="/context/ssl.html" class="link">SSL context options</a> to
allow more fine grained control over protocol and verification settings
when using encrypted streams.

These changes are described in more detail in the
<a href="/migration56/openssl.html" class="link">OpenSSL changes in PHP 5.6.x</a>
section of this migration guide.

### <a href="/book/pgsql.html" class="link">pgsql</a> async support

The <a href="/book/pgsql.html" class="link">pgsql</a> extension now
supports asynchronous connections and queries, thereby enabling
non-blocking behaviour when interacting with PostgreSQL databases.
Asynchronous connections may be established via the
**`PGSQL_CONNECT_ASYNC`** constant, and the new <span
class="function">pg\_connect\_poll</span>, <span
class="function">pg\_socket</span>, <span
class="function">pg\_consume\_input</span> and <span
class="function">pg\_flush</span> functions may be used to handle
asynchronous connections and queries.
