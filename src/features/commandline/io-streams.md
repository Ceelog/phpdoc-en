Input/output streams
--------------------

The CLI SAPI defines a few constants for I/O streams to make programming
for the command line a bit easier.

<table>
<caption><strong>CLI specific Constants</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Constant</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>STDIN</code></strong></td>
<td><p>An already opened stream to <em>stdin</em>. This saves opening it with</p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb1"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb1-1"><a href="#cb1-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb1-2"><a href="#cb1-2"></a><span class="kw">$stdin</span> = <span class="fu">fopen</span><span class="ot">(</span><span class="st">&#39;php://stdin&#39;</span><span class="ot">,</span> <span class="st">&#39;r&#39;</span><span class="ot">);</span></span>
<span id="cb1-3"><a href="#cb1-3"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div>
If you want to read single line from <em>stdin</em>, you can use
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb2"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb2-1"><a href="#cb2-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb2-2"><a href="#cb2-2"></a><span class="kw">$line</span> = <span class="fu">trim</span><span class="ot">(</span><span class="fu">fgets</span><span class="ot">(</span><span class="kw">STDIN</span><span class="ot">));</span> <span class="co">// reads one line from STDIN</span></span>
<span id="cb2-3"><a href="#cb2-3"></a><span class="fu">fscanf</span><span class="ot">(</span><span class="kw">STDIN</span><span class="ot">,</span> <span class="st">&quot;%d</span><span class="kw">\n</span><span class="st">&quot;</span><span class="ot">,</span> <span class="kw">$number</span><span class="ot">);</span> <span class="co">// reads number from STDIN</span></span>
<span id="cb2-4"><a href="#cb2-4"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div></td>
</tr>
<tr class="even">
<td><strong><code>STDOUT</code></strong></td>
<td><p>An already opened stream to <em>stdout</em>. This saves opening it with</p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb3"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb3-1"><a href="#cb3-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb3-2"><a href="#cb3-2"></a><span class="kw">$stdout</span> = <span class="fu">fopen</span><span class="ot">(</span><span class="st">&#39;php://stdout&#39;</span><span class="ot">,</span> <span class="st">&#39;w&#39;</span><span class="ot">);</span></span>
<span id="cb3-3"><a href="#cb3-3"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div></td>
</tr>
<tr class="odd">
<td><strong><code>STDERR</code></strong></td>
<td><p>An already opened stream to <em>stderr</em>. This saves opening it with</p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb4"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb4-1"><a href="#cb4-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb4-2"><a href="#cb4-2"></a><span class="kw">$stderr</span> = <span class="fu">fopen</span><span class="ot">(</span><span class="st">&#39;php://stderr&#39;</span><span class="ot">,</span> <span class="st">&#39;w&#39;</span><span class="ot">);</span></span>
<span id="cb4-3"><a href="#cb4-3"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div></td>
</tr>
</tbody>
</table>

Given the above, you don't need to open e.g. a stream for *stderr*
yourself but simply use the constant instead of the stream resource:

``` shell
php -r 'fwrite(STDERR, "stderr\n");'
```

You do not need to explicitly close these streams, as they are closed
automatically by PHP when your script ends.

> **Note**:
>
> These constants are not available if reading the PHP script from
> *stdin*.
