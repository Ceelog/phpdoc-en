glob://
=======

Find pathnames matching pattern

### Description

The `glob:` stream wrapper is available since PHP 5.3.0.

### Usage

-   <span class="simpara">`glob://`</span>

### Options

| Attribute                                                                          | Supported |
|------------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a>   | No        |
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_include</a> | No        |
| Allows Reading                                                                     | No        |
| Allows Writing                                                                     | No        |
| Allows Appending                                                                   | No        |
| Allows Simultaneous Reading and Writing                                            | No        |
| Supports <span class="function">stat</span>                                        | No        |
| Supports <span class="function">unlink</span>                                      | No        |
| Supports <span class="function">rename</span>                                      | No        |
| Supports <span class="function">mkdir</span>                                       | No        |
| Supports <span class="function">rmdir</span>                                       | No        |

### Examples

**Example \#1 Basic usage**

``` php
<?php
// Loop over all *.php files in ext/spl/examples/ directory
// and print the filename and its size
$it = new DirectoryIterator("glob://ext/spl/examples/*.php");
foreach($it as $f) {
    printf("%s: %.1FK\n", $f->getFilename(), $f->getSize()/1024);
}
?>
```

    tree.php: 1.0K
    findregex.php: 0.6K
    findfile.php: 0.7K
    dba_dump.php: 0.9K
    nocvsdir.php: 1.1K
    phar_from_dir.php: 1.0K
    ini_groups.php: 0.9K
    directorytree.php: 0.9K
    dba_array.php: 1.1K
    class_tree.php: 1.8K
