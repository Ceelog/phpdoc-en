# phpdoc-en

## What

PHP manual in Markdown format

## Why

Markdown has become a mainstream document writing markup language, which can efficiently write and read documents.

In addition, markdown has a rich tool chain that can convert documents to various formats and customize rendering styles.

Due to historical reasons, the php manual has been written in xml format, which is not conducive to promotion and application. In order to allow more users to use the php manual as they please, and easily notice the latest changes in the documentation, this project pulls updates from the php manual svn library every day and converts them to md format.

## How

[PHP Manual](http://svn.php.net/viewvc/phpdoc/) The original content is an xml file using docbook syntax, through [PhD](http://doc.php.net/phd.php) The document conversion tool generates content in intermediate html format, and then uses [pandoc](https://github.com/jgm/pandoc) to convert to md format.

Finally, you can use [mdbook](https://github.com/rust-lang/mdBook) to render the content in md format into the desired style for easy reading.

You can also read the generated documentation directly at http://phpdoc-en.roadmapedu.com/.

## Acknowledgement

- https://www.php.net/docs.php
- http://doc.php.net/phd.php
- https://github.com/jgm/pandoc
- https://github.com/rust-lang/mdBook
- http://phpdoc-zh.roadmapedu.com/
- http://phpdoc-en.roadmapedu.com/
