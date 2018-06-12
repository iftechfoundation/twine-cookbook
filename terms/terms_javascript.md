# JavaScript

The programming language [JavaScript](https://en.wikipedia.org/wiki/JavaScript) is embedded in all modern web browsers and is a foundational part of how Twine works.

Knowledge of JavaScript is not required to create [Stories](../terms/terms_stories.md) using Twine. However, understanding how JavaScript works and the expectations of how things are structured in the language can be helpful when using advanced functionality in [SugarCube](../terms/terms_storyformats.md) and when using Snowman.

## Story JavaScript

When using Twine, extra functionality can be added through the Story JavaScript screen. This is run *before* the Story is run and provides an opportunity to write specialized code or include external libraries and files. Some story formats, like SugarCube, provide the ability to translate between JavaScript and macro usage in Twine. Others, like Snowman, expect this to be used when creating more complex projects.

## *window.setup*

Based on the object provided by SugarCube [of the same name](http://www.motoslave.net/sugarcube/2/docs/special-names.html#special-variables-setup), this cookbook suggests creating and using a *window.setup* global object when working with Story JavaScript in Twine for greater portability between story formats.
