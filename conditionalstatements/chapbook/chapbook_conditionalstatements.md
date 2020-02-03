# "Conditional Statements": Chapbook (v1.0.0)

## Summary

The `[if condition]` and `[else]` modifiers found in the [Conditional Display](https://klembot.github.io/chapbook/guide/state/conditional-display.html) section of the Chapbook guide can be used to conditionally display content based on the current value of a variable.

## Live Example

<section>
<iframe src="chapbook_conditionalstatements_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_conditionalstatements_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
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

Download: <a href="chapbook_conditionalstatements_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/chapbook/chapbook_settingandshowing.md)

