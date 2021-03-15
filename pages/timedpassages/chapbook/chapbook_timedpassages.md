# "Timed Passages": Chapbook (v1.0.0)

## Summary

Made famous in [*Queers in Love at the End of the World*](https://w.itch.io/end-of-the-world) (2013), "Timed Passages" uses the JavaScript function **[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)** and Chapbook's internal **go()** function to reload a passage every second. It combines the use of the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) with [multiple modifiers](https://klembot.github.io/chapbook/guide/references/modifiers.html).

## Example

[Download](chapbook_timedpassages_example.html){: target="_top" download="chapbook_timedpassages_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Timed Passages

:: Start
timeLeft: 11
--
[[Start->Timer]]

:: World End
The world ended.

:: Timer
timeLeft: timeLeft - 1
--
[if timeLeft > 0]
  There are {timeLeft} seconds left.
[else]
  {embed passage: 'World End'}
[JavaScript]
  window.setTimeout(() => go('Timer'), 1000);

```

[Twee Download](chapbook_timedpassages_twee.txt){ target="_top" download="chapbook_timedpassages_twee.txt"}
