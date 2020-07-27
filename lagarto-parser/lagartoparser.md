---
description: Fast event-based HTML parser
---

# LagartoParser

**LagartoParser** is an _event-based_ HTML parser. It processes the input and emits events as they are parsed, using a [visitor pattern](https://en.wikipedia.org/wiki/Visitor_pattern).  This makes parsing very fast and memory-usage is minimal. However, sometimes event-based parsing can be tedious; in that case, try **LagartoDom** parser. 

Let's see it in action:

```java
LagartoParser lagartoParser = new LagartoParser(htmlContent);
TagVisitor tagVisitor = new MyTagVisitor();
lagartoParser.parse(tagVisitor);
```

As the input content is parsed, the callback methods in `MyTagVisitor`are invoked.

### Parsing specification

HTML Parsing is done strictly by the official [HTML5 specification](https://html.spec.whatwg.org). Note the following:

* the text is emitted as a single block of text and not one by one character.
* the case of a tag name \(and other tokens\) is not changed when emitted.
* **LagartoParser** does only tokenization. The DOM tree is not created, neither validated.
* the script tag is emitted separately.
* conditional comments are supported.
* XML is supported too.

