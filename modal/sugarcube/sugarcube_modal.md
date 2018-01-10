# "Modal (Pop-up Window)": SugarCube (v2.18)

## Summary
This example uses the built-in *Dialog* object to *setup()*, add content ( *wiki()* ), and finally *open()* the dialog window. SugarCube also comes with [additional functionality](http://www.motoslave.net/sugarcube/2/docs/api-dialog.html) to adjust other settings.

## Live Example
<section>
<iframe src="sugarcube_modal_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_modal_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Modal

:: Start
<<link "Open dialog!">>
	<<script>>
		Dialog.setup("Dialog");
		Dialog.wiki("Text within the dialog window");
		Dialog.open();
	<</script>>
<</link>>


```

Download: <a href="sugarcube_modal_twee.txt" target="_blank">Twee Code</a>
