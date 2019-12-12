# "Google Fonts": SugarCube (v2.18)

## Summary

"Google Fonts" uses a [Google Font](https://fonts.google.com/) loaded via the CSS ```@import``` at-rule. A class style rule ("message") is then created using the imported font-family and applied to a ```<div>``` element within a single passage. 

Other Google Fonts could be imported and applied using the same method, creating new class or ID style rules to be applied for and across different HTML elements in the same way.

## Live Example

<section>
<iframe src="sugarcube_googlefonts_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_googlefonts_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Google Fonts

:: StoryStylesheet[stylesheet]
@import url('https://fonts.googleapis.com/css?family=Roboto');

.message {
	font-family: 'Roboto', sans-serif; 
}

:: Start
<div class="message">This text is styled using a Google Font</div>

```

Download: <a href="sugarcube_googlefonts_twee.txt" target="_blank">Twee Code</a>
