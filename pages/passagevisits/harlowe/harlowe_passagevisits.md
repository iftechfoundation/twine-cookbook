# "Passage Visits": Harlowe (v1.0)

## Summary

In Harlowe, the macro [`(count:)`](https://twine2.neocities.org/#macro_count) returns the number of times a value appears in an array. The macro [`(history:)`](https://twine2.neocities.org/#macro_history) returns an array of any passages visited as part of the story.

Combined together, the macro `(count:)` with the `(history:)` can return the number of times a certain passage has been visited during the course of the story.

## Example

[Download](harlowe_passagevisits_example.html)

## Twee Code

```twee
:: StoryTitle
Harlowe: Passage Visits

:: Start
How many times has the passage "Another Passage" been visited? (count: (history: ), "Another Passage")

[[Another Passage]]

:: Another Passage
[[Start]]

```

[Twee Download](harlowe_passagevisits_twee.txt)
