# Story Formats

Each story format provides a different visual layout, set of [macros](../terms/terms_macros.md), and internal JavaScript functionality.

## Harlowe

[Harlowe](https://twine2.neocities.org/) is the default story format in Twine 2. It is designed for ease-of-use and for those using Twine 2 for the first time.

**Harlowe Example:**

```twee
(if: $hasKey)[It looks like the key will open the door.]
(else:)[No way forward!]
```

## SugarCube

[SugarCube](http://www.motoslave.net/sugarcube/2/) continues the traditions of Twine 1 while also expanding the available macros. It has more functionality than Harlowe, but can sometimes require greater knowledge of programming techniques and development patterns for more advanced usage.

**SugarCube Example:**

```twee
<<if $hasKey>>
It looks like the key will open the door.
<<else>>
No way forward!
<</if>>
```

## Snowman

[Snowman](https://videlais.github.io/snowman/) is designed to be written with custom JavaScript and CSS. It has no built-in macros, but includes the [Underscore.js](http://underscorejs.org/), [Marked](https://marked.js.org/#/README.md), and [jQuery](https://jquery.com/) JavaScript libraries.

**Snowman Example:**

```twee
<% if (s.hasKey) { %>
It looks like the key will open the door.
<% } else { %>
No way forward!
<% } %>
```

## Chapbook

[Chapbook](https://klembot.github.io/chapbook/guide/) is a "second-generation" Twine 2 story format that seperates its functionality into ["inserts"](https://klembot.github.io/chapbook/guide/references/inserts.html), which cause text to appear, and ["modifiers"](https://klembot.github.io/chapbook/guide/references/modifiers.html), functionality that affect text in some way.

**Chapbook Example:**

```twee
[if hasKey]
It looks like the key will open the door.
[else]
No way forward!
```
