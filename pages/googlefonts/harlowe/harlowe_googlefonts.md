# "Google Fonts": Harlowe (v2.0)

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS **@import** at-rule. The loaded font is then applied to selected text using the [`(font:)`](https://twine2.neocities.org/#macro_font) macro.

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Example

[Download](harlowe_googlefonts_example.html){ target="_top" download="harlowe_googlefonts_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe: Google Fonts

:: StoryStylesheet[stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

:: Start
(font:"Roboto")[This text is styled by a Google Font]

```

[Twee Download](harlowe_googlefonts_twee.txt){ target="_top" download="harlowe_googlefonts_twee.txt"}
