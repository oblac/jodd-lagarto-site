---
description: Available selectors
---

# Selectors

The list of default selectors supported by **CSSelly**:

* `*` any element
* `E` an element of type E
* `E[foo]` an E element with a "foo" attribute
* `E[foo="bar"]` an E element whose "foo" attribute value is exactly equal to "bar"
* `E[foo~="bar"]` an E element whose "foo" attribute value is a list of whitespace-separated values, one of which is exactly equal to "bar"
* `E[foo^="bar"]` an E element whose "foo" attribute value begins exactly with the string "bar"
* `E[foo$="bar"]` an E element whose "foo" attribute value ends exactly with the string "bar"
* `E[foo*="bar"]` an E element whose "foo" attribute value contains the substring "bar"
* `E[foo|="en"]` an E element whose "foo" attribute has a hyphen-separated list of values beginning \(from the left\) with "en"
* `E:root` an E element, root of the document
* `E:nth-child(n)` an E element, the n-th child of its parent
* `E:nth-last-child(n)` an E element, the n-th child of its parent, counting from the last one
* `E:nth-of-type(n)` an E element, the n-th sibling of its type
* `E:nth-last-of-type(n)` an E element, the n-th sibling of its type, counting from the last one
* `E:first-child` an E element, first child of its parent
* `E:last-child` an E element, last child of its parent
* `E:first-of-type` an E element, first sibling of its type
* `E:last-of-type` an E element, last sibling of its type
* `E:only-child` an E element, only child of its parent
* `E:only-of-type` an E element, only sibling of its type
* `E:empty` an E element that has no children \(including text nodes\)
* `E#myid` an E element with ID equal to “myid”.
* `E F` an F element descendant of an E element
* `E > F` an F element child of an E element
* `E + F` an F element immediately preceded by an E element
* `E ~ F` an F element preceded by an E element

The list of additional pseudo-classes and pseudo-functions supported by **CSSelly**:

* `:first`
* `:last`
* `:button`
* `:checkbox`
* `:file`
* `:header`
* `:image`
* `:input`
* `:parent`
* `:password`
* `:radio`
* `:reset`
* `:selected`
* `:checked`
* `:submit`
* `:text`
* `:even`
* `:odd`
* `:eq(n)`
* `:gt(n)`
* `:lt(n)`
* `:contains(text)`

