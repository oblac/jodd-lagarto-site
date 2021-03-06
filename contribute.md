---
description: Tips on how to install Jodd Lagarto library in your app
---

# Installation

**Jodd Lagarto** is released on Maven Central. You can use the following snippets to add it to your project:

{% tabs %}
{% tab title="Maven" %}
```markup
<dependency>
  <groupId>org.jodd</groupId>
  <artifactId>jodd-lagarto</artifactId>
  <version>x.x.x</version>
</dependency>
```
{% endtab %}

{% tab title="Gradle" %}
```text
implementation 'org.jodd:jodd-lagarto:x.x.x'
```
{% endtab %}

{% tab title="Gradl.kt" %}
```kotlin
implementation("org.jodd:jodd-lagarto:x.x.x")
```
{% endtab %}

{% tab title="Scala SBT" %}
```scala
libraryDependencies += "org.jodd" % "jodd-lagarto" % "x.x.x"
```
{% endtab %}

{% tab title="Ivy" %}
```markup
<dependency org="org.jodd" name="jodd-lagarto" rev="x.x.x" />
```
{% endtab %}

{% tab title="Leiningen" %}
```
[org.jodd/jodd-lagarto "x.x.x"]
```
{% endtab %}

{% tab title="Buildr" %}
```
'org.jodd:jodd-lagarto:jar:x.x.x'
```
{% endtab %}
{% endtabs %}

That is all!

Jodd Lagarto has only one \(and small\) dependency: the Jodd util library, that is released under the same license.

### Snapshots

**Jodd Lagarto** snapshots are published on [Maven Central Snapshot repo](https://oss.sonatype.org/content/repositories/snapshots/org/jodd/jodd-lagarto/).

{% hint style="warning" %}
Snapshots are released manually. Feel free to contact me if you need a new SNAPSHOT release sooner.
{% endhint %}



