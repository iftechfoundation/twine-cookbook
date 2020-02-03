# "Timed Passages": Chapbook (v1.0.0)

## Summary

Made famous in [*Queers in Love at the End of the World*](https://w.itch.io/end-of-the-world) (2013), "Timed Passages" uses the JavaScript function **[setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout)** and Chapbook's internal **go()** function to reload a passage every second. It combines the use of the [Vars Section](https://klembot.github.io/chapbook/guide/state/the-vars-section.html) with [multiple modifiers](https://klembot.github.io/chapbook/guide/references/modifiers.html).

## Live Example

<section>
<iframe src="chapbook_timedpassages_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_timedpassages_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
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

Download: <a href="chapbook_timedpassages_twee.txt" target="_blank">Twee Code</a>

