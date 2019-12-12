# Variables

In programming terminology, a variable is a container for a value that can change. In Twine, a variable is a way of storing and acting on data of some sort. Anything from a number to a series of characters can be stored in a variable. Unlike other code or text in a [Passage](../terms/terms_passages.md), variables most commonly start with either the dollar sign ($) or the underscore (```_```) in the Harlowe and SugarCube story formats. (In Chapbook, variables are part of a ['vars section'](https://klembot.github.io/chapbook/guide/state/the-vars-section.html).)

## Story Variables (Harlowe and SugarCube)

Once created, story variables in Twine can be accessed from any passage at any time. They are *globally* accessible to all functionality everywhere.

**Example:**
```
$numberVariable
```

Variables are translated into their values when used by themselves in a Passage. To display their value, they can simply be included as part of any other text.

**Example:**
```
The value of the variable is $numberVariable.
```

## Temporary Variables (Harlowe and SugarCube)

It can often be useful to work with values in a more controlled manner. For this purpose, temporary variables can be used. They are *locally* accessible. They only exist while the current passage is shown. They start with an underscore (```_```).

**Example:**
```
_tempVariable
```
Temporary variables can also be used to display their values with other text like Story Variables.

**Example:**
```
The value of the variable is _numberVariable.
```

## Differences in Chapbook

Chapbook [handles variables](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) differently. Instead of variables needing to start with the dollar sign `$` or an underscore, `_`, Chapbook also allows variable names to start with upper or lowercase letters as well.

**Example:**
```
strength: 18
$dexterity: 7
_constitution: 14
```

## Differences in Snowman

Snowman uses JavaScript [variables](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var). It provides three global variables: `window.story` (for working with the story), `window.passage` (for working with the current passage), and `s` (as a way to access values across passages).

**Example:**
```
s.strength = 14;
```
