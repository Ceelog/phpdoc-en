ZooKeeper
=========

**Table of Contents**

-   [Introduction](/intro/zookeeper.html)
-   [Installing/Configuring](/zookeeper/setup.html)
    -   [Requirements](/zookeeper/setup.html#Requirements)
    -   [Installation](/zookeeper/setup.html#Installation)
    -   [Runtime
        Configuration](/zookeeper/setup.html#Runtime%20Configuration)
    -   [Resource Types](/zookeeper/setup.html#Resource%20Types)
-   [Predefined Constants](/zookeeper/constants.html)
-   [ZooKeeper Functions](/ref/zookeeper.html)
    -   [zookeeper\_dispatch](/ref/zookeeper.html#zookeeper_dispatch) —
        Calls callbacks for pending operations
-   [Zookeeper](/class/zookeeper.html) — The Zookeeper class
    -   [Zookeeper::addAuth](/class/zookeeper.html#Zookeeper::addAuth) —
        Specify application credentials
    -   [Zookeeper::close](/class/zookeeper.html#Zookeeper::close) —
        Close the zookeeper handle and free up any resources
    -   [Zookeeper::connect](/class/zookeeper.html#Zookeeper::connect) —
        Create a handle to used communicate with zookeeper
    -   [Zookeeper::\_\_construct](/class/zookeeper.html#Zookeeper::__construct)
        — Create a handle to used communicate with zookeeper
    -   [Zookeeper::create](/class/zookeeper.html#Zookeeper::create) —
        Create a node synchronously
    -   [Zookeeper::delete](/class/zookeeper.html#Zookeeper::delete) —
        Delete a node in zookeeper synchronously
    -   [Zookeeper::exists](/class/zookeeper.html#Zookeeper::exists) —
        Checks the existence of a node in zookeeper synchronously
    -   [Zookeeper::get](/class/zookeeper.html#Zookeeper::get) — Gets
        the data associated with a node synchronously
    -   [Zookeeper::getAcl](/class/zookeeper.html#Zookeeper::getAcl) —
        Gets the acl associated with a node synchronously
    -   [Zookeeper::getChildren](/class/zookeeper.html#Zookeeper::getChildren)
        — Lists the children of a node synchronously
    -   [Zookeeper::getClientId](/class/zookeeper.html#Zookeeper::getClientId)
        — Return the client session id, only valid if the connections is
        currently connected (ie. last watcher state is
        ZOO\_CONNECTED\_STATE)
    -   [Zookeeper::getConfig](/class/zookeeper.html#Zookeeper::getConfig)
        — Get instance of ZookeeperConfig
    -   [Zookeeper::getRecvTimeout](/class/zookeeper.html#Zookeeper::getRecvTimeout)
        — Return the timeout for this session, only valid if the
        connections is currently connected (ie. last watcher state is
        ZOO\_CONNECTED\_STATE). This value may change after a server
        re-connect
    -   [Zookeeper::getState](/class/zookeeper.html#Zookeeper::getState)
        — Get the state of the zookeeper connection
    -   [Zookeeper::isRecoverable](/class/zookeeper.html#Zookeeper::isRecoverable)
        — Checks if the current zookeeper connection state can be
        recovered
    -   [Zookeeper::set](/class/zookeeper.html#Zookeeper::set) — Sets
        the data associated with a node
    -   [Zookeeper::setAcl](/class/zookeeper.html#Zookeeper::setAcl) —
        Sets the acl associated with a node synchronously
    -   [Zookeeper::setDebugLevel](/class/zookeeper.html#Zookeeper::setDebugLevel)
        — Sets the debugging level for the library
    -   [Zookeeper::setDeterministicConnOrder](/class/zookeeper.html#Zookeeper::setDeterministicConnOrder)
        — Enable/disable quorum endpoint order randomization
    -   [Zookeeper::setLogStream](/class/zookeeper.html#Zookeeper::setLogStream)
        — Sets the stream to be used by the library for logging
    -   [Zookeeper::setWatcher](/class/zookeeper.html#Zookeeper::setWatcher)
        — Set a watcher function
-   [ZookeeperConfig](/class/zookeeperconfig.html) — The ZookeeperConfig
    class
    -   [ZookeeperConfig::add](/class/zookeeperconfig.html#ZookeeperConfig::add)
        — Add servers to the ensemble
    -   [ZookeeperConfig::get](/class/zookeeperconfig.html#ZookeeperConfig::get)
        — Gets the last committed configuration of the ZooKeeper cluster
        as it is known to the server to which the client is connected,
        synchronously
    -   [ZookeeperConfig::remove](/class/zookeeperconfig.html#ZookeeperConfig::remove)
        — Remove servers from the ensemble
    -   [ZookeeperConfig::set](/class/zookeeperconfig.html#ZookeeperConfig::set)
        — Change ZK cluster ensemble membership and roles of ensemble
        peers
-   [ZookeeperException](/class/zookeeperexception.html) — The
    ZookeeperException class
-   [ZookeeperAuthenticationException](/class/zookeeperauthenticationexception.html)
    — The ZookeeperAuthenticationException class
-   [ZookeeperConnectionException](/class/zookeeperconnectionexception.html)
    — The ZookeeperConnectionException class
-   [ZookeeperMarshallingException](/class/zookeepermarshallingexception.html)
    — The ZookeeperMarshallingException class
-   [ZookeeperNoNodeException](/class/zookeepernonodeexception.html) —
    The ZookeeperNoNodeException class
-   [ZookeeperOperationTimeoutException](/class/zookeeperoperationtimeoutexception.html)
    — The ZookeeperOperationTimeoutException class
-   [ZookeeperSessionException](/class/zookeepersessionexception.html) —
    The ZookeeperSessionException class

Introduction
------------

Represents ZooKeeper session.

Class synopsis
--------------

**Zookeeper**

<span class="ooclass"> class **Zookeeper** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`<span
class="initializer"> = ''</span></span> \[, <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$recv_timeout`<span class="initializer"> = 10000</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addAuth</span> ( <span
class="methodparam"><span class="type">string</span> `$scheme`</span> ,
<span class="methodparam"><span class="type">string</span>
`$cert`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$completion_cb`<span class="initializer">
= **`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$recv_timeout`<span class="initializer"> = 10000</span></span> \]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">create</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> ,
<span class="methodparam"><span class="type">array</span> `$acls`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = **`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">exists</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$max_size`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getAcl</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getChildren</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getClientId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ZookeeperConfig</span> <span
class="methodname">getConfig</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getRecvTimeout</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getState</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isRecoverable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">set</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setAcl</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">int</span> `$version`</span> ,
<span class="methodparam"><span class="type">array</span> `$acl`</span>
)

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setDebugLevel</span> ( <span
class="methodparam"><span class="type">int</span> `$logLevel`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setDeterministicConnOrder</span> ( <span
class="methodparam"><span class="type">bool</span> `$yesOrNo`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setLogStream</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setWatcher</span> ( <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`</span> )

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`PERM_READ` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`PERM_WRITE` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`PERM_CREATE` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`PERM_DELETE` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`PERM_ADMIN` <span class="initializer"> = 16</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`PERM_ALL` <span class="initializer"> = 31</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`EPHEMERAL` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SEQUENCE` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`LOG_LEVEL_ERROR` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`LOG_LEVEL_WARN` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`LOG_LEVEL_INFO` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`LOG_LEVEL_DEBUG` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`EXPIRED_SESSION_STATE` <span class="initializer"> = -112</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`AUTH_FAILED_STATE` <span class="initializer"> = -113</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CONNECTING_STATE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ASSOCIATING_STATE` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CONNECTED_STATE` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`READONLY_STATE` <span class="initializer"> = 5</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOTCONNECTED_STATE` <span class="initializer"> = 999</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CREATED_EVENT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DELETED_EVENT` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CHANGED_EVENT` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CHILD_EVENT` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SESSION_EVENT` <span class="initializer"> = -1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOTWATCHING_EVENT` <span class="initializer"> = -2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SYSTEMERROR` <span class="initializer"> = -1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`RUNTIMEINCONSISTENCY` <span class="initializer"> = -2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DATAINCONSISTENCY` <span class="initializer"> = -3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CONNECTIONLOSS` <span class="initializer"> = -4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MARSHALLINGERROR` <span class="initializer"> = -5</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UNIMPLEMENTED` <span class="initializer"> = -6</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`OPERATIONTIMEOUT` <span class="initializer"> = -7</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`BADARGUMENTS` <span class="initializer"> = -8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`INVALIDSTATE` <span class="initializer"> = -9</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NEWCONFIGNOQUORUM` <span class="initializer"> = -13</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`RECONFIGINPROGRESS` <span class="initializer"> = -14</span> ;

<span class="modifier">const</span> <span class="type">int</span> `OK`
<span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`APIERROR` <span class="initializer"> = -100</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NONODE` <span class="initializer"> = -101</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOAUTH` <span class="initializer"> = -102</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`BADVERSION` <span class="initializer"> = -103</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOCHILDRENFOREPHEMERALS` <span class="initializer"> = -108</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NODEEXISTS` <span class="initializer"> = -110</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOTEMPTY` <span class="initializer"> = -111</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SESSIONEXPIRED` <span class="initializer"> = -112</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`INVALIDCALLBACK` <span class="initializer"> = -113</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`INVALIDACL` <span class="initializer"> = -114</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`AUTHFAILED` <span class="initializer"> = -115</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`CLOSING` <span class="initializer"> = -116</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOTHING` <span class="initializer"> = -117</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`SESSIONMOVED` <span class="initializer"> = -118</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOTREADONLY` <span class="initializer"> = -119</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`EPHEMERALONLOCALSESSION` <span class="initializer"> = -120</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`NOWATCHER` <span class="initializer"> = -121</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`RECONFIGDISABLED` <span class="initializer"> = -122</span> ;

}

Predefined Constants
--------------------

ZooKeeper Permissions
---------------------

**`Zookeeper::PERM_READ`**  
Can read nodes value and list its children

**`Zookeeper::PERM_WRITE`**  
Can set the nodes value

**`Zookeeper::PERM_CREATE`**  
Can create children

**`Zookeeper::PERM_DELETE`**  
Can delete children

**`Zookeeper::PERM_ADMIN`**  
Can execute set\_acl()

**`Zookeeper::PERM_ALL`**  
All of the above flags ORd together

ZooKeeper Create Flags
----------------------

**`Zookeeper::EPHEMERAL`**  
If Zookeeper::EPHEMERAL flag is set, the node will automatically get
removed if the client session goes away.

**`Zookeeper::SEQUENCE`**  
If the Zookeeper::SEQUENCE flag is set, a unique monotonically
increasing sequence number is appended to the path name. The sequence
number is always fixed length of 10 digits, 0 padded.

ZooKeeper Log Levels
--------------------

**`Zookeeper::LOG_LEVEL_ERROR`**  
Outputs only error mesages

**`Zookeeper::LOG_LEVEL_WARN`**  
Outputs errors/warnings

**`Zookeeper::LOG_LEVEL_INFO`**  
Outputs big action messages besides errors/warnings

**`Zookeeper::LOG_LEVEL_DEBUG`**  
Outputs all

ZooKeeper States
----------------

**`Zookeeper::EXPIRED_SESSION_STATE`**  
Connected but session expired

**`Zookeeper::AUTH_FAILED_STATE`**  
Connected but auth failed

**`Zookeeper::CONNECTING_STATE`**  
Connecting

**`Zookeeper::ASSOCIATING_STATE`**  
Associating

**`Zookeeper::CONNECTED_STATE`**  
Connected

**`Zookeeper::READONLY_STATE`**  
TODO: help us improve this extension.

**`Zookeeper::NOTCONNECTED_STATE`**  
Connection failed

ZooKeeper Watch Types
---------------------

**`Zookeeper::CREATED_EVENT`**  
A node has been created

This is only generated by watches on non-existent nodes. These watches
are set using Zookeeper::exists.

**`Zookeeper::DELETED_EVENT`**  
A node has been deleted

This is only generated by watches on nodes. These watches are set using
Zookeeper::exists and Zookeeper::get.

**`Zookeeper::CHANGED_EVENT`**  
A node has changed

This is only generated by watches on nodes. These watches are set using
Zookeeper::exists and Zookeeper::get.

**`Zookeeper::CHILD_EVENT`**  
A change as occurred in the list of children

This is only generated by watches on the child list of a node. These
watches are set using Zookeeper::getChildren.

**`Zookeeper::SESSION_EVENT`**  
A session has been lost

This is generated when a client loses contact or reconnects with a
server.

**`Zookeeper::NOTWATCHING_EVENT`**  
A watch has been removed

This is generated when the server for some reason, probably a resource
constraint, will no longer watch a node for a client.

ZooKeeper System and Server-side Errors
---------------------------------------

**`Zookeeper::SYSTEMERROR`**  
This is never thrown by the server, it shouldn't be used other than to
indicate a range. Specifically error codes greater than this value, but
lesser than Zookeeper::APIERROR, are system errors.

**`Zookeeper::RUNTIMEINCONSISTENCY`**  
A runtime inconsistency was found.

**`Zookeeper::DATAINCONSISTENCY`**  
A data inconsistency was found.

**`Zookeeper::CONNECTIONLOSS`**  
Connection to the server has been lost.

**`Zookeeper::MARSHALLINGERROR`**  
Error while marshalling or unmarshalling data.

**`Zookeeper::UNIMPLEMENTED`**  
Operation is unimplemented.

**`Zookeeper::OPERATIONTIMEOUT`**  
Operation timeout.

**`Zookeeper::BADARGUMENTS`**  
Invalid arguments.

**`Zookeeper::INVALIDSTATE`**  
Invliad zhandle state.

**`Zookeeper::NEWCONFIGNOQUORUM`**  
No quorum of new config is connected and up-to-date with the leader of
last committed config - try invoking reconfiguration after new servers
are connected and synced.

Available as of ZooKeeper 3.5.0

**`Zookeeper::RECONFIGINPROGRESS`**  
Reconfiguration requested while another reconfiguration is currently in
progress. This is currently not supported. Please retry.

Available as of ZooKeeper 3.5.0

ZooKeeper API Errors
--------------------

**`Zookeeper::OK`**  
Everything is OK.

**`Zookeeper::APIERROR`**  
This is never thrown by the server, it shouldn't be used other than to
indicate a range. Specifically error codes greater than this value are
API errors (while values less than this indicate a
Zookeeper::SYSTEMERROR).

**`Zookeeper::NONODE`**  
Node does not exist.

**`Zookeeper::NOAUTH`**  
Not authenticated.

**`Zookeeper::BADVERSION`**  
Version conflict.

**`Zookeeper::NOCHILDRENFOREPHEMERALS`**  
Ephemeral nodes may not have children.

**`Zookeeper::NODEEXISTS`**  
The node already exists.

**`Zookeeper::NOTEMPTY`**  
The node has children.

**`Zookeeper::SESSIONEXPIRED`**  
The session has been expired by the server.

**`Zookeeper::INVALIDCALLBACK`**  
Invalid callback specified.

**`Zookeeper::INVALIDACL`**  
Invalid ACL specified.

**`Zookeeper::AUTHFAILED`**  
Client authentication failed.

**`Zookeeper::CLOSING`**  
ZooKeeper is closing.

**`Zookeeper::NOTHING`**  
(not error) No server responses to process.

**`Zookeeper::SESSIONMOVED`**  
Session moved to another server, so operation is ignored.

**`Zookeeper::NOTREADONLY`**  
State-changing request is passed to read-only server.

**`Zookeeper::EPHEMERALONLOCALSESSION`**  
Attempt to create ephemeral node on a local session.

**`Zookeeper::NOWATCHER`**  
The watcher couldn't be found.

**`Zookeeper::RECONFIGDISABLED`**  
Attempts to perform a reconfiguration operation when reconfiguration
feature is disabled.

Zookeeper::addAuth
==================

Specify application credentials

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::addAuth</span> ( <span
class="methodparam"><span class="type">string</span> `$scheme`</span> ,
<span class="methodparam"><span class="type">string</span>
`$cert`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$completion_cb`<span class="initializer">
= **`null`**</span></span> \] )

The application calls this function to specify its credentials for
purposes of authentication. The server will use the security provider
specified by the scheme parameter to authenticate the client connection.
If the authentication request has failed: - the server connection is
dropped. - the watcher is called with the ZOO\_AUTH\_FAILED\_STATE value
as the state parameter.

### Parameters

`scheme`  
The id of authentication scheme. Natively supported: "digest"
password-based authentication

`cert`  
Application credentials. The actual value depends on the scheme.

`completion_cb`  
The routine to invoke when the request completes. One of the following
result codes may be passed into the completion callback: - ZOK operation
completed successfully - ZAUTHFAILED authentication failed

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or operation fails.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::addAuth</span>
example**

Add auth before requesting node value.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/path/to/node';
$value = 'nodevalue';
$zookeeper->set($path, $value);

$zookeeper->addAuth('digest', 'user0:passwd0');
$r = $zookeeper->get($path);
if ($r)
  echo $r;
else
  echo 'ERR';
?>
```

The above example will output:

    nodevalue

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::setAcl</span>
-   <span class="methodname">Zookeeper::getAcl</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20States" class="link">ZooKeeper States</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::close
================

Close the zookeeper handle and free up any resources

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Zookeeper::close</span> ( <span
class="methodparam">void</span> )

### Errors/Exceptions

This method emits <span class="classname">ZookeeperException</span> and
it's derivatives when closing an uninitialized instance.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::connect
==================

Create a handle to used communicate with zookeeper

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Zookeeper::connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$recv_timeout`<span class="initializer"> = 10000</span></span> \]\] )

This method creates a new handle and a zookeeper session that
corresponds to that handle. Session establishment is asynchronous,
meaning that the session should not be considered established until (and
unless) an event of state ZOO\_CONNECTED\_STATE is received.

### Parameters

`host`  
Comma separated host:port pairs, each corresponding to a zk server. e.g.
"127.0.0.1:3000,127.0.0.1:3001,127.0.0.1:3002"

`watcher_cb`  
The global watcher callback function. When notifications are triggered
this function will be invoked.

`recv_timeout`  
The timeout for this session, only valid if the connections is currently
connected (ie. last watcher state is ZOO\_CONNECTED\_STATE).

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or could not init instance.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::\_\_construct
========================

Create a handle to used communicate with zookeeper

### Description

<span class="modifier">public</span> <span
class="methodname">Zookeeper::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`<span
class="initializer"> = ''</span></span> \[, <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$recv_timeout`<span class="initializer"> = 10000</span></span> \]\]\] )

This method creates a new handle and a zookeeper session that
corresponds to that handle. Session establishment is asynchronous,
meaning that the session should not be considered established until (and
unless) an event of state ZOO\_CONNECTED\_STATE is received.

### Parameters

`host`  
comma separated host:port pairs, each corresponding to a zk server. e.g.
"127.0.0.1:3000,127.0.0.1:3001,127.0.0.1:3002"

`watcher_cb`  
the global watcher callback function. When notifications are triggered
this function will be invoked.

`recv_timeout`  
the timeout for this session, only valid if the connections is currently
connected (ie. last watcher state is ZOO\_CONNECTED\_STATE).

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or could not init instance.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::connect</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::create
=================

Create a node synchronously

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Zookeeper::create</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> , <span class="methodparam"><span
class="type">array</span> `$acls`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`null`**</span></span> \] )

This method will create a node in ZooKeeper. A node can only be created
if it does not already exists. The Create Flags affect the creation of
nodes. If ZOO\_EPHEMERAL flag is set, the node will automatically get
removed if the client session goes away. If the ZOO\_SEQUENCE flag is
set, a unique monotonically increasing sequence number is appended to
the path name.

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`value`  
The data to be stored in the node.

`acls`  
The initial ACL of the node. The ACL must not be null or empty.

`flags`  
this parameter can be set to 0 for normal create or an OR of the Create
Flags

### Return Values

Returns the path of the new node (this might be different than the
supplied path because of the ZOO\_SEQUENCE flag) on success, and false
on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to create node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::create</span>
example**

Create a new node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$aclArray = array(
  array(
    'perms'  => Zookeeper::PERM_ALL,
    'scheme' => 'world',
    'id'     => 'anyone',
  )
);
$path = '/path/to/newnode';
$realPath = $zookeeper->create($path, null, $aclArray);
if ($realPath)
  echo $realPath;
else
  echo 'ERR';
?>
```

The above example will output:

    /path/to/newnode

### See Also

-   <span class="methodname">Zookeeper::delete</span>
-   <span class="methodname">Zookeeper::getChildren</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20Permissions" class="link">ZooKeeper Permissions</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::delete
=================

Delete a node in zookeeper synchronously

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::delete</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \] )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`version`  
The expected version of the node. The function will fail if the actual
version of the node does not match the expected version. If -1 is used
the version check will not take place.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to delete node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::delete</span>
example**

Delete a existing node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/path/to/node';
$r = $zookeeper->delete($path);
if ($r)
  echo 'SUCCESS';
else
  echo 'ERR';
?>
```

The above example will output:

    SUCCESS

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::getChildren</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::exists
=================

Checks the existence of a node in zookeeper synchronously

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Zookeeper::exists</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \] )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`watcher_cb`  
if nonzero, a watch will be set at the server to notify the client if
the node changes. The watch will be set even if the node does not

### Return Values

Returns the value of stat for the path if the given node exists,
otherwise false.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to check the existence of a node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::exists</span>
example**

Check the existence of a node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/path/to/node';
$r = $zookeeper->exists($path);
if ($r)
  echo 'EXISTS';
else
  echo 'N/A or ERR';
?>
```

The above example will output:

    EXISTS

### See Also

-   <span class="methodname">Zookeeper::get</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::get
==============

Gets the data associated with a node synchronously

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Zookeeper::get</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$max_size`<span
class="initializer"> = 0</span></span> \]\]\] )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`watcher_cb`  
If nonzero, a watch will be set at the server to notify the client if
the node changes.

`stat`  
If not NULL, will hold the value of stat for the path on return.

`max_size`  
Max size of the data. If 0 is used, this method will return the whole
data.

### Return Values

Returns the data on success, and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to get value from node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::get</span> example**

Get value from node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/path/to/node';
$value = 'nodevalue';
$zookeeper->set($path, $value);

$r = $zookeeper->get($path);
if ($r)
  echo $r;
else
  echo 'ERR';
?>
```

The above example will output:

    nodevalue

**Example \#2 <span class="methodname">Zookeeper::get</span> stat
example**

Get node stat info.

``` php
<?php
$zookeeper = new Zookeeper('localhost:2181');
$path = '/path/to/node';
$stat = [];
$zookeeper->get($path, null, $stat);
var_dump($stat);
?>
```

The above example will output:

    array(11) {
      ["czxid"]=>
      float(0)
      ["mzxid"]=>
      float(0)
      ["ctime"]=>
      float(0)
      ["mtime"]=>
      float(0)
      ["version"]=>
      int(0)
      ["cversion"]=>
      int(-2)
      ["aversion"]=>
      int(0)
      ["ephemeralOwner"]=>
      float(0)
      ["dataLength"]=>
      int(0)
      ["numChildren"]=>
      int(2)
      ["pzxid"]=>
      float(0)
    }

### See Also

-   <span class="methodname">Zookeeper::set</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::getAcl
=================

Gets the acl associated with a node synchronously

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Zookeeper::getAcl</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

### Return Values

Return acl array on success and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to get ACL of a node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::getAcl</span>
example**

Get ACL of a node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$aclArray = array(
  array(
    'perms'  => Zookeeper::PERM_ALL,
    'scheme' => 'world',
    'id'     => 'anyone',
  )
);
$path = '/path/to/newnode';
$zookeeper->setAcl($path, $aclArray);

$r = $zookeeper->getAcl($path);
if ($r)
  var_dump($r);
else
  echo 'ERR';
?>
```

The above example will output:

    array(1) {
      [0]=>
      array(3) {
        ["perms"]=>
        int(31)
        ["scheme"]=>
        string(5) "world"
        ["id"]=>
        string(6) "anyone"
      }
    }

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::setAcl</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20Permissions" class="link">ZooKeeper Permissions</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::getChildren
======================

Lists the children of a node synchronously

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Zookeeper::getChildren</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \] )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`watcher_cb`  
If nonzero, a watch will be set at the server to notify the client if
the node changes.

### Return Values

Returns an array with children paths on success, and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to list children of a node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::getChildren</span>
example**

Lists children of a node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/zookeeper';
$r = $zookeeper->getchildren($path);
if ($r)
  var_dump($r);
else
  echo 'ERR';
?>
```

The above example will output:

    array(1) {
      [0]=>
      string(6) "config"
    }

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::delete</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::getClientId
======================

Return the client session id, only valid if the connections is currently
connected (ie. last watcher state is ZOO\_CONNECTED\_STATE)

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Zookeeper::getClientId</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns the client session id on success, and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when it could not get client session
id.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="methodname">Zookeeper::getState</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20States" class="link">ZooKeeper States</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::getConfig
====================

Get instance of ZookeeperConfig

### Description

<span class="modifier">public</span> <span
class="type">ZookeeperConfig</span> <span
class="methodname">Zookeeper::getConfig</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns instance of ZookeeperConfig.

### See Also

-   <span class="classname">ZookeeperConfig</span>

Zookeeper::getRecvTimeout
=========================

Return the timeout for this session, only valid if the connections is
currently connected (ie. last watcher state is ZOO\_CONNECTED\_STATE).
This value may change after a server re-connect

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Zookeeper::getRecvTimeout</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns the timeout for this session on success, and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when operation fails.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::getState
===================

Get the state of the zookeeper connection

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Zookeeper::getState</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns the state of zookeeper connection on success, and false on
failure.

### Errors/Exceptions

This method emits PHP error/warning when it fails to get state of
zookeeper connection.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="methodname">Zookeeper::getClientId</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20States" class="link">ZooKeeper States</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::isRecoverable
========================

Checks if the current zookeeper connection state can be recovered

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::isRecoverable</span> ( <span
class="methodparam">void</span> )

The application must close the handle and try to reconnect.

### Return Values

Returns true/false on success, and false on failure.

### Errors/Exceptions

This method emits PHP error/warning when operation fails.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="methodname">Zookeeper::getClientId</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20States" class="link">ZooKeeper States</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::set
==============

Sets the data associated with a node

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::set</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$version`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">array</span> `&$stat`<span class="initializer"> =
**`null`**</span></span> \]\] )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`value`  
The data to be stored in the node.

`version`  
The expected version of the node. The function will fail if the actual
version of the node does not match the expected version. If -1 is used
the version check will not take place.

`stat`  
If not NULL, will hold the value of stat for the path on return.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to save value to node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::set</span> example**

Save value to node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$path = '/path/to/node';
$value = 'nodevalue';
$r = $zookeeper->set($path, $value);
if ($r)
  echo 'SUCCESS';
else
  echo 'ERR';
?>
```

The above example will output:

    SUCCESS

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::get</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::setAcl
=================

Sets the acl associated with a node synchronously

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::setAcl</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">int</span>
`$version`</span> , <span class="methodparam"><span
class="type">array</span> `$acl`</span> )

### Parameters

`path`  
The name of the node. Expressed as a file name with slashes separating
ancestors of the node.

`version`  
The expected version of the path.

`acl`  
The acl to be set on the path.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to set ACL for a node.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::setAcl</span>
example**

Set ACL for a node.

``` php
<?php
$zookeeper = new Zookeeper('locahost:2181');
$aclArray = array(
  array(
    'perms'  => Zookeeper::PERM_ALL,
    'scheme' => 'world',
    'id'     => 'anyone',
  )
);
$path = '/path/to/newnode';
$zookeeper->setAcl($path, $aclArray);

$r = $zookeeper->getAcl($path);
if ($r)
  var_dump($r);
else
  echo 'ERR';
?>
```

The above example will output:

    array(1) {
      [0]=>
      array(3) {
        ["perms"]=>
        int(31)
        ["scheme"]=>
        string(5) "world"
        ["id"]=>
        string(6) "anyone"
      }
    }

### See Also

-   <span class="methodname">Zookeeper::create</span>
-   <span class="methodname">Zookeeper::getAcl</span>
-   <a href="/class/zookeeper.html#ZooKeeper%20Permissions" class="link">ZooKeeper Permissions</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::setDebugLevel
========================

Sets the debugging level for the library

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Zookeeper::setDebugLevel</span> ( <span
class="methodparam"><span class="type">int</span> `$logLevel`</span> )

### Parameters

`logLevel`  
ZooKeeper log level constants.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to set debug level.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### Examples

**Example \#1 <span class="methodname">Zookeeper::setDebugLevel</span>
example**

Set debugl level.

``` php
<?php
$r = Zookeeper::setDebugLevel(Zookeeper::LOG_LEVEL_WARN);
if ($r)
  echo 'SUCCESS';
else
  echo 'ERR';
?>
?>
```

The above example will output:

    SUCCESS

### See Also

-   <a href="/class/zookeeper.html#ZooKeeper%20Log%20Levels" class="link">ZooKeeper Log Levels</a>
-   <span class="classname">ZookeeperException</span>

Zookeeper::setDeterministicConnOrder
====================================

Enable/disable quorum endpoint order randomization

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Zookeeper::setDeterministicConnOrder</span> ( <span
class="methodparam"><span class="type">bool</span> `$yesOrNo`</span> )

If passed a true value, will make the client connect to quorum peers in
the order as specified in the zookeeper\_init() call. A false value
causes zookeeper\_init() to permute the peer endpoints which is good for
more even client connection distribution among the quorum peers.
ZooKeeper C Client uses false by default.

### Parameters

`yesOrNo`  
Disable/enable quorum endpoint order randomization.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or operation fails.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::\_\_construct</span>
-   <span class="methodname">Zookeeper::connect</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::setLogStream
=======================

Sets the stream to be used by the library for logging

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::setLogStream</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

The zookeeper library uses stderr as its default log stream. Application
must make sure the stream is writable. Passing in NULL resets the stream
to its default value (stderr).

### Parameters

`stream`  
The stream to be used by the library for logging.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or operation fails.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::setDebugLevel</span>
-   <span class="classname">ZookeeperException</span>

Zookeeper::setWatcher
=====================

Set a watcher function

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Zookeeper::setWatcher</span> ( <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`</span> )

### Parameters

`watcher_cb`  
A watch will be set at the server to notify the client if the node
changes.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Errors/Exceptions

This method emits PHP error/warning when parameters count or types are
wrong or fail to set watcher.

**Caution**

Since version 0.3.0, this method emits <span
class="classname">ZookeeperException</span> and it's derivatives.

### See Also

-   <span class="methodname">Zookeeper::exists</span>
-   <span class="methodname">Zookeeper::get</span>
-   <span class="classname">ZookeeperException</span>

Introduction
------------

The ZooKeeper Config handling class.

Class synopsis
--------------

**ZookeeperConfig**

<span class="ooclass"> class **ZookeeperConfig** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">string</span> `$members`</span> \[, <span
class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">get</span> (\[ <span class="methodparam"><span
class="type">callable</span> `$watcher_cb`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">array</span> `&$stat`<span class="initializer"> =
**`null`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">remove</span> ( <span class="methodparam"><span
class="type">string</span> `$id_list`</span> \[, <span
class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">set</span> ( <span class="methodparam"><span
class="type">string</span> `$members`</span> \[, <span
class="methodparam"><span class="type">int</span> `$version`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

}

ZookeeperConfig::add
====================

Add servers to the ensemble

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ZookeeperConfig::add</span> ( <span
class="methodparam"><span class="type">string</span> `$members`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$version`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

### Parameters

`members`  
Comma separated list of servers to be added to the ensemble. Each has a
configuration line for a server to be added (as would appear in a
configuration file), only for maj. quorums.

`version`  
The expected version of the node. The function will fail if the actual
version of the node does not match the expected version. If -1 is used
the version check will not take place.

`stat`  
If not NULL, will hold the value of stat for the path on return.

### Errors/Exceptions

This method emits <span class="classname">ZookeeperException</span> and
it's derivatives when parameters count or types are wrong or fail to
save value to node.

### Examples

**Example \#1 <span class="methodname">ZookeeperConfig::add</span>
example**

Add members.

``` php
<?php
$client = new Zookeeper();
$client->connect('localhost:2181');
$client->addAuth('digest', 'timandes:timandes');
$zkConfig = $client->getConfig();
$zkConfig->set("server.1=localhost:2888:3888:participant;0.0.0.0:2181");
$zkConfig->add("server.2=localhost:2889:3889:participant;0.0.0.0:2182");
$r = $zkConfig->get();
if ($r)
  echo $r;
else
  echo 'ERR';
?>
```

The above example will output:

    server.1=localhost:2888:3888:participant;0.0.0.0:2181
    server.2=localhost:2889:3889:participant;0.0.0.0:2182
    version=0xca01e881a2

### See Also

-   <span class="methodname">ZookeeperConfig::get</span>
-   <span class="methodname">ZookeeperConfig::set</span>
-   <span class="methodname">ZookeeperConfig::remove</span>
-   <span class="classname">ZookeeperException</span>

ZookeeperConfig::get
====================

Gets the last committed configuration of the ZooKeeper cluster as it is
known to the server to which the client is connected, synchronously

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ZookeeperConfig::get</span> (\[ <span
class="methodparam"><span class="type">callable</span>
`$watcher_cb`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

### Parameters

`watcher_cb`  
If nonzero, a watch will be set at the server to notify the client if
the node changes.

`stat`  
If not NULL, will hold the value of stat for the path on return.

### Return Values

Returns the configuration string on success, and false on failure.

### Errors/Exceptions

This method emits <span class="classname">ZookeeperException</span> and
it's derivatives when parameters count or types are wrong or fail to get
configuration.

### Examples

**Example \#1 <span class="methodname">ZookeeperConfig::get</span>
example**

Get configuration.

``` php
<?php
$zk = new Zookeeper();
$zk->connect('localhost:2181');
$zk->addAuth('digest', 'timandes:timandes');
$zkConfig = $zk->getConfig();
$r = $zkConfig->get();
if ($r)
  echo $r;
else
  echo 'ERR';
?>
```

The above example will output:

    server.1=localhost:2888:3888:participant;0.0.0.0:2181
    version=0xca01e881a2

### See Also

-   <span class="methodname">ZookeeperConfig::set</span>
-   <span class="methodname">ZookeeperConfig::add</span>
-   <span class="methodname">ZookeeperConfig::remove</span>
-   <span class="classname">ZookeeperException</span>

ZookeeperConfig::remove
=======================

Remove servers from the ensemble

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ZookeeperConfig::remove</span> ( <span
class="methodparam"><span class="type">string</span> `$id_list`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$version`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

### Parameters

`id_list`  
Comma separated list of server IDs to be removed from the ensemble. Each
has an id of a server to be removed, only for maj. quorums.

`version`  
The expected version of the node. The function will fail if the actual
version of the node does not match the expected version. If -1 is used
the version check will not take place.

`stat`  
If not NULL, will hold the value of stat for the path on return.

### Errors/Exceptions

This method emits <span class="classname">ZookeeperException</span> and
it's derivatives when parameters count or types are wrong or fail to
save value to node.

### Examples

**Example \#1 <span class="methodname">ZookeeperConfig::remove</span>
example**

Remove members.

``` php
<?php
$client = new Zookeeper();
$client->connect('localhost:2181');
$client->addAuth('digest', 'timandes:timandes');
$zkConfig = $client->getConfig();
$zkConfig->set("server.1=localhost:2888:3888:participant;0.0.0.0:2181,server.2=localhost:2889:3889:participant;0.0.0.0:2182");
$zkConfig->remove("2");
echo $zkConfig->get();
if ($r)
  echo $r;
else
  echo 'ERR';
?>
```

The above example will output:

    server.1=localhost:2888:3888:participant;0.0.0.0:2181
    version=0xca01e881a2

### See Also

-   <span class="methodname">ZookeeperConfig::get</span>
-   <span class="methodname">ZookeeperConfig::add</span>
-   <span class="methodname">ZookeeperConfig::set</span>
-   <span class="classname">ZookeeperException</span>

ZookeeperConfig::set
====================

Change ZK cluster ensemble membership and roles of ensemble peers

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ZookeeperConfig::set</span> ( <span
class="methodparam"><span class="type">string</span> `$members`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$version`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$stat`<span
class="initializer"> = **`null`**</span></span> \]\] )

### Parameters

`members`  
Comma separated list of new membership (e.g., contents of a membership
configuration file) - for use only with a non-incremental
reconfiguration.

`version`  
The expected version of the node. The function will fail if the actual
version of the node does not match the expected version. If -1 is used
the version check will not take place.

`stat`  
If not NULL, will hold the value of stat for the path on return.

### Errors/Exceptions

This method emits <span class="classname">ZookeeperException</span> and
it's derivatives when parameters count or types are wrong or fail to
save value to node.

### Examples

**Example \#1 <span class="methodname">ZookeeperConfig::set</span>
example**

Reconfig.

``` php
<?php
$client = new Zookeeper();
$client->connect('localhost:2181');
$client->addAuth('digest', 'timandes:timandes');
$zkConfig = $client->getConfig();
$zkConfig->set("server.1=localhost:2888:3888:participant;0.0.0.0:2181");
?>
```

### See Also

-   <span class="methodname">ZookeeperConfig::get</span>
-   <span class="methodname">ZookeeperConfig::add</span>
-   <span class="methodname">ZookeeperConfig::remove</span>
-   <span class="classname">ZookeeperException</span>

Introduction
------------

The ZooKeeper exception handling class.

Class synopsis
--------------

**ZookeeperException**

<span class="ooclass"> class **ZookeeperException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper authentication exception handling class.

Class synopsis
--------------

**ZookeeperAuthenticationException**

<span class="ooclass"> class **ZookeeperAuthenticationException**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper connection exception handling class.

Class synopsis
--------------

**ZookeeperConnectionException**

<span class="ooclass"> class **ZookeeperConnectionException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper exception (while marshalling or unmarshalling data)
handling class.

Class synopsis
--------------

**ZookeeperMarshallingException**

<span class="ooclass"> class **ZookeeperMarshallingException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper exception (when node does not exist) handling class.

Class synopsis
--------------

**ZookeeperNoNodeException**

<span class="ooclass"> class **ZookeeperNoNodeException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper operation timeout exception handling class.

Class synopsis
--------------

**ZookeeperOperationTimeoutException**

<span class="ooclass"> class **ZookeeperOperationTimeoutException**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

The ZooKeeper session exception handling class.

Class synopsis
--------------

**ZookeeperSessionException**

<span class="ooclass"> class **ZookeeperSessionException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ZookeeperException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}
