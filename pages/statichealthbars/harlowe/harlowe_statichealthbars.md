# "Static Healthbars": Harlowe (v2.0)

## Summary

"Static Healthbars" demonstrates how to write HTML elements using variable values. In this example, the [`(print:)`](https://twine2.neocities.org/#macro_print) macro is used to create `<progress>` and `<meter>` elements. A [`(text:)`](https://twine2.neocities.org/#macro_str) macro is also used to temporarily convert the current Numeric value of the *$heath* story variable into a String value.

## Example

[Download](harlowe_statichealthbars_example.html){: target="_top" download="harlowe_statichealthbars_example.html"}

## Twee Code

```twee
:: StoryTitle
Static Healthbars for Harlowe

:: Start
(set: $health to 80)

Show a healthbar using a Progress element:
(print: '<progress value="' + (text: $health) + '" max="100"></progress>')

Show a healthbar using a Meter element:
(print: '<meter value="' + (text: $health) + '" min="0" max="100"></meter>')


```

[Twee Download](harlowe_statichealthbars_twee.txt){ target="_top" download="harlowe_statichealthbars_twee.txt"}
