---
description: List of events emitted during the parsing
---

# Events

During the content parsing, **LagartoParser** calls various callback methods of provided `TagVisitor` implementation.

### `start()` & `end()`

Invoked before and after the content is parsed.

### `text(CharSequence)`

Callback invoked on a block of plain text.

### `comment(CharSequence)`

Invoked on an HTML comment. The argument contains the comment content, without the boundaries.

### `tag(Tag)`

Callback invoked foo all HTML tags: _open_, _close,_ or an _empty_ tag. The argument is a `Tag` instance, containing various information about the tag: tags name, attributes, depth level, etc.

{% hint style="warning" %}
`Tag` instance is reused during HTML parsing for better performances! The same `Tag`instance is passed to all callback methods and for every detected HTML tag.
{% endhint %}

### `script(Tag, CharSequence)`

Invoked on all `script` tags. The callback method receives the script Tag instance and the script body.

### `doctype(Doctype)`

Callback for the `doctype` tag.

### `xml()` and `cdata()`

These two callbacks are invoked for XML-specific tags when parsing the XML content.

## Example

For given HTML snippet

