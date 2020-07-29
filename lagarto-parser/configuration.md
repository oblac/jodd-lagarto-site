---
description: Fine-tune the parser
---

# Configuration

**LagartoParser** configuration is defined in `LagartoParserConfig` class. An instance of this class can be passed to a constructor or you can just modify it later, functional style. For example:

```java
LagartoParserConfig cfg = new LagartoParserConfig().setCaseSensitive(true);
LagartoParser lagartoParser = new LagartoParser(cfg, "<html>");
```

```java
LagartoParser lagartoParser =
    new LagartoParser("<html>")
        .configure(cfg -> {
            cfg.setCaseSensitive(true);
        });
```

The list of available properties follows.

### calculatePosition

By default disabled, this property switches the calculation of elements position. The position consists of a line number, approximate column number, and a total offset in the file.

{% hint style="danger" %}
Calculating position makes processing slower.
{% endhint %}

### enableConditionalComments

When enabled, **LagartoParser** will detect IE conditional comments. When its disabled and conditional comment is found, **LagartoParser** sends an error for revealed conditional comment tags or threats downlevel-hidden conditional comments as regular comments.

{% hint style="danger" %}
Enabling conditional comments also makes parsing slower.
{% endhint %}

### caseSensitive

By default is `false`. When enabled various matching will be case sensitive. Should not be used for parsing HTML content.

### parseXmlTags

Enables parsing of XML specific tags. By default it's disabled.

### enableRawTextModes

Enabled by default, tells **LagartoParser** to take special take on all so-called 'raw' text tags, such as `style`, `script`, `xmp` and so on. You can disable this if that content is not of importance, and gain some more speed.

### textBufferSize

By default its set to `1024`. It's the size of the internal text buffer used to collect all text blocks. This buffer will grow if needed. If your HTML contains text blocks of large size, you may increase this number, just for the purpose of small performance improvement.

