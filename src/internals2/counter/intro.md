Introduction
------------

The "counter" extension provides any number of counters to PHP code
using it which reset at times determined by the caller.

There are three interfaces to "counter": basic, extended, and objective.
The basic interface provides a single counter controlled by INI settings
and function calls. The extended interface provides an arbitrary number
of named counter resources which may optionally persist beyond the
lifetime of a single PHP request. The objective interface combines both
the basic and extended interfaces into a <span
class="classname">Counter</span> class.
