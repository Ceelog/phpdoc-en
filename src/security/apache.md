Installed as an Apache module
=============================

When PHP is used as an Apache module it inherits Apache's user
permissions (typically those of the "nobody" user). This has several
impacts on security and authorization. For example, if you are using PHP
to access a database, unless that database has built-in access control,
you will have to make the database accessible to the "nobody" user. This
means a malicious script could access and modify the database, even
without a username and password. It's entirely possible that a web
spider could stumble across a database administrator's web page, and
drop all of your databases. You can protect against this with Apache
authorization, or you can design your own access model using LDAP,
`.htaccess` files, etc. and include that code as part of your PHP
scripts.

Often, once security is established to the point where the PHP user (in
this case, the apache user) has very little risk attached to it, it is
discovered that PHP is now prevented from writing any files to user
directories. Or perhaps it has been prevented from accessing or changing
databases. It has equally been secured from writing good and bad files,
or entering good and bad database transactions.

A frequent security mistake made at this point is to allow apache root
permissions, or to escalate apache's abilities in some other way.

Escalating the Apache user's permissions to root is extremely dangerous
and may compromise the entire system, so sudo'ing, chroot'ing, or
otherwise running as root should not be considered by those who are not
security professionals.

There are some simpler solutions. By using
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
you can control and restrict what directories are allowed to be used for
PHP. You can also set up apache-only areas, to restrict all web based
activity to non-user, or non-system, files.
