No external libraries are needed to build this extension, but if you
want PHP to support LFS (large files) on Linux, then you need to have a
recent glibc and you need compile PHP with the following compiler flags:
*-D\_LARGEFILE\_SOURCE -D\_FILE\_OFFSET\_BITS=64*.
