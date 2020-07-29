---
description: Parse HTML to a DOM tree.
---

# LagartoDOM

**LagartoDOM** parses HTML content and creates a DOM tree from it. It is based on **LagartoParser**. The created DOM is convenient to traverse and manipulate. However, if you need ultimate performance, go with the event-based **LagartoParser**.

Let's see **LagartoDom** in action:

```java
Document document = new LagartoDOMBuilder()
				.parse("<html><h1>Hello</h1></html>");

Node html = document.getChild(0);
Node h1 = html.getFirstChild();

System.out.println(h1.getTextContent());				// Hello

Text text = (Text) h1.getFirstChild();
System.out.println(text.getTextValue());				// Hello

System.out.println(text.getCssPath());				  // html h1
```

It's simple as that. As said, the DOM tree is created. It consists of `Node` elements. Each `Node` contains a bunch of methods related to tree traversing, such as `getChild(index)`, `getFirstChild()`, `getParentNode()`, `getChildNodes()`, etc.

`Node` contains also getters for node name, attributes, node values. `Node` can be detached from the tree or attached at some point. `Element` is a special type of the `Node` that represents elements, and there is a whole subset of methods that deal only with elements.

Finally, you can render DOM tree or any `Node` back to HTML content.

### Parsing specification

**LagartoDOM** follows only a subset of the official DOM-building specification. Here is why!

By default, **LagartoDOM** follows all the rules that do not involve any _movements of DOM_ nodes. This is done on purpose. The idea is to get the exact tree to what you have provided. For example, if you pass HTML with some tags that are not supposed to be nested, **LagartoDOM** would not complain and you will get exactly what you have on input.

In most cases, this will be perfectly fine, as developers are probably not using all the tricks of HTML5 for the sake of better readability.

Still, you can turn on some more rules, you can turn them on! In that case, the resulting DOM tree can be modified per HTML5 rules. I have implemented the most common of these rules and exceptions, but haven't covered them all \(yet\). So if you have some weird HTML, you might get a different tree than what you get in a browser.

{% hint style="info" %}
**LagartoDOM** is not \(yet\) a strict implementation of HTML5 DOM-building rules, but it is good enough for most cases!
{% endhint %}

Carry on :\)

