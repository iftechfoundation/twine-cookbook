# "Google Fonts": Snowman (v1.3)

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS **@import** at-rule. A class style rule ("message") is then created using the imported font-family and applied to a `<div>` element within a single passage.

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Example

[Download](snowman_googlefonts_example.html){: target="_top" download="snowman_googlefonts_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Google Fonts

:: StoryStylesheet[stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

.message {
  font-family: 'Roboto', sans-serif;
}

:: Start
<div class="message">This text is styled using a Google Font</div>

```

[Twee Download](snowman_googlefonts_twee.txt){ target="_top" download="snowman_googlefonts_twee.txt"}
