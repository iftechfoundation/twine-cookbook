# "Deleting Variables": SugarCube (v2.18)

## Summary

In SugarCube, [`<<unset>>`](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-unset) works as a "reverse" to `<<set>>`. Instead of setting a value, it deletes it. `<<unset>>` works on both temporary and story variables.

## Example

[Download](sugarcube_deletingvariables_example.html)

## Twee Code

```twee
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

[Twee Download](sugarcube_deletingvariables_twee.txt)

## See Also

[Conditional Statements](../../conditionalstatements/sugarcube/sugarcube_conditionalstatements.md), [Setting and Showing](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
