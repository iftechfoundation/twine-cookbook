# SugarCube JavaScript

The SugarCube documentation provides details for using [Scripting Macros](https://www.motoslave.net/sugarcube/2/docs/#macros-scripting) with JavaScript code. It also provides multiple application programming interfaces (APIs) for using JavaScript with its own built-in functionality.

## `window.setup`

When working with [Story JavaScript](../../introduction/twine2_passages_view.md#edit-story-javascript), it is strongly recommended, to use the [**setup**](https://www.motoslave.net/sugarcube/2/docs/#special-variable-setup) object in SugarCube to add functionality.

```javascript
window.setup = window.setup || {};
```

## SugarCube Addons

Working with [SugarCube Addons](https://www.motoslave.net/sugarcube/2/) requires using Story JavaScript. The provided instructions with the addon often require copying and pasting code into this area or configuring other options.
