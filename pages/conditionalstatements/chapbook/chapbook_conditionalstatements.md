# "Conditional Statements": Chapbook (v1.0.0)

## Summary

The `[if condition]` and `[else]` modifiers found in the [Conditional Display](https://klembot.github.io/chapbook/guide/state/conditional-display.html) section of the Chapbook guide can be used to conditionally display content based on the current value of a variable.

## Example

[Download](chapbook_conditionalstatements_example.html){ target="_top" download="chapbook_conditionalstatements_example.html"}

## Twee Code

```twee
:: StoryTitle
Conditional Statements in Chapbook

:: Start
animal: "horse"
--
[if animal === "dog"]
It's a dog!
[else]
It's a horse!
[continue]
```

[Twee Download](chapbook_conditionalstatements_twee.txt){ target="_top" download="chapbook_conditionalstatements_twee.txt"}

## See Also

[Setting and Showing Variables](../../settingandshowing/chapbook/chapbook_settingandshowing.md)
