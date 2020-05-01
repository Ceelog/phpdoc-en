Directories
===========

**Table of Contents**

-   [Installing/Configuring](/dir/setup.html)
    -   [Requirements](/dir/setup.html#Requirements)
    -   [Installation](/dir/setup.html#Installation)
    -   [Runtime Configuration](/dir/setup.html#Runtime%20Configuration)
    -   [Resource Types](/dir/setup.html#Resource%20Types)
-   [Predefined Constants](/dir/constants.html)
-   [Directory](/class/directory.html) — The Directory class
    -   [Directory::close](/class/directory.html#Directory::close) —
        Close directory handle
    -   [Directory::read](/class/directory.html#Directory::read) — Read
        entry from directory handle
    -   [Directory::rewind](/class/directory.html#Directory::rewind) —
        Rewind directory handle
-   [Directory Functions](/ref/dir.html)
    -   [chdir](/ref/dir.html#chdir) — Change directory
    -   [chroot](/ref/dir.html#chroot) — Change the root directory
    -   [closedir](/ref/dir.html#closedir) — Close directory handle
    -   [dir](/ref/dir.html#dir) — Return an instance of the Directory
        class
    -   [getcwd](/ref/dir.html#getcwd) — Gets the current working
        directory
    -   [opendir](/ref/dir.html#opendir) — Open directory handle
    -   [readdir](/ref/dir.html#readdir) — Read entry from directory
        handle
    -   [rewinddir](/ref/dir.html#rewinddir) — Rewind directory handle
    -   [scandir](/ref/dir.html#scandir) — List files and directories
        inside the specified path

Introduction
------------

Instances of <span class="classname">Directory</span> are created by
calling the <span class="function">dir</span> function, not by the
<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>
operator.

Class synopsis
--------------

**Directory**

<span class="ooclass"> class **Directory** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">string</span>
`$path` ;

<span class="modifier">public</span> <span class="type">resource</span>
`$handle` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">close</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">read</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$dir_handle`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

}

Properties
----------

`path`  
The directory that was opened.

`handle`  
Can be used with other directory functions such as <span
class="function">readdir</span>, <span class="function">rewinddir</span>
and <span class="function">closedir</span>.

Directory::close
================

Close directory handle

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Directory::close</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Same as <span class="function">closedir</span>, only `    dir_handle`
defaults to `$this->handle`.

Directory::read
===============

Read entry from directory handle

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Directory::read</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Same as <span class="function">readdir</span>, only `    dir_handle`
defaults to `$this->handle`.

Directory::rewind
=================

Rewind directory handle

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Directory::rewind</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Same as <span class="function">rewinddir</span>, only `    dir_handle`
defaults to `$this->handle`.
