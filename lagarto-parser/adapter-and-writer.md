---
description: Additional cool classes
---

# Adapter and Writer

Besides `TagVisitor`, you can use also one of the following classes.

* `EmptyTagVisitor` - default implementation that does nothing. You will probably use it, as you can override just the methods you need.
* `TagVisitors` - is a simple composite of many `TagVisitor`s implementations. They will be invoked in the given order.
* `TagAdapter` - is an adapter over target `TagVisitor`. With such adapter you can change the behavior of an existing visitor.

### Enclosed adapters

You can use the following adapters:

* `StripHtmlTagAdapter` - strips all the unnecessary whitespaces from text blocks and also removes all the comments. For example, multiple spaces would be replaced with a single space, etc. 
* `UrlRewriterTagAdapter` - as the name implies, you may change the `<a href` link values.

### Writer

`TagWriter` is a simple `TagVisitor` that _builds_ HTML from the events. Usually, you can use it as target of some adapter. This way you can modify input HTML by parsing it, adapt it, and then write it again to an `Appendable` content.

### Example

```java
TagWriter tagWriter = new TagWriter();
StripHtmlTagAdapter adapter = new StripHtmlTagAdapter(tagWriter);
LagartoParser lagartoParser = new LagartoParser(
        "<html> <h1>  Hello  </h1> </html>");

lagartoParser.parse(adapter);

System.out.println(tagWriter.getOutput().toString());
```

The resulting string would be:

```text
<html><h1> Hello </h1></html>
```

