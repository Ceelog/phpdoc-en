Interactive shell
-----------------

As of PHP 5.1.0, the CLI SAPI provides an interactive shell using the
**-a** option if PHP is compiled with the **--with-readline** option. As
of PHP 7.1.0 the interactive shell is also available on Windows, if the
<a href="/book/readline.html" class="link">readline extension</a> is
enabled.

Using the interactive shell you are able to type PHP code and have it
executed directly.

**Example \#1 Executing code using the interactive shell**

``` shell
$ php -a
Interactive shell

php > echo 5+8;
13
php > function addTwo($n)
php > {
php { return $n + 2;
php { }
php > var_dump(addtwo(2));
int(4)
php >
```

The interactive shell also features tab completion for functions,
constants, class names, variables, static method calls and class
constants.

**Example \#2 Tab completion**

Pressing the tab key twice when there are multiple possible completions
will result in a list of these completions:

``` shell
php > strp[TAB][TAB]
strpbrk   strpos    strptime  
php > strp
```

When there is only one possible completion, pressing tab once will
complete the rest on the same line:

``` shell
php > strpt[TAB]ime(
```

Completion will also work for names that have been defined during the
current interactive shell session:

``` shell
php > $fooThisIsAReallyLongVariableName = 42;
php > $foo[TAB]ThisIsAReallyLongVariableName
```

The interactive shell stores your history which can be accessed using
the up and down keys. The history is saved in the `~/.php_history` file.

As of PHP 5.4.0, the CLI SAPI provides the `php.ini` settings
`cli.pager` and `cli.prompt`. The `cli.pager` setting allows an external
program (such as `less`) to act as a pager for the output instead of
being displayed directly on the screen. The `cli.prompt` setting makes
it possible to change the *php \>* prompt.

In PHP 5.4.0 it was also made possible to set `php.ini` settings in the
interactive shell using a shorthand notation.

**Example \#3 Setting `php.ini` settings in the interactive shell**

The `cli.prompt` setting:

``` shell
php > #cli.prompt=hello world :> 
hello world :>
```

Using backticks it is possible to have PHP code executed in the prompt:

``` shell
php > #cli.prompt=`echo date('H:i:s');` php > 
15:49:35 php > echo 'hi';
hi
15:49:43 php > sleep(2);
15:49:45 php >
```

Setting the pager to `less`:

``` shell
php > #cli.pager=less
php > phpinfo();
(output displayed in less)
php >
```

The `cli.prompt` setting supports a few escape sequences:

| Sequence | Description                                                                                                                                                          |
|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *\\e*    | Used for adding colors to the prompt. An example could be *\\e\[032m\\v \\e\[031m\\b \\e\[34m\\\> \\e\[0m*                                                           |
| *\\v*    | The PHP version.                                                                                                                                                     |
| *\\b*    | Indicates which block PHP is in. For instance */\** to indicate being inside a multi-line comment. The outer scope is denoted by *php*.                              |
| *\\\>*   | Indicates the prompt character. By default this is *\>*, but changes when the shell is inside an unterminated block or string. Possible characters are: *' " { ( \>* |

> **Note**:
>
> Files included through
> <a href="/ini/core.html#ini.auto-prepend-file" class="link">auto_prepend_file</a>
> and
> <a href="/ini/core.html#ini.auto-append-file" class="link">auto_append_file</a>
> are parsed in this mode but with some restrictions - e.g. functions
> have to be defined before called.

> **Note**:
>
> <a href="/language/oop5/autoload.html" class="link">Autoloading</a> is
> not available if using PHP in CLI interactive mode.
