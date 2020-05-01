Case Folding
============

The element handler functions may get their element names <span
class="glossterm">case-folded</span>. Case-folding is defined as "a
process applied to a sequence of characters, in which those identified
as non-uppercase are replaced by their uppercase equivalents". In other
words, when it comes to XML, case-folding simply means uppercasing.

By default, all the element names that are passed to the handler
functions are case-folded. This behaviour can be queried and controlled
per XML parser with the <span
class="function">xml\_parser\_get\_option</span> and <span
class="function">xml\_parser\_set\_option</span> functions,
respectively.
