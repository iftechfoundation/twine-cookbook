# "Limiting the Range of a Number": Harlowe (v3.2)

## Summary

This example demonstrates how to limit a numeric variable to a value between a set range. This process is commonly known as clamping.

Harlowe does not include any built-in functionality, but the effect can be achieved with the Harlowe macros [`(min:)`](https://twine2.neocities.org/#macro_min) and [`(max:)`](https://twine2.neocities.org/#macro_max). The former returns the lowest of the list of values provided to it, so it can be used to prevent numbers from exceeding a given value, while the latter returns the highest of the list of values, meaning it can be used to prevent numbers from going below a given value.

## Example

[Download](harlowe_clamping_numbers_example.html){: target="_top" download="harlowe_clamping_numbers_example.html"}

## Twee Code

```twee
:: StoryTitle
Limiting the range of a number in Harlowe

:: Start
Initialize the numeric variable to a value with the range you want.
eg. between ''1'' and ''10'' inclusive.
&#40;note: You don't need to clamp anything at this point.&#41;\

(set: $valueToClamp to 5)
''Current value'': $valueToClamp

Increase the number to a value that is ''within'' the desired range.
eg. Add 1 to the current value.\

(set: $valueToClamp to (min: $valueToClamp + 1, 10))
''New value'': $valueToClamp

Try to increase the number to a value that is ''outside'' the desired range.
eg. Add 100 to the current value.\

(set: $valueToClamp to (min: $valueToClamp + 100, 10))
''New value'': $valueToClamp

Decrease the number to a value that is ''within'' the desired range.
eg. Minus 5 from the current value.\

(set: $valueToClamp to (max: $valueToClamp - 5, 1))
''New value'': $valueToClamp

Try to decrease the number to a value that is ''outside'' the desired range.
eg. Minus 100 from the current value.\

(set: $valueToClamp to (max: $valueToClamp - 100, 1))
''New value'': $valueToClamp
```

[Twee Download](harlowe_clamping_numbers_twee.txt){: target="_top" download="harlowe_clamping_numbers_twee.txt"}