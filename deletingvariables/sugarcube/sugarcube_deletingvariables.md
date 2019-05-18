# "Deleting Variables": SugarCube (v2.18)

## Summary

In SugarCube, [*&lt;&lt;unset&gt;&gt;*](http://www.motoslave.net/sugarcube/2/docs/#macros-macro-unset) works as a "reverse" to &lt;&lt;set&gt;&gt;. Instead of setting a value, it deletes it. *&lt;&lt;unset&gt;&gt;* works on both temporary and story variables.

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

## See Also

[Conditional Statements](../../conditionalstatements/sugarcube/sugarcube_conditionalstatements.md), [Setting and Showing](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
