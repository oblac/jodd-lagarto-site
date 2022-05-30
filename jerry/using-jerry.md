---
description: Some differences and add-ons
---

# Using Jerry

In Java we do not have the document context as in browsers, so we need to create one first. To do that, simply pass HTML content to **Jerry** static factory method. That will create a root **Jerry** set, containing a `Document` root node of the parsed DOM tree.

What happens in the background is that **LagartoDOM** builds a DOM tree and wraps it in the **Jerry**/jQuery API.

### Using CSS selectors

You can use most of the standard CSS selectors and also most of the jQuery CSS selectors extensions. CSS selectors are supported by the **CSSelly**.

### Differences

As **Jerry** speaks Java, there are some differences in API made to make Jerry API more Java friendly. For example, `css()` method accepts an array of property/values, and not a single string:

```java
Jerry
    .of(html)
    .s("tr:last")
    .css("background-color", "yellow", "fontWeight", "bolder");
```

Similarly, `each()` method receives a lambda:

```java
Jerry.of(someHtml)
    .s("select option:selected")
    .each(($this, index) -> {
        System.out.println($this.text());
        return true;
    });
```

### Unsupported stuff

As **Jerry** is all about 'static' manipulation of HTML content, all jQuery methods and selectors that are related to any dynamic activity are not supported. This includes animations, Ajax calls, selectors that depend on CSS definitions...

### Add-ons

**Jerry** provides some add-ons that do not exist in jQuery.

First, there are few methods that return `Node` of parsed DOM tree (similar to JavaScript).

Then there are some new methods that are more meaningful in Java world. One of them is the `form()` method. It collects all parameters from a given form, allowing easy form handling. Here is an example:

```java
Jerry.of("html")
     .form("#myform", (form, parameters) -> {
         // process form and parameters
     });
```

Convenient, right!?
