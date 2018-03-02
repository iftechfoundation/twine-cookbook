# "Fairmath System": SugarCube (v2.18)

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, increase and decrease changes the value by a percentage as the difference between the original and adjusted value.

This example uses the [*&lt;&lt;widget&gt;&gt;*](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-widget) macro in SugarCube to separate operations for increasing and decreasing.

## Live Example

<section>
<iframe src="sugarcube_fairmath_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_fairmath_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Fairmath in SugarCube

:: Start
<!-- Fairmath formulas based on http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath -->

<<set $valueToAdjust to 100>>
The inital value is $valueToAdjust

<!-- Call the decrease widget -->
<<decrease $valueToAdjust 50>>
The adjusted value is $resultValue.

<!-- Save the changed value -->
<<set $valueToAdjust to $resultValue>>
<!-- Call the increase widget -->
<<increase $valueToAdjust 100>>
The adjusted value is $resultValue.

:: Fairmath Operations[widget]
<<widget "increase">>
<<set $resultValue to Math.round($args[0]+((100-$args[0])*($args[1]/100))) >>
<</widget>>

<<widget "decrease">>
<<set $resultValue to Math.round($args[0]-($args[0]*($args[1]/100) )) >>
<</widget>>

```

Download: <a href="sugarcube_fairmath_twee.txt" target="_blank">Twee Code</a>

