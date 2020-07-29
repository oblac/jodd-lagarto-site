---
description: jQuery in Java
---

# Jerry

**Jerry** is a [jQuery](http://jquery.com/) in Java - fast and focused Java library that simplifies parsing, traversing and manipulating the HTML content, using the same methods and syntax as the jQuery.

Look, it's really cool:

```java
Jerry doc = Jerry.of("<html><div id='jodd'><b>Hello</b> Jerry</div></html>");
doc.s("div#jodd b").css("color", "red").addClass("ohmy");
```

The \(formatted\) output will be:

```markup
<html>
    <div id="jodd">
        <b style="color:red;" class="ohmy">Hello</b> Jerry
    </div>
</html>
```

I tried to keep **Jerry** API identical to the jQuery as much as possible. In some cases, you can simply copy some jQuery code and paste it in Java - and it will work! Of course, there are some differences due to the different nature of the platforms.

{% hint style="warning" %}
The well-known jQuery method `$()` is renamed to`s()` in **Jerry**. The reason is compatibility with different JVMs: GraalVM, for example, does not allow usage of `$` in method names.
{% endhint %}

If you don't like the `s()` method, use the `find()` alternative.

