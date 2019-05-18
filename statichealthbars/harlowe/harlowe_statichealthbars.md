# "Static Healthbars": Harlowe (v2.0)

## Summary

"Static Healthbars" demonstrates how to write HTML elements using variable values. In this example, the [(print:)](https://twine2.neocities.org/#macro_print) macro is used to create &lt;progress&gt; and &lt;meter&gt; elements. A [(text:)]() macro is also used to temporarily convert the current **Numeric** value of the *$heath* story variable into a **String** value.

## Twee Code

```
:: StoryTitle
Static Healthbars for Harlowe

:: Start
(set: $health to 80)

Show a healthbar using a Progress element:
(print: '<progress value="' + (text: $health) + '" max="100"></progress>')

Show a healthbar using a Meter element:
(print: '<meter value="' + (text: $health) + '" min="0" max="100"></meter>')


```
