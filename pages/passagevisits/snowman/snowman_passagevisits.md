# "Passage Visits": Snowman (v2.0)

## Summary

Starting with Snowman 2.0, the global function **[visited()](https://videlais.github.io/snowman/#/2/utility/visited)** returns the number of times one or more passages have been visited during the course of the story. Combined with the use of [Underscore template interpolation](https://videlais.github.io/snowman/#/2/learning/template), the result of a function can be written to a passage.

## Example

[Download](snowman_passagevisits_example.html){: target="_top" download="snowman_passagevisits_example.html"}

## Twee Code

```twee
:: StoryTitle
Snowman: Passage Visits

:: Start
How many times has the passage "Another Passage" been visited? <%= visited("Another Passage") %>

[[Another Passage]]

:: Another Passage
[[Start]]

```

[Twee Download](snowman_passagevisits_twee.txt){ target="_top" download="snowman_passagevisits_twee.txt"}
