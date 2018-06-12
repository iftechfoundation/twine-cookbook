# Story Formats

Each story format provides a different default layout, set of [macros](../terms/terms_macros.md), and its own internal set of JavaScript functionality.

## Harlowe

[Harlowe](https://twine2.neocities.org/) is the default story format in Twine 2. It is designed for ease-of-use and those beginning with Twine.

**Harlowe Example:**
```
(if: $hasKey)[It looks like the key will open the door.]
(else:)[No way forward!]
```

## SugarCube

[SugarCube](http://www.motoslave.net/sugarcube/2/) continues the traditions of Twine 1 while also expanding the available macros. It has more functionality than Harlowe, but can sometimes require greater knowledge of programming techniques and development patterns for more advanced usage.

**SugarCube Example:**
```
<<if $hasKey>>
It looks like the key will open the door.
<<else>>
No way forward!
<</if>>
```

## Snowman

[Snowman](https://twinery.org/wiki/snowman:reference) is designed to be written with custom JavaScript and CSS. It has no built-in macros, but includes the [Underscore.js JavaScript library](http://underscorejs.org/).

**Snowman Example:**
```
<% if (s.hasKey) { %>
It looks like the key will open the door.
<% } else { %>
No way forward!
<% } %> 
```
