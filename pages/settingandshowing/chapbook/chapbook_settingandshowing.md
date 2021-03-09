# "Setting and Showing Variables": Chapbook (v1.0.0)

## Summary

In Chapbook all variables are initialised and updated within the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) of a passage, this section is always added at the beginning of the passage and there can only be one such section per passage.

The Vars Section is separated from the passage's normal text by two dashes (`--`); The value of a variable can be [displayed](https://klembot.github.io/chapbook/guide/state/displaying-variables.html) using the `{insert}` insert.

## Example

[Download](chapbook_settingandshowing_example.html){ target="_top" download="chapbook_settingandshowing_example.html"}

## Twee Code

```twee
:: StoryTitle
Setting and Showing Variables in Chapbook

:: Start
numberVariable: 5
wordVariable: "five"
phraseVariable: "The value"
--

{phraseVariable} is {numberVariable} and {wordVariable}.

{embed passage: "Increment number"}

The number variable was incremented by one to {numberVariable}.

:: Increment number
numberVariable: numberVariable + 1
--

```

[Twee Download](chapbook_settingandshowing_twee.txt){ target="_top" download="chapbook_settingandshowing_twee.txt"}
