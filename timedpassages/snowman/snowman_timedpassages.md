# "Timed Passages": Snowman (1.3.0)

*Contributed by <a href="https://github.com/klembot">@klembot</a>*

## Summary

Made famous in <a href="http://auntiepixelante.com/endoftheworld/">Queers in Love at the End of the World</a>, "Timed Passages" uses the the *_.delay()* function to count seconds while checking if the timer has reached zero. If so, the *story.show()* function will immediately transition to another passage.

## Live Example

<section>
<iframe src="snowman_timedpassages_example.html" height=400 width=90%></iframe>


Download: <a href="snowman_timedpassages_example.html" target="_blank">Live Example</a>
</section>

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

Download: <a href="snowman_timedpassages_twee.txt" target="_blank">Twee Code</a>
