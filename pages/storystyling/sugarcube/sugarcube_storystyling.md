# "Variable Story Styling": SugarCube (v2.18)

## Summary

"Variable Story Styling" demonstrates how to use the [`<<toggleClass>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-toggleclass) macro to switch between two pre-defined style rule-sets. Combined with the "body" selector, the entire page is selected and the classes are switched when the macro is used.

## Example

[Download](sugarcube_storystyling_example.html){ target="_top" download="sugarcube_storystyling_example.html"}

## Twee Code

```twee
:: StoryTitle
Variable Story Styling in SugarCube

:: UserStylesheet[stylesheet]
.green {
  background: white;
    color: green;
}
.white {
  background: black;
    color: white;
}

:: Start
<<set $classToShow to "green">>
This text is green on a white background.
<<toggleclass "body" $classToShow>>
[[Next Passage]]

:: Next Passage
<<set $classToShow to "white">>
This text is white on a black background.
<<toggleclass "body" $classToShow>>

```

[Twee Download](sugarcube_storystyling_twee.txt){ target="_top" download="sugarcube_storystyling_twee.txt"}
