# "Deleting Variables": SugarCube (v2.18)

## Summary

In SugarCube, [`<<unset>>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-unset) works as a "reverse" to `<<set>>`. Instead of setting a value, it deletes it. `<<unset>>` works on both temporary and story variables.

## Live Example

<section>
<iframe src="sugarcube_deletingvariables_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_deletingvariables_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
SugarCube: Unsetting Variables

:: Start
<<set $proof to "hand-written letter">>

[[Accidentally drop the letter]]

:: Accidentally drop the letter
<<unset $proof>>

[[Present the letter to the sheriff]]

:: Present the letter to the sheriff
You present the $proof to the sheriff, not realizing the rain has washed away the ink from the hand-written letter.

```

Download: <a href="sugarcube_deletingvariables_twee.txt" target="_blank">Twee Code</a>

## See Also

[Conditional Statements](../../conditionalstatements/sugarcube/sugarcube_conditionalstatements.md), [Setting and Showing](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
