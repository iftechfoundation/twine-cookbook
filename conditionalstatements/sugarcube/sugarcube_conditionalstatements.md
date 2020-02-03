# "Conditional Statements": SugarCube (v2.18)

## Summary

In SugarCube, the [`<<if>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-if) and `<<else>>` macros conditionally run sections. If the statement is true, the `<<if>>` section will be run. Otherwise, the `<<else>>` section will be.

## Live Example

<section>
<iframe src="sugarcube_conditionalstatements_example.html" height=400 width=90%></iframe>

Download: <a href="sugarcube_conditionalstatements_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Conditional Statements in SugarCube

:: Start
<<set $animal to "horse">>

<<if $animal is "dog">>
It's a dog!
<<else>>
It's a horse!
<</if>>
```

Download: <a href="sugarcube_conditionalstatements_twee.txt" target="_blank">Twee Code</a>

## See Also

[Setting and Showing Variables](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
