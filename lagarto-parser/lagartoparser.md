---
description: Fast event-based HTML parser
---

# LagartoParser

**LagartoParser** is an event-based HTML parser. It processes the input and emits events as they are parsed, using a [visitor pattern](https://en.wikipedia.org/wiki/Visitor_pattern). 

Parsing is done strictly by the official HTML5 specification.

Let's see it in action:

```java
LagartoParser lagartoParser = new LagartoParser(htmlContent);
TagVisitor tagVisitor = new MyTagVisitor();
lagartoParser.parse(tagVisitor);
```

As the input content is parsed, the visitor's methods are invoked.

