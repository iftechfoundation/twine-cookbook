# "Cycling Choices": Chapbook (v1.0.0)

## Summary

Chapbook provides the [`{cycling link}`](https://klembot.github.io/chapbook/guide/player-input/dropdown-menus-cycling-links.html) modifier for creating a cycling link effect.

## Live Example

<section>
<iframe src="chapbook_cycling_example.html" height=400 width=90%></iframe>


Download: <a href="chapbook_cycling_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Cycling Links

:: Start
This cycling link example remembers the choice made:
{cycling link for: 'hair', choices: ["Black", "Brown", "Blonde", "Red", "White"]}

This cycling-link example will disappear (show empty string) on its last choice:
{cycling link for: 'breakfast', choices: ["Two eggs", "One egg", ""]}

```

Download: <a href="chapbook_cycling_twee.txt" target="_blank">Twee Code</a>

