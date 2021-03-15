# "Passage Visits": Harlowe (v3.1)

## Summary

In Harlowe 3.1, the keyword [`visits`](https://twine2.neocities.org/#keyword_visits) is introduced. This value will contains the number of times the current passage has been visited.

In this example, the macro [`(str:)`](https://twine2.neocities.org/#macro_str) is used with the keyword `visits` to show the value.

## Example

[Download](harlowe_passagevisits_example.html){: target="_top" download="harlowe_passagevisits_example.html"}

## Twee Code

```twee
:: StoryTitle
Harlowe: Passage Visits

:: Start
How many times has the passage "Another Passage" been visited? (str: visits)

[[Another Passage]]

:: Another Passage
[[Start]]

```

[Twee Download](harlowe_passagevisits_twee.txt){ target="_top" download="harlowe_passagevisits_twee.txt"}
