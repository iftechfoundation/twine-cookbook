# "Passages in Passages": SugarCube (v2.2)

## Summary

In SugarCube, the contents of a passage can be shown in another through the use of the [`<<include>>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-include) macro. Through using the name of an existing passage, its contents will be included where the macro is called.

## Live Example

<section>
<iframe src="sugarcube_passagesinpassages_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_passagesinpassages_example.html" target="_blank">Live Example</a>
</section>

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

Download: <a href="sugarcube_passagesinpassages_twee.txt" target="_blank">Twee Code</a>
