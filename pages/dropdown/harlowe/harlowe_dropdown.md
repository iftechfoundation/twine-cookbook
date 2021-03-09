# "Dropdown": Harlowe (v3.0)

## Summary

The macro [`(dropdown:)`](https://twine2.neocities.org/#macro_dropdown) was introduced with Harlowe 3.0. It creates a drop-down menu based on the options supplied to it. In order to save the outcome of using the drop-down menu, the keyword [`bind`](https://twine2.neocities.org/#type_bind) is used to save the choice.

## Example

[Download](harlowe_dropdown_example.html){ target="_top" download="harlowe_dropdown_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe 3: Dropdown

:: Start
Choose direction:
(dropdown: bind $direction, "Up", "Down", "Left", "Right")

[[Show result]]

:: Show result
The direction picked was $direction.


```

[Twee Download](harlowe_dropdown_twee.txt){ target="_top" download="harlowe_dropdown_twee.txt"}
