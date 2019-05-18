# "Timed Passages": Harlowe (v2.0)

## Summary

Made famous in [*Queers in Love at the End of the World* (2013)](http://auntiepixelante.com/endoftheworld/), "Timed Passages" uses the the [*(live:)*](https://twine2.neocities.org/#macro_live) macro to count seconds while checking if the timer has reached zero. If so, the [*(goto:)*](https://twine2.neocities.org/#macro_go-to) macro will immediately go to another passage.

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

## See Also

[Delayed Text](../../delayedtext/harlowe/harlowe_delayedtext.md), [Typewriter Effect](../../typewriter/harlowe/harlowe_typewriter.md)
