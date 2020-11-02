Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/zookeeper/setup.html#Requirements)
-   [Installation](/zookeeper/setup.html#Installation)
-   [Runtime
    Configuration](/zookeeper/setup.html#Runtime%20Configuration)
-   [Resource Types](/zookeeper/setup.html#Resource%20Types)

Requirements
------------

This extension requires
<a href="https://zookeeper.apache.org/" class="link external">» ZooKeeper</a>
C Binding (version 3.4.1 or greater). For more information, see
<a href="https://zookeeper.apache.org/doc/trunk/zookeeperProgrammers.html#C+Binding" class="link external">» ZooKeeper Programmer's Guide</a>.

This extension requires PHP version 5.2.0 or higher. Since 0.6.0, it
requires PHP version 7.0.0 or higher.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/zookeeper" class="link external">» https://pecl.php.net/package/zookeeper</a>.

To enable zookeeper support, configure with
**--with-libzookeeper-dir=DIR**. DIR is the install prefix of ZooKeeper
C Binding, which must contain the `include/zookeeper/zookeeper.h`

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                       | Default | Changeable       | Changelog |
|----------------------------------------------------------------------------|---------|------------------|-----------|
| <a href="/zookeeper/setup.html#" class="link">zookeeper.recv_timeout</a>   | 10000   | PHP\_INI\_ALL    |           |
| <a href="/zookeeper/setup.html#" class="link">zookeeper.session_lock</a>   | 1       | PHP\_INI\_SYSTEM |           |
| <a href="/zookeeper/setup.html#" class="link">zookeeper.sess_lock_wait</a> | 150000  | PHP\_INI\_ALL    |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`zookeeper.recv_timeout` <span class="type">int</span>  
Default the timeout for any ZooKeeper session.

`zookeeper.session_lock` <span class="type">int</span>  
Enable PHP session locking.

`zookeeper.sess_lock_wait` <span class="type">int</span>  
PHP Session spin lock retry wait time in microseconds. Be carefull when
setting this value. Valid values are integers, where 0 is interpreted as
the default value. Negative values result in a reduces locking to a try
lock.

Resource Types
--------------

This extension has no resource types defined.
