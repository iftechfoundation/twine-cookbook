# "Google Fonts": Chapbook (v1.0.0)

## Summary

Chapbook provides a global variable, *config.style.googleFont*, that can be used within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) to load and use an [external font](https://klembot.github.io/chapbook/guide/customization/external-web-fonts.html).

## Live Example

[Download](chapbook_googlefonts_example.html){ target="_top" download="chapbook_googlefonts_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Google Fonts

:: Start
config.style.googleFont: '<link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">'
config.style.page.font: 'Roboto'
--
This text is styled by a Google Font.
```

[Twee Download](chapbook_googlefonts_twee.txt){ target="_top" download="chapbook_googlefonts_twee.txt"}
