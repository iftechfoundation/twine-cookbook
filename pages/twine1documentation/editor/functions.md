# Functions

When writing code in your stories, functions are special devices that can be used in expressions in place of variables or values.

Syntactically, they consist of:

- a name, which is subject to the same rules that variable names are under,
- followed by a `(` left bracket,
- followed by zero or more other expressions separated by commas,
- followed by a `)` right bracket.

Technically speaking, any Javascript built-in function is available to the Twine author: `parseInt()`, `JSON.stringify()`, `document.createElement()` and all the rest are accessible, as are any functions that have been added by scripts.
