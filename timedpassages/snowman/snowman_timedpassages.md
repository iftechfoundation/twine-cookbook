# "Timed Passages": Snowman (1.3.0)

## Summary

Made famous in [*Queers in Love at the End of the World* (2013)](http://auntiepixelante.com/endoftheworld/), "Timed Passages" uses the the [*_.delay()*](http://underscorejs.org/#delay) function to count seconds while checking if the timer has reached zero. If so, the [*window.story.show()*](https://twinery.org/wiki/snowman:window-story:show) function will immediately transition to another passage.

## Twee Code

```
:: Start
There are <span class="time-left">10</span> seconds left.

<%
$(function() {
	var timeLeft = parseInt($('.time-left').text());

	function tick() {
		if (--timeLeft === 0) {
			story.show('World End');
		}
		else {
			$('.time-left').text(timeLeft);
		}

		_.delay(tick, 1000);
	}

	/* Start ticking. */

	_.delay(tick, 1000);
});
%>

:: World End
The world ended.
```

## See Also

[Delayed Text](../../delayedtext/snowman/snowman_delayedtext.md), [Typewriter Effect](../../typewriter/snowman/snowman_typewriter.md)
