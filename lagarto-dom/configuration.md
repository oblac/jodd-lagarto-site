---
description: Fine-tune parsing to DOM tree.
---

# Configuration

**LagartoDom** configuration is specified in `LagartoDomBuilderConfig` class. Among new properties, there is also the instance of the **LagartoParser** configuration, of the parser that is used internally.

In most cases, you will just use the predefined modes. Here is the list of properties that you can configure.

### ignoreWhitespacesBetweenTags

This flag is used for XML mode, to ignore all whitespace content between two starting or two ending tags. Whitespace content between one open and one closed tag is still not ignored.

### ignoreComments

This flag simply defines if the resulting DOM tree should contain comments or not.

### enabledVoidTags

Flag to enable/disable void tags.

### selfCloseVoidTags

When an element is a void element, this flag defines if it can be self-closed or if it should have the standard end tag.

### impliedEndTags

Enables rules for implicit end tags. There are a number of tags that do not require the use of a closing tag for valid HTML \(`body`, `li`, `dd`, `dt`, `p`, `td`, `tr`,...\). When this flag is on, these tags are implicitly closed if needed and no error/warning is logged.

This feature somewhat slows down the parsing. If you know that all tags are closed in input HTML, consider switching this feature off, to improve performances.

### condCommentIEVersion

The version of conditional comments.

### errorLogger & debugLogger

Custom loggers.

