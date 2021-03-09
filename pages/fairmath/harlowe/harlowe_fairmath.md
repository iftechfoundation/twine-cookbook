# "Fairmath System": Harlowe (v2.0)

## Summary

"Fairmath System" demonstrates how to re-create the Fairmath system found [in ChoiceScript](http://choicescriptdev.wikia.com/wiki/Arithmetic_operators#Fairmath). Based on a percentage operation, increasing and decreasing changes the value by a percentage as the difference between the original and adjusted value.

This example uses the [`(display:)`](https://twine2.neocities.org/#macro_display) macro in Harlowe to separate operations for increasing and decreasing. Through setting values to adjust, either passage can be included and the *$resultValue* used to track and store changes.

## Example

[Download](harlowe_fairmath_example.html){: target="_top" download="harlowe_fairmath_example.html"}

## Twee Code

```twee
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
<!-- Display (call) the Fairmath Decrease passage -->
(display: "Decrease")
<!-- The new value will be resultValue -->
The adjusted value is $resultValue.

<!-- Update valueToAdjust -->
(set: $valueToAdjust to $resultValue)
<!-- Set originalValue to the value to adjust -->
(set: $originalValue to $valueToAdjust)
<!-- Set the changeValue (percentage) to adjust -->
(set: $changeValue to 100)
<!-- Display (call) the Fairmath Increase passage -->
(display: "Increase")
The adjusted value is $resultValue.

:: Increase
(set: $resultValue to (round: $originalValue+((100-$originalValue)*($changeValue/100))) )

:: Decrease
(set: $resultValue to (round: $originalValue-($originalValue*($changeValue/100)) ) )


```

[Twee Download](harlowe_fairmath_twee.txt){ target="_top" download="harlowe_fairmath_twee.txt"}
