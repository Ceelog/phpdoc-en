Examples
========

Here is a simple example PHP script using the tokenizer that will read
in a PHP file, strip all comments from the source and print the pure
code only.

**Example \#1 Strip comments with the tokenizer**

``` php
<?php
$source = file_get_contents('example.php');
$tokens = token_get_all($source);

foreach ($tokens as $token) {
   if (is_string($token)) {
       // simple 1-character token
       echo $token;
   } else {
       // token array
       list($id, $text) = $token;

       switch ($id) { 
           case T_COMMENT: 
           case T_DOC_COMMENT:
               // no action on comments
               break;

           default:
               // anything else -> output "as is"
               echo $text;
               break;
       }
   }
}
?>
```
