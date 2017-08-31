# "Google Fonts": Snowman (v1.3)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS ```@import``` at-rule. A class style rule ("googleFont") is then created using the imported font-family and applied to a ```<div>``` element within a single passage. 

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Live Example

<section>
<iframe src="snowman_googlefonts_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_googlefonts_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Snowman: Google Fonts

:: StoryStylesheet[stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

.googleFont {
	font-family: 'Roboto', sans-serif; 
}

:: Start
<div class="googleFont">This text is styled using a Google Font</div>

```

Download: <a href="snowman_googlefonts_twee.txt" target="_blank">Twee Code</a>
