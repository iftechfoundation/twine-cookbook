# "Google Fonts": Sugarcane (v1.4.2)

!!! Warning
    The following example is designed for Twine 1.4.2.

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS **@import** at-rule. A class style rule ("message") is then created using the imported font-family and applied to a `<div>` element within a single passage.

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Example

[Download](sugarcane_googlefonts_example.html){: target="_top" download="sugarcane_googlefonts_example.html"}

## Twee Code

```twee
:: StoryTitle
Responsive: Google Fonts

:: StoryAuthor
@videlais

:: StoryStylesheet [stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

.message {
  font-family: 'Roboto', sans-serif;
}

:: Start
<div class="message">This text is styled using a Google Font</div>

```

[Twee Download](sugarcane_googlefonts_twee.txt){ target="_top" download="sugarcane_googlefonts_twee.txt"}
