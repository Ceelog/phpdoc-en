Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/lapack/setup.html#Requirements)
-   [Installation](/lapack/setup.html#Installation)
-   [Runtime Configuration](/lapack/setup.html#Runtime%20Configuration)
-   [Resource Types](/lapack/setup.html#Resource%20Types)

Requirements
------------

Lapack requires the LAPACK and LAPACKE libraries.

Installation
------------

Most distribution LAPACK packages do not include lapacke, so the easiest
method is to build from source:

      svn co https://icl.cs.utk.edu/svn/lapack-dev/lapack/trunk lapack
      cd lapack
      mkdir build
      cd build
      cmake -D BUILD_SHARED_LIBS=ON -D LAPACKE=ON ../
      make 
      sudo make install
      

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.
