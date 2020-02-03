# "Google Fonts": Chapbook (v1.0.0)

## Summary

Chapbook provides a global variable, *config.style.googleFont*, that can be used within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) to load and use an [external font](https://klembot.github.io/chapbook/guide/customization/external-web-fonts.html).

## Live Example

<section>
<iframe src="chapbook_googlefonts_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_googlefonts_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Google Fonts

:: Start
config.style.googleFont: '<link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">'
config.style.page.font: 'Roboto'
--
This text is styled by a Google Font.


```
Download: <a href="chapbook_googlefonts_twee.txt" target="_blank">Twee Code</a>
