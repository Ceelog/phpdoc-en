PDO Driver How-To
=================

**Table of Contents**

-   [Prerequisites](/internals2/pdo/prerequisites.html)
-   [Preparation and Housekeeping](/internals2/pdo/preparation.html)
-   [Fleshing out your skeleton](/internals2/pdo/implementing.html)
-   [Building](/internals2/pdo/building.html)
-   [Testing](/internals2/pdo/testing.html)
-   [Packaging and distribution](/internals2/pdo/packaging.html)
-   [pdo\_dbh\_t definition](/internals2/pdo/pdo-dbh-t.html)
-   [pdo\_stmt\_t definition](/internals2/pdo/pdo-stmt-t.html)
-   [Constants](/internals2/pdo/constants.html)
-   [Error handling](/internals2/pdo/error-handling.html)

The purpose of this How-To is to provide a basic understanding of the
steps required to write a database driver that interfaces with the PDO
layer. Please note that this is still an evolving API and as such,
subject to change. This document was prepared based on version 0.3 of
PDO. The learning curve is steep; expect to spend a lot of time on the
prerequisites.
