---
description: Jerry has a girlfriend!
---

# CSSelly

**CSSelly** is a Java implementation of the W3C Selectors Level 3 specification.

It's small, fast and extendable. **CSSelly** parses an input containing CSS selectors. The result then may be used by any HTML parser. Yet, it works the best with **LagartoDOM** tree and our **Jerry.**

### **Example**

```java
CSSelly csselly = new CSSelly("div:nth-child(2n) span#jodd");
List<CssSelector> selectors = csselly.parse();
```

As said, CSSelly is used as node selector in **LagartoDOM** \(and therefore in **Jerry**, too\):

```java
NodeSelector nodeSelector = new NodeSelector(document);
LinkedList<Node> selectedNodes = nodeSelector.select("div#jodd li");
```



