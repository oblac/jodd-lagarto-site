---
description: 'LagartoDom parses XML, XHTML and HTML'
---

# Parsing modes

**LagartoDom** can parse XML, XHTML and HTML content. There are already predefined methods that quickly enable these modes:

* `enableHtmlMode()`
* `enableXhtmlMode()`
* `enableXmlMode()`

### HTML plus mode

There is one more mode available:

* `enableHtmlPlusMode()`

The default HTML mode does not change the order of the nodes. However, HTML5 specification has some rules where nodes are moved around the DOM. For example, all tags written beyond table tags in a table are moved before table definition. Moreover, there are some special rules on which orphan tags may be closed and the scope in which they can be closed.

HTML Plus mode is one that enables these additional parsing rules. These rules require some additional processing and may slow down the processing.

### Debug mode

Regardless of the parsing mode, **LagartoDom** may work in debug mode:

* `enableDebugMode()`

In debugging mode all the errors are collected and their position is calculated. Of course, this slows down the processing.

