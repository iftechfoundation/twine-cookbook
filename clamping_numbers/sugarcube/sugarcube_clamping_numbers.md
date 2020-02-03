# "Limiting the Range of a Number": SugarCube (v2.18)

## Summary

This example demonstrates how to limit a numeric variable to a value between a set range, this process is commonly known as clamping. It uses the **[Math.clamp()](http://www.motoslave.net/sugarcube/2/docs/object-methods.html#math-mathclamp)** function in SugarCube to achieve the desired result.

## Live Example

<section>
<iframe src="sugarcube_clamping_numbers_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_clamping_numbers_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Limiting the range of a number in SugarCube


:: Start
Initialise the numeric variable to a value with the range you want.
eg. between ''1'' and ''10'' inclusive.
(note: You don't need to use the //Math.clamp()// funtion at this point.)\

<<set $valueToClamp to 5>>
''Current value'': $valueToClamp

Increase the number to a value that is ''within'' the desired range.
eg. Add 1 to the current value.\

<<set $valueToClamp to Math.clamp($valueToClamp + 1, 1, 10)>>
''New value'': $valueToClamp

Try to increase the number to a value that is ''outside'' the desired range.
eg. Add 100 to the current value.\

<<set $valueToClamp to Math.clamp($valueToClamp + 100, 1, 10)>>
''New value'': $valueToClamp

Decrease the number to a value that is ''within'' the desired range.
eg. Minus 5 from the current value.\

<<set $valueToClamp to Math.clamp($valueToClamp - 5, 1, 10)>>
''New value'': $valueToClamp

Try to decrease the number to a value that is ''outside'' the desired range.
eg. Minus 100 from the current value.\

<<set $valueToClamp to Math.clamp($valueToClamp - 100, 1, 10)>>
''New value'': $valueToClamp

```

Download: <a href="sugarcube_clamping_numbers_twee.txt" target="_blank">Twee Code</a>

