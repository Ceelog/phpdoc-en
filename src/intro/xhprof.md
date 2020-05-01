XHProf is a light-weight hierarchical and instrumentation based
profiler. During the data collection phase, it keeps track of call
counts and inclusive metrics for arcs in the dynamic callgraph of a
program. It computes exclusive metrics in the reporting/post processing
phase, such as wall (elapsed) time, CPU time and memory usage. A
functions profile can be broken down by callers or callees. XHProf
handles recursive functions by detecting cycles in the callgraph at data
collection time itself and avoiding the cycles by giving unique depth
qualified names for the recursive invocations.

XHProf includes a simple HTML based user interface (written in PHP). The
browser based UI for viewing profiler results makes it easy to view
results or to share results with peers. A callgraph image view is also
supported.

XHProf reports can often be helpful in understanding the structure of
the code being executed. The hierarchical nature of the reports can be
used to determine, for example, what chain of calls led to a particular
function getting called.

XHProf supports ability to compare two runs (a.k.a. "diff" reports) or
aggregate data from multiple runs. Diff and aggregate reports, much like
single run reports, offer "flat" as well as "hierarchical" views of the
profile.

Additional documentation can be found via the
<a href="http://web.archive.org/web/20110514095512/http://mirror.facebook.net/facebook/xhprof/doc.html" class="link external">» facebook xhprof</a>
website.
