# "Google Fonts": Sugarcane (v1.4.2)

<div class="alertbox warning"><strong>Note:</strong> The following example is designed for Twine 1.4.2.</div>

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS ```@import``` at-rule. A class style rule ("googleFont") is then created using the imported font-family and applied to a ```<div>``` element within a single passage. 

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Live Example

<section>
<iframe src="sugarcane_googlefonts_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcane_googlefonts_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: Start
<div class="googleFont">This text is styled using a Google Font</div>

:: StoryStylesheet [stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

.googleFont {
	font-family: 'Roboto', sans-serif; 
}

:: StoryTitle
Responsive: Google Fonts

:: StoryAuthor
@videlais

```

Download: <a href="sugarcane_googlefonts_twee.txt" target="_blank">Twee Code</a>
