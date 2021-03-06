Dealing with XForms
===================

<a href="http://www.w3.org/MarkUp/Forms/" class="link external">» XForms</a>
defines a variation on traditional webforms which allows them to be used
on a wider variety of platforms and browsers or even non-traditional
media such as PDF documents.

The first key difference in XForms is how the form is sent to the
client.
<a href="http://www.w3.org/MarkUp/Forms/2003/xforms-for-html-authors.html" class="link external">» <em>XForms for HTML Authors</em></a>
contains a detailed description of how to create XForms, for the purpose
of this tutorial we'll only be looking at a simple example.

**Example \#1 A simple XForms search form**

``` html
<h:html xmlns:h="http://www.w3.org/1999/xhtml"
        xmlns="http://www.w3.org/2002/xforms">
<h:head>
 <h:title>Search</h:title>
 <model>
  <submission action="http://example.com/search"
              method="post" id="s"/>
 </model>
</h:head>
<h:body>
 <h:p>
  <input ref="q"><label>Find</label></input>
  <submit submission="s"><label>Go</label></submit>
 </h:p>
</h:body>
</h:html>
```

The above form displays a text input box (named `q`), and a submit
button. When the submit button is clicked, the form will be sent to the
page referred to by *action*.

Here's where it starts to look different from your web application's
point of view. In a normal HTML form, the data would be sent as
*application/x-www-form-urlencoded*, in the XForms world however, this
information is sent as XML formatted data.

If you're choosing to work with XForms then you probably want that data
as XML, in that case, look in `$HTTP_RAW_POST_DATA` where you'll find
the XML document generated by the browser which you can pass into your
favorite XSLT engine or document parser.

If you're not interested in formatting and just want your data to be
loaded into the traditional `$_POST` variable, you can instruct the
client browser to send it as *application/x-www-form-urlencoded* by
changing the `method` attribute to *urlencoded-post*.

**Example \#2 Using an XForm to populate `$_POST`**

``` html
<h:html xmlns:h="http://www.w3.org/1999/xhtml"
        xmlns="http://www.w3.org/2002/xforms">
<h:head>
 <h:title>Search</h:title>
 <model>
  <submission action="http://example.com/search"
              method="urlencoded-post" id="s"/>
 </model>
</h:head>
<h:body>
 <h:p>
  <input ref="q"><label>Find</label></input>
  <submit submission="s"><label>Go</label></submit>
 </h:p>
</h:body>
</h:html>
```

> **Note**: <span class="simpara"> As of this writing, many browsers do
> not support XForms. Check your browser version if the above examples
> fails. </span>
