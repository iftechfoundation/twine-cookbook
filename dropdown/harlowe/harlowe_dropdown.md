# "Dropdown": Harlowe (v3.0)

## Summary

The macro [*(dropdown:)*](https://twine2.neocities.org/#macro_dropdown) was introduced with Harlowe 3.0. It creates a drop-down menu based on the options supplied to it. In order to save the outcome of using the drop-down menu, the keyword [*bind*](https://twine2.neocities.org/#type_bind) is used to save the choice.

## Twee Code

```
:: StoryTitle
Harlowe 3: Dropdown

:: Start
Choose direction:
(dropdown: bind $direction, "Up", "Down", "Left", "Right")

[[Show result]]

:: Show result
The direction picked was $direction.


```
