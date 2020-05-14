# Custom Macros

It's possible to write macros for use in your stories. Doing so requires knowledge of both JavaScript and the Twine engine.

The following is an example passage that creates a macro named `<<hello>>` that, when invoked in another passage, displays an alert that greets the reader.

```twee
:: Hello macro [script]
macros['hello'] =
{
  handler: function()
  {
    alert('Hi, reader!');
  }
}

:: Start
<<hello>>
```

Browsing the [source code repository](https://github.com/tweecode/twine) may be helpful, too.
