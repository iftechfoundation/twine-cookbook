# "Conditional Statements": SugarCube (v2.18)

## Summary

In SugarCube, the *[&lt;&lt;if&gt;&gt;](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-if)* and *&lt;&lt;else&gt;&gt;* macros conditionally run sections. If the statement is true, the *&lt;&lt;if&gt;&gt;* section will be run. Otherwise, the *&lt;&lt;else&gt;&gt;* section will be.

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

## See Also

[Setting and Showing Variables](../../settingandshowing/sugarcube/sugarcube_settingandshowing.md)
