Filesystem
==========

**Table of Contents**

-   [Introduction](/intro/filesystem.html)
-   [Installing/Configuring](/filesystem/setup.html)
    -   [Requirements](/filesystem/setup.html#Requirements)
    -   [Installation](/filesystem/setup.html#Installation)
    -   [Runtime
        Configuration](/filesystem/setup.html#Runtime%20Configuration)
    -   [Resource Types](/filesystem/setup.html#Resource%20Types)
-   [Predefined Constants](/filesystem/constants.html)
-   [Filesystem Functions](/ref/filesystem.html)
    -   [basename](/ref/filesystem.html#basename) — Returns trailing
        name component of path
    -   [chgrp](/ref/filesystem.html#chgrp) — Changes file group
    -   [chmod](/ref/filesystem.html#chmod) — Changes file mode
    -   [chown](/ref/filesystem.html#chown) — Changes file owner
    -   [clearstatcache](/ref/filesystem.html#clearstatcache) — Clears
        file status cache
    -   [copy](/ref/filesystem.html#copy) — Copies file
    -   [delete](/ref/filesystem.html#delete) — See unlink or unset
    -   [dirname](/ref/filesystem.html#dirname) — Returns a parent
        directory's path
    -   [disk\_free\_space](/ref/filesystem.html#disk_free_space) —
        Returns available space on filesystem or disk partition
    -   [disk\_total\_space](/ref/filesystem.html#disk_total_space) —
        Returns the total size of a filesystem or disk partition
    -   [diskfreespace](/ref/filesystem.html#diskfreespace) — Alias of
        disk\_free\_space
    -   [fclose](/ref/filesystem.html#fclose) — Closes an open file
        pointer
    -   [feof](/ref/filesystem.html#feof) — Tests for end-of-file on a
        file pointer
    -   [fflush](/ref/filesystem.html#fflush) — Flushes the output to a
        file
    -   [fgetc](/ref/filesystem.html#fgetc) — Gets character from file
        pointer
    -   [fgetcsv](/ref/filesystem.html#fgetcsv) — Gets line from file
        pointer and parse for CSV fields
    -   [fgets](/ref/filesystem.html#fgets) — Gets line from file
        pointer
    -   [fgetss](/ref/filesystem.html#fgetss) — Gets line from file
        pointer and strip HTML tags
    -   [file\_exists](/ref/filesystem.html#file_exists) — Checks
        whether a file or directory exists
    -   [file\_get\_contents](/ref/filesystem.html#file_get_contents) —
        Reads entire file into a string
    -   [file\_put\_contents](/ref/filesystem.html#file_put_contents) —
        Write data to a file
    -   [file](/ref/filesystem.html#file) — Reads entire file into an
        array
    -   [fileatime](/ref/filesystem.html#fileatime) — Gets last access
        time of file
    -   [filectime](/ref/filesystem.html#filectime) — Gets inode change
        time of file
    -   [filegroup](/ref/filesystem.html#filegroup) — Gets file group
    -   [fileinode](/ref/filesystem.html#fileinode) — Gets file inode
    -   [filemtime](/ref/filesystem.html#filemtime) — Gets file
        modification time
    -   [fileowner](/ref/filesystem.html#fileowner) — Gets file owner
    -   [fileperms](/ref/filesystem.html#fileperms) — Gets file
        permissions
    -   [filesize](/ref/filesystem.html#filesize) — Gets file size
    -   [filetype](/ref/filesystem.html#filetype) — Gets file type
    -   [flock](/ref/filesystem.html#flock) — Portable advisory file
        locking
    -   [fnmatch](/ref/filesystem.html#fnmatch) — Match filename against
        a pattern
    -   [fopen](/ref/filesystem.html#fopen) — Opens file or URL
    -   [fpassthru](/ref/filesystem.html#fpassthru) — Output all
        remaining data on a file pointer
    -   [fputcsv](/ref/filesystem.html#fputcsv) — Format line as CSV and
        write to file pointer
    -   [fputs](/ref/filesystem.html#fputs) — Alias of fwrite
    -   [fread](/ref/filesystem.html#fread) — Binary-safe file read
    -   [fscanf](/ref/filesystem.html#fscanf) — Parses input from a file
        according to a format
    -   [fseek](/ref/filesystem.html#fseek) — Seeks on a file pointer
    -   [fstat](/ref/filesystem.html#fstat) — Gets information about a
        file using an open file pointer
    -   [ftell](/ref/filesystem.html#ftell) — Returns the current
        position of the file read/write pointer
    -   [ftruncate](/ref/filesystem.html#ftruncate) — Truncates a file
        to a given length
    -   [fwrite](/ref/filesystem.html#fwrite) — Binary-safe file write
    -   [glob](/ref/filesystem.html#glob) — Find pathnames matching a
        pattern
    -   [is\_dir](/ref/filesystem.html#is_dir) — Tells whether the
        filename is a directory
    -   [is\_executable](/ref/filesystem.html#is_executable) — Tells
        whether the filename is executable
    -   [is\_file](/ref/filesystem.html#is_file) — Tells whether the
        filename is a regular file
    -   [is\_link](/ref/filesystem.html#is_link) — Tells whether the
        filename is a symbolic link
    -   [is\_readable](/ref/filesystem.html#is_readable) — Tells whether
        a file exists and is readable
    -   [is\_uploaded\_file](/ref/filesystem.html#is_uploaded_file) —
        Tells whether the file was uploaded via HTTP POST
    -   [is\_writable](/ref/filesystem.html#is_writable) — Tells whether
        the filename is writable
    -   [is\_writeable](/ref/filesystem.html#is_writeable) — Alias of
        is\_writable
    -   [lchgrp](/ref/filesystem.html#lchgrp) — Changes group ownership
        of symlink
    -   [lchown](/ref/filesystem.html#lchown) — Changes user ownership
        of symlink
    -   [link](/ref/filesystem.html#link) — Create a hard link
    -   [linkinfo](/ref/filesystem.html#linkinfo) — Gets information
        about a link
    -   [lstat](/ref/filesystem.html#lstat) — Gives information about a
        file or symbolic link
    -   [mkdir](/ref/filesystem.html#mkdir) — Makes directory
    -   [move\_uploaded\_file](/ref/filesystem.html#move_uploaded_file)
        — Moves an uploaded file to a new location
    -   [parse\_ini\_file](/ref/filesystem.html#parse_ini_file) — Parse
        a configuration file
    -   [parse\_ini\_string](/ref/filesystem.html#parse_ini_string) —
        Parse a configuration string
    -   [pathinfo](/ref/filesystem.html#pathinfo) — Returns information
        about a file path
    -   [pclose](/ref/filesystem.html#pclose) — Closes process file
        pointer
    -   [popen](/ref/filesystem.html#popen) — Opens process file pointer
    -   [readfile](/ref/filesystem.html#readfile) — Outputs a file
    -   [readlink](/ref/filesystem.html#readlink) — Returns the target
        of a symbolic link
    -   [realpath\_cache\_get](/ref/filesystem.html#realpath_cache_get)
        — Get realpath cache entries
    -   [realpath\_cache\_size](/ref/filesystem.html#realpath_cache_size)
        — Get realpath cache size
    -   [realpath](/ref/filesystem.html#realpath) — Returns
        canonicalized absolute pathname
    -   [rename](/ref/filesystem.html#rename) — Renames a file or
        directory
    -   [rewind](/ref/filesystem.html#rewind) — Rewind the position of a
        file pointer
    -   [rmdir](/ref/filesystem.html#rmdir) — Removes directory
    -   [set\_file\_buffer](/ref/filesystem.html#set_file_buffer) —
        Alias of stream\_set\_write\_buffer
    -   [stat](/ref/filesystem.html#stat) — Gives information about a
        file
    -   [symlink](/ref/filesystem.html#symlink) — Creates a symbolic
        link
    -   [tempnam](/ref/filesystem.html#tempnam) — Create file with
        unique file name
    -   [tmpfile](/ref/filesystem.html#tmpfile) — Creates a temporary
        file
    -   [touch](/ref/filesystem.html#touch) — Sets access and
        modification time of file
    -   [umask](/ref/filesystem.html#umask) — Changes the current umask
    -   [unlink](/ref/filesystem.html#unlink) — Deletes a file
