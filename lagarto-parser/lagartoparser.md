---
description: Fast event-based HTML parser
---

# LagartoParser

**LagartoParser** is an _event-based_ HTML parser. It processes the input and emits events as they are parsed; using a [visitor pattern](https://en.wikipedia.org/wiki/Visitor_pattern).  This makes parsing very fast and memory-usage is minimal. However, sometimes event-based parsing can be tedious; in that case, try **LagartoDom** parser instead. 

Let's see it in action:

```java
LagartoParser lagartoParser = new LagartoParser("<html><h1>Hello</h1></html>");

TagVisitor tagVisitor = new EmptyTagVisitor() {
			@Override
			public void tag(final Tag tag) {
				if (tag.nameEquals("h1")) {
					System.out.println(tag.getName());
				}
			}

			@Override
			public void text(final CharSequence text) {
				System.out.println(text);
			}
		};

lagartoParser.parse(tagVisitor);
```

As the input content is parsed, the callback methods in the visitor get invoked. In this case, the result is:

```text
h1
Hello
h1
```

Note that the `tag()` event was emitted twice: first for the open tag, and then for the close tag. In other words, **LagartoParser** performs the _tokenization_ of the input HTML.

### Parsing specification

HTML parsing \(i.e. tokenization\) is done strictly by the official [HTML5 specification](https://html.spec.whatwg.org). Note the following:

* the text is emitted as a single block of text and not one by one character.
* the case of a tag name \(and other tokens\) is not changed when emitted.
* **LagartoParser** does only tokenization. The DOM tree is not created, neither validated.
* the script tag is emitted separately.
* Internet Explorer conditional comments are supported.
* XML is supported too.

{% hint style="warning" %}
**LagartoParser** only performs tokenization and it does not verify if tags make sense. For example, if your HTML has a non-closed tag, **LagartoParser** will not consider this as an error. **LagartoDom**, on the other hand, will handle these cases.
{% endhint %}

### Input types

**LagartoParser** accepts both `char[]` and `CharSequence`. This allows the usage of various implementations of inputs, including `String`, or even a `Reader`.

