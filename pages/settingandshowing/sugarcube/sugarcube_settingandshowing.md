# "Setting and Showing Variables": SugarCube (v2.18)

## Summary

Variables, symbols starting with `$` (for normal) or `_` (for temporary), can be "set" using the *[`<<set>>`](http://www.motoslave.net/sugarcube/2/docs/macros.html#macros-set)* macro in SugarCube.

`$` is used for storing data throughout the story, and `_` should be used for data only needed in the current passage. Using `_` is useful for not wanting to accidentally overwrite variables elsewhere in the story. They can also help with debugging through not cluttering up the variables list of future passages.

## Example

[Download](sugarcube_settingandshowing_example.html){ target="_top" download="sugarcube_settingandshowing_example.html"}

## Twee Code

```twee
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

[Twee Download](sugarcube_settingandshowing_twee.txt){ target="_top" download="sugarcube_settingandshowing_twee.txt"}
