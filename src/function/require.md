require
-------

*require* is identical to <span class="function">include</span> except
upon failure it will also produce a fatal **`E_COMPILE_ERROR`** level
error. In other words, it will halt the script whereas <span
class="function">include</span> only emits a warning (**`E_WARNING`**)
which allows the script to continue.

See the <span class="function">include</span> documentation for how this
works.
