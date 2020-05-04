# "Modal (Pop-up Window)": SugarCube (v2.18)

## Summary

This example uses the built-in *[Dialog](http://www.motoslave.net/sugarcube/2/docs/api-dialog.html)* object to **setup()**, add content ( **wiki()** ), and finally **open()** the dialog window. SugarCube also comes with [additional functionality](http://www.motoslave.net/sugarcube/2/docs/api-dialog.html) to adjust other settings.

## Example

[Download](sugarcube_modal_example.html)

## Twee Code

```twee
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

[Twee Download](sugarcube_modal_twee.txt)
