# Story Formats

Each story format provides a different default layout, set of [macros](../terms/terms_macros.md), and its own internal set of JavaScript functionality.

## Harlowe

[Harlowe](https://twine2.neocities.org/) is the default story format in Twine 2.

**Harlowe Example:**
```
(if: $hasKey)[It looks like the key will open the door.]
(else:)[No way forward!]
```

## SugarCube

[SugarCube](http://www.motoslave.net/sugarcube/2/) continues the traditions of Twine 1 while also expanding the available macros.

**SugarCube Example:**
```
<<if $hasKey>>
It looks like the key will open the door.
<<else>>
No way forward!
<</if>>
```

## Snowman

[Snowman](https://twinery.org/wiki/snowman:reference) is designed to be written with custom JavaScript and CSS.

**Snowman Example:**
```
<% if (s.hasKey) { %>
It looks like the key will open the door.
<% } else { %>
No way forward!
<% } %> 
```
