# Variables

In programming terminology, a variable is something which changes. In Twine, a variable is a way of storing and acting on data of some sort. Anything from a number to a series of characters can be stored in a variable. Unlike other code or text in a [Passage](../terms/terms_passages.md), variables most commonly start with either the dollar sign ($) or the underscore (```_```).

## Story Variables

Once created, story variables in Twine can be accessed from any passage at any time. They are *globally* accessible to all functionality everywhere.

**Example:**
```
$numberVariable
```

All story formats (except Snowman) understand variables and translate them into their values when used by themselves in a Passage. To display their value, they can simply be included as part of any other text.

**Example:**
```
The value of the variable is $numberVariable.
```

## Temporary Variables

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
