# "Cycling Choices": Chapbook (v1.0.0)

## Summary

Chapbook provides the [`{cycling link}`](https://klembot.github.io/chapbook/guide/player-input/dropdown-menus-cycling-links.html) modifier for creating a cycling link effect.

## Example

[Download](chapbook_cycling_example.html){ target="_top" download="chapbook_cycling_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Cycling Links

:: Start
This cycling link example remembers the choice made:
{cycling link for: 'hair', choices: ["Black", "Brown", "Blonde", "Red", "White"]}

This cycling-link example will disappear (show empty string) on its last choice:
{cycling link for: 'breakfast', choices: ["Two eggs", "One egg", ""]}

```

[Twee Download](chapbook_cycling_twee.txt){ target="_top" download="chapbook_cycling_twee.txt"}
