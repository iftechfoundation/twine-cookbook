# Macros

Macros allow programming code to be intermixed with text shown onscreen. They allow a wide variety of functionality to be added to a story, from changing the appearance of text to reacting to mouse and touch events. [Story Formats](../terms/terms_storyformats.md) are often chosen based on the macros they provide and how they can be used together.

## Twine 1 and SugarCube

In Twine 1, macros were written with two less-than (`<<`) and two-greater-than signs (`>>`) around code. ([SugarCube](../terms/terms_storyformats.md), as a successor of this form, follows the same syntax.)

**Example:**
```
<<display "Another Passage">>
```

## Harlowe

The [Harlowe](../terms/terms_storyformats.md) story format uses a different syntax for macros. They are wrapped in a single open `(` and close parenthesis `)`, and use brackets, `[]`, to indicate which text or sections are associated or acted upon by the macro.

**Example:**
```
(font: “Arial”)[This text will be in Arial.]
```

## Snowman

[Snowman](../terms/terms_storyformats.md) does not provide macros in the same sense that SugarCube and Harlowe do, but allow mixing JavaScript code in text with `<%` and `%>`, with `<%=` and `%>` displaying the result on the page.

**Examples**
```
The chalkboard reads 2 + 2 = <%= 2 + 2 %>.
```

## Chapbook

[Chapbook](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) provides [inserts](https://klembot.github.io/chapbook/guide/references/inserts.html) and [modifiers](https://klembot.github.io/chapbook/guide/references/modifiers.html) to work with variables and other values. However, any variable testing must be done within the vars section itself.

**Examples**
```
largeFamily: cousins > 10
--
```
