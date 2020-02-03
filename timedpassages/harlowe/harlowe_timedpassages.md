# "Timed Passages": Harlowe (v2.0)

## Summary

Made famous in [*Queers in Love at the End of the World*](https://w.itch.io/end-of-the-world) (2013), "Timed Passages" uses the the [`(live:)`](https://twine2.neocities.org/#macro_live) macro to count seconds while checking if the timer has reached zero. If so, the [`(goto:)`](https://twine2.neocities.org/#macro_go-to) macro will immediately go to another passage.

## Live Example

<section>
<iframe src="harlowe_timedpassages_example.html" height=400 width=90%></iframe>

Download: <a href="harlowe_timedpassages_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Timed Passages

:: StoryStylesheet[stylesheet]
tw-include[type="startup"]{
	display: none;
}
tw-sidebar {
  	display:none;
}


:: Start
[[Start Timer|First Passage]]

:: World End
The world ended.

:: First Passage
(display: "Timer")

[[Second Passage]]

:: Timer
{
	(live: 1s)[
    	(if: $timer is 0)[
			(stop:)
			(goto: "World End")
		]
    	(else: )[
			(set: $timer to it - 1)
			The world will end in $timer seconds
		]
	]
}

:: Second Passage
(display: "Timer")

[[First Passage]]

:: Startup[startup]
(set: $timer to 10)

```

Download: <a href="harlowe_timedpassages_twee.txt" target="_blank">Twee Code</a>

## See Also

[Delayed Text](../../delayedtext/harlowe/harlowe_delayedtext.md), [Typewriter Effect](../../typewriter/harlowe/harlowe_typewriter.md)
