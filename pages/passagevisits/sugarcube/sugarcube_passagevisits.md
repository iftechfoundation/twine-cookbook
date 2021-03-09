# "Passage Visits": SugarCube (v2.2)

## Summary

In SugarCube, the global function **[visited()](http://www.motoslave.net/sugarcube/2/docs/#functions-function-visited)** returns the number of times a passage has been visited during the course of the story. Combined with the [`<<= >>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-equal) macro expression, the result of a global function can be written to a passage.

## Example

[Download](sugarcube_passagevisits_example.html){: target="_top" download="sugarcube_passagevisits_example.html"}

## Twee Code

```twee
:: StoryTitle
SugarCube: Passage Visits

:: Start
How many times has the passage "Another Passage" been visited? <<= visited("Another Passage")>>

[[Another Passage]]

:: Another Passage
[[Start]]

```

[Twee Download](sugarcube_passagevisits_twee.txt){ target="_top" download="sugarcube_passagevisits_twee.txt"}
