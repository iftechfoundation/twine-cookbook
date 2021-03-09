# "Passage Visits": Chapbook (v1.0.0)

## Summary

In Chapbook, the [lookup](https://klembot.github.io/chapbook/guide/state/objects-and-lookups.html) *passage.visits* variable contains the number of times the current passages has been visited by the user.

## Example

[Download](chapbook_passagevisits_example.html){ target="_top" download="chapbook_passagevisits_example.html"}

## Twee Code

```twee
:: StoryTitle
Chapbook: Passage Visits

:: Start

[[Another Passage]]

:: Another Passage
How many times has the current passage been visited? {passage.visits}

[[Start]]

```

[Twee Download](chapbook_passagevisits_twee.txt){ target="_top" download="chapbook_passagevisits_twee.txt"}
