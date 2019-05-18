# "Dice Rolling": Harlowe (v2.0)

## Summary

"Dice Rolling" demonstrates how to create the same effects of rolling various physical dice through using the *[(random:)](https://twine2.neocities.org/#macro_random)* macro and adding or subtracting numbers.

## Live Example

<section>
<iframe src="harlowe_dicerolling_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_dicerolling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Harlowe: Dice Rolling

:: Start
Rolling a 1d4: (random: 1,4)
Rolling a 1d6: (random: 1,6)
Rolling a 1d8: (random: 1,8)
Rolling a 1d10: (random: 1, 10)
Rolling a 1d12: (random: 1, 12)
Rolling a 1d20: (random: 1, 20)
Rolling a 1d100: (random: 1, 100)
Rolling a 1d4 + 4: (text: (random: 1, 4) + 4)
Rolling a 1d6 - 2: (text: (random: 1, 6) - 2)
Rolling a 2d6 + 10: (text: (random: 1, 6) + (random: 1, 6) + 10)
```

Download: <a href="harlowe_dicerolling_twee.txt" target="_blank">Twee Code</a>
