# "Fairmath System": Harlowe (v2.0)

*Contributed by <a href="https://github.com/videlais">@videlais</a>*

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, addition and subtraction changes the value by a percentage as the difference between the original and adjusted value.

This example uses the *(display:)* macro in Harlowe to separate operations for addition and subtraction. Through setting values to adjust, either passage can be included and the *$resultValue* used to track and store changes.


## Live Example

<section>
<iframe src="harlowe_fairmath_example.html" height=400 width=90%></iframe>


Download: <a href="harlowe_fairmath_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Fairmath System in Harlowe

:: Start
<!-- Fairmath formulas based on http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath -->

<!-- Set an initial value for the story -->
(set: $valueToAdjust to 100)
The initial value is $valueToAdjust.

<!-- Set originalValue to the value to adjust -->
(set: $originalValue to $valueToAdjust)
<!-- Set the changeValue (percentage) to adjust -->
(set: $changeValue to 50)
<!-- Display (call) the Fairmath Subtraction passage -->
(display: "Subtraction")
<!-- The new value will be resultValue -->
The adjusted value is $resultValue.

<!-- Update valueToAdjust -->
(set: $valueToAdjust to $resultValue)
<!-- Set originalValue to the value to adjust -->
(set: $originalValue to $valueToAdjust)
<!-- Set the changeValue (percentage) to adjust -->
(set: $changeValue to 100)
<!-- Display (call) the Fairmath Addition passage -->
(display: "Addition")
The adjusted value is $resultValue.

:: Addition
(set: $resultValue to (round: $originalValue+((100-$originalValue)*($changeValue/100))) )

:: Subtraction
(set: $resultValue to (round: $originalValue-($originalValue*($changeValue/100)) ) )

```

Download: <a href="harlowe_fairmath_twee.txt" target="_blank">Twee Code</a>

