# "Dropdown": Chapbook (v1.0)

## Summary

The insert [`{dropdown}`](https://klembot.github.io/chapbook/guide/player-input/dropdown-menus-cycling-links.html) is used to create a dropdown menu in Chapbook. The `for:` option specifies where to save the selected value and the `choices:` option defines what the choices should be for the user.

## Example

[Download](chapbook_dropdown_example.html)

## Twee Code

```twee
:: StoryTitle
Chapbook: Dropdown

:: Start
{dropdown menu for: "chosenValue", choices: ["Up", "Down", "Left", "Right"]}

[[Check Choice]]

:: Check Choice
You chose {chosenValue}.

```

[Twee Download](chapbook_dropdown_twee.txt)
