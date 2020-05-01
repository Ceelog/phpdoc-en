The inotify extension exposes the inotify functions <span
class="function">inotify\_init</span>, <span
class="function">inotify\_add\_watch</span> and <span
class="function">inotify\_rm\_watch</span>.

As the C <span class="function">inotify\_init</span> function returns a
file descriptor, PHP's <span class="function">inotify\_init</span>
returns a stream resource, usable with standard stream functions, like
<span class="function">stream\_select</span>, <span
class="function">stream\_set\_blocking</span> and <span
class="function">fclose</span>. <span
class="function">inotify\_read</span> replaces the C way of reading
inotify events.
