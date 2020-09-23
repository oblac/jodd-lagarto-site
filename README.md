---
description: Java libraries for HTML/XML parsing
---

# Lagarto HTML parsers suite

**Lagarto Suite** is the family of HTML/XML parsers written in Java. It consists of the following libraries:

1. **LagartoParser** is an all-purpose fast and versatile event-based HTML parser. You can use it to modify or analyze some markup content, allowing you to assemble custom complex transformations and code analysis tools quickly. It is performant and follows the rules of the official HTML specification.
2. **LagartoDom** builds a DOM tree in memory from the input. You can manipulate a tree more conveniently, with minor performance sacrifice.
3. **Jerry** is a "jQuery in Java" - you can use the familiar syntax of JavaScript library inside of Java to parse and manipulate HTML.
4. **CSSelly** - finally, the parser of CSS3 selectors.

{% hint style="info" %}
Each of the **Lagarto** libraries has it's pros and cons. You should check each and use one that suits your requirements.
{% endhint %}

Lagarto parsers are compatible with Java 8 and newer.

### License

The code is released under the `BSD-2-Clause` license. It has a minimal set of dependencies with the same or similarly open license, so you should be able to use it in any project and for any purpose.

