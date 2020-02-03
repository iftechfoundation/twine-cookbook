# "Dropdown": Chapbook (v1.0)

## Summary

The insert [`{dropdown}`](https://klembot.github.io/chapbook/guide/player-input/dropdown-menus-cycling-links.html) is used to create a dropdown menu in Chapbook. The `for:` option specifies where to save the selected value and the `choices:` option defines what the choices should be for the user.

## Live Example

<section>
<iframe src="chapbook_dropdown_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_dropdown_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Dropdown

:: Start
{dropdown menu for: "chosenValue", choices: ["Up", "Down", "Left", "Right"]}

[[Check Choice]]

:: Check Choice
You chose {chosenValue}.

```

Download: <a href="chapbook_dropdown_twee.txt" target="_blank">Twee Code</a>
