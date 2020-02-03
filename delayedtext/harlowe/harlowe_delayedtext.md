# "Delayed Text": Harlowe (v2.0)

## Summary

"Delayed Text" uses the [`(live:)`](https://twine2.neocities.org/#macro_live) and [`(stop:)`](https://twine2.neocities.org/#macro_stop) macros to create a loop that runs only once with a delay of five seconds.

## Live Example

<section>
<iframe src="harlowe_delayedtext_example.html" height=400 width=90%></iframe>

Download: <a href="harlowe_delayedtext_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Delayed Text in Harlowe

:: Start
{
	(live: 5s)[
    	(stop:)
		It has been 5 seconds. Show the text!
	]
}

```

Download: <a href="harlowe_delayedtext_twee.txt" target="_blank">Twee Code</a>

## See Also

[Typewriter Effect](../../typewriter/harlowe/harlowe_typewriter.md)
