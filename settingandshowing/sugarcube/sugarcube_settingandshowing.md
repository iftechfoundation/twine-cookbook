# "Setting and Showing Variables": SugarCube (v2.18)

## Summary

Variables, symbols starting with ```$``` (for normal) or ```_``` (for temporary), can be "set" using the *[```<<set>>```](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-set)* macro in SugarCube.

## Live Example

<section>
<iframe src="sugarcube_settingandshowing_example.html" height=400 width=90%></iframe>


Download: <a href="sugarcube_settingandshowing_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Setting and Showing Variables in SugarCube

:: Start
<<set $numberVariable to 5>>
<<set $wordVariable to "five">>
<<set $phraseVariable to "The value">>

$phraseVariable is $numberVariable and $wordVariable.

<<set $numberVariable to $numberVariable + 1>>

$phraseVariable is $numberVariable and $wordVariable.

```

Download: <a href="sugarcube_settingandshowing_twee.txt" target="_blank">Twee Code</a>

