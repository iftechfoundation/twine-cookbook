# "Dice Rolling": Snowman (v1.3)

## Summary

"Dice Rolling" demonstrates how to create the same effects of rolling various physical dice through using Underscore.js's [`_.random()`](http://underscorejs.org/#random) function and its interpolating functionality.

## Example

[Download](snowman_dicerolling_example.html){: target="_top" download="snowman_dicerolling_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Dice Rolling

:: Start
Rolling a 1d4: <%= _.random(1,4) %>

Rolling a 1d6: <%= _.random(1,6) %>

Rolling a 1d8: <%= _.random(1,8) %>

Rolling a 1d10: <%= _.random(1, 10) %>

Rolling a 1d12: <%= _.random(1, 12) %>

Rolling a 1d20: <%= _.random(1, 20) %>

Rolling a 1d100: <%= _.random(1, 100) %>

Rolling a 1d4 + 4: <%= _.random(1, 4) + 4 %>

Rolling a 1d6 - 2: <%= _.random(1, 6) - 2 %>

Rolling a 2d6 + 10: <%= _.random(1, 6) + _.random(1, 6) + 10 %>

```

[Twee Download](snowman_dicerolling_twee.txt){ target="_top" download="snowman_dicerolling_twee.txt"}
