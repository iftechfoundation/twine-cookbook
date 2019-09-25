# "Passage Visits": SugarCube (v2.2)

## Summary

In SugarCube, the global function [`visited()`](http://www.motoslave.net/sugarcube/2/docs/#functions-function-visited) returns the number of times a passage has been visited during the course of the story. Combined with the [`<<= >>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-equal) expression, the result of a global function can be written to a passage.

## Live Example

<section>
<iframe src="sugarcube_passagevisits_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_passagevisits_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Passage Visits

:: Start
How many times has the passage "Another Passage" been visited? <<= visited("Another Passage")>>

[[Another Passage]]

:: Another Passage
[[Start]]

```

Download: <a href="sugarcube_passagevisits_twee.txt" target="_blank">Twee Code</a>
