---
description: Custom pseudo classes and functions
---

# Customize

### Custom pseudo-class

Custom pseudo-classes extends the `PseudoClass` and implements `match(Node node)`. This method should return `true` if a node is matched. You may also override the method `getPseudoClassName()` if you don't want to generate a pseudo-class name from the class name. For example:

```java
public class MyPseudoClass extends PseudoClass {
    @Override
    public boolean match(Node node) {
      return node.hasAttribute("jodd-attr");
    }

    @Override
    public String getPseudoClassName() {
      return "jodd";
    }
}
```

Then register your pseudo-class with:

```java
    PseudoClassSelector.registerPseudoClass(MyPseudoClass.class);
```

From that moment you will be able to find all nodes with the attribute `jodd-attr` using the `:jodd` pseudo-class.

When a pseudo-class needs to perform an additional match in the range of matched nodes \(e.g. first, last etc\), then override `matchInRange()` method, too.

### Custom pseudo-function

Similar to pseudo-classes, custom pseudo-function implements the `PseudoFunction` class. Additionally, you need to also implement a method that parses input expression. This expression is later passed to the matching method.

Let's make a function that matches all nodes with certain name length:

```java
public class MyPseudoFunction extends PseudoFunction {
    @Override
    public Object parseExpression(String expression) {
        return Integer.valueOf(expression);
    }

    @Override
    public boolean match(Node node, Object expression) {
        Integer size = (Integer) expression;
        return node.getNodeName().length() == size.intValue();
    }

    @Override
    public String getPseudoFunctionName() {
        return "len-fn";
    }
}
```

Register it with:

```java
PseudoFunctionSelector.registerPseudoFunction(MyPseudoFunction.class);
```

Start using it! E.g. `:len-fn(3)` to match all nodes with short names:\)

