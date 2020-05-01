# "Dice Rolling": SugarCube (v2.18)

## Summary

"Dice Rolling" demonstrates how to create the same effects of rolling various physical dice through using the **[random()](http://www.motoslave.net/sugarcube/2/docs/functions.html#random)** function and the [`<<print>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-print) macro to show the results.

## Live Example

<section>
<iframe src="sugarcube_dicerolling_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_dicerolling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```twee
:: StoryTitle
SugarCube: Dice Rolling

:: Start
Rolling a 1d4: <<print random(1,4) >>
Rolling a 1d6: <<print random(1,6) >>
Rolling a 1d8: <<print random(1,8) >>
Rolling a 1d10: <<print random(1, 10) >>
Rolling a 1d12: <<print random(1, 12) >>
Rolling a 1d20: <<print random(1, 20) >>
Rolling a 1d100: <<print random(1, 100) >>
Rolling a 1d4 + 4: <<print random(1, 4) + 4 >>
Rolling a 1d6 - 2: <<print random(1, 6) - 2 >>
Rolling a 2d6 + 10: <<print random(1, 6) + random(1, 6) + 10 >>
```

Download: <a href="sugarcube_dicerolling_twee.txt" target="_blank">Twee Code</a>
