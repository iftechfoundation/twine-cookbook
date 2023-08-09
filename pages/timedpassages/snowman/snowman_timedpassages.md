# "Timed Passages": Snowman (1.4)

## Summary

Made famous in [*Queers in Love at the End of the World*](https://w.itch.io/end-of-the-world) (2013), "Timed Passages" uses the the **[`_`.delay()](http://underscorejs.org/#delay)** function to count seconds while checking if the timer has reached zero. If so, the **[window.story.show()](https://videlais.github.io/snowman/#/1/window_story/functions/show)** function will immediately transition to another passage.

## Example

[Download](snowman_timedpassages_example.html){: target="_top" download="snowman_timedpassages_example.html"}

## Twee Code

```twee
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

[Twee Download](snowman_timedpassages_twee.txt){ target="_top" download="snowman_timedpassages_twee.txt"}

## See Also

[Delayed Text](../../delayedtext/snowman/snowman_delayedtext.md), [Typewriter Effect](../../typewriter/snowman/snowman_typewriter.md)
