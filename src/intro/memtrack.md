The purpose of this extension is to detect the most memory hungry
scripts and functions.

memtrack tracks memory consumption in PHP scripts and produces reports
(warnings) when the consumption reaches certain levels set by the user.
This is achieved by replacing default executor function by a special
function which compares memory usage before and after running the
original executor - this way we can tell how much the memory usage has
changed during the execution of the current part of the code.

Zend Engine runs its executor for each opcode array (op\_array), which
usually means function, plain script and such, so memtrack doesn't have
any noticeable effect on performance.

memtrack doesn't provide any functions, there are only INI directives
which allow you to configure the way it should work.

**Warning**

This extension is *EXPERIMENTAL*. The behaviour of this extension
including the names of its functions and any other documentation
surrounding this extension may change without notice in a future release
of PHP. This extension should be used at your own risk.
