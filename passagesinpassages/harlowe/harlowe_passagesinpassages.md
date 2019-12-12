# "Passages in Passages": Harlowe (v1.0)

## Summary

The Harlowe story format allows for content in one passage to be displayed in another through the use of the [`(display:)`](https://twine2.neocities.org/#macro_display) macro. Given the name of an existing passage, its contents will added wherever the macro is called.

## Live Example

<section>
<iframe src="harlowe_passagesinpassages_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_passagesinpassages_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Passages in Passages

:: Start
This is the Start passage!
(display: "Another")

:: Another
And this is another passage!

```

Download: <a href="harlowe_passagesinpassages_twee.txt" target="_blank">Twee Code</a>
