# Macros

For as long as [Twine](../terms/terms_twine.md) has existed, macros have been a part of it. They provide ways to do additional functionality ranging from changing the style of text to dynamically reacting to mouse events. Often, [Story Formats](../terms/terms_storyformats.md) are chosen based on what macros they provide and how they can be used.

## Twine 1 and SugarCube

Originally, macros were written with two less-than (```<<```) and two-greater-than signs (```>>```) around the keyword. ([SugarCube](../terms/terms_storyformats.md), as a successor of this form, follows the same syntax.)

**Example:**
```
<<display “Another Passage”>>
```

## Harlowe

Introduced in Twine 2, the [Harlowe](../terms/terms_storyformats.md) story format uses a different syntax for macros where they are wrapped in a single open and close parenthesis and use brackets to indicate which text or sections are associated or acted upon by the macro.

**Example:**
```
(font: “Arial”)[This text will be in Arial.]
```

## Snowman

[Snowman](../terms/terms_storyformats.md) does not provide macros. Instead, it has a new set JavaScript functions and expects the author to write their own code and macro-like functionality. 
