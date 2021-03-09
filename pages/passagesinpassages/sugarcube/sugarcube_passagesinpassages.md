# "Passages in Passages": SugarCube (v2.2)

## Summary

In SugarCube, the contents of a passage can be shown in another through the use of the [`<<include>>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-include) macro. Through using the name of an existing passage, its contents will be included where the macro is called.

## Example

[Download](sugarcube_passagesinpassages_example.html){: target="_top" download="sugarcube_passagesinpassages_example.html"}

## Twee Code

```twee
:: StoryTitle
SugarCube: Passages in Passages

:: Start
This is the Start passage!
<<include "Another">>

:: Another
And this is Another passage!

```

[Twee Download](sugarcube_passagesinpassages_twee.txt){ target="_top" download="sugarcube_passagesinpassages_twee.txt"}
